# Cryptography Policy — backend replies to Deejay's comments

Each section: where the comment sits, what Deejay asked, the reply to paste, and any edit to make in the document.

Skipped as not backend: USB Block (5.3), Microsoft Defender (5.3), Regulatory Compliance (8.1), Review Schedule (9.1).

All facts checked against the live AWS account and the code on 24 Sep 2026.

---

## 1. Scope — Information Assets (section 3)

**Deejay:** Confirm the scope reflects the information, systems and AWS services Riverly uses.

**Reply:**

Confirmed for the technical environment. Customer and financial data is held in Amazon RDS PostgreSQL, encrypted with AWS KMS. Files and documents are in Amazon S3 with AES-256 encryption. Application secrets are in AWS Secrets Manager. Short-lived session and cache data is in Amazon ElastiCache (Redis). The application runs on Amazon ECS, and all internet-facing traffic goes through an AWS Application Load Balancer over TLS 1.2 or 1.3.

**Edit:** none.

---

## 2. Mandatory Cryptographic Protection Scenarios (section 5.2)

**Deejay:** Confirm these scenarios match current operations, and whether any other systems or data need cryptographic protection.

**Reply:**

Confirmed. Cloud storage encryption, AWS KMS for the database, TLS 1.2 or higher for internet traffic and bcrypt for password hashing are all in place. Other data that needs cryptographic protection, all currently protected: customer BVN (AES-256-GCM encryption in the application), transaction PINs and one-time codes (bcrypt), application secrets (AWS Secrets Manager), and session tokens and provider webhooks (HMAC-SHA256 and HMAC-SHA512). Riverly does not store or process payment card numbers.

**Optional line — your call whether to include it:**

One gap: the Amazon ElastiCache (Redis) cache that holds short-lived session and cache data is not currently encrypted at rest or in transit. It is only reachable inside the private network. Remediation will be scheduled.

**Edit:** none.

---

## 3. Technique Selection Matrix — BitLocker row (section 5.3)

**Deejay:** Confirm which technologies are actively used and which are not applicable.

**Reply:**

All technologies from the gap assessment are confirmed in use: AWS KMS, AES-256 storage encryption, TLS 1.2 or higher (the load balancer allows TLS 1.2 and 1.3 only), AWS Certificate Manager, hashing, HMAC signing, AWS Secrets Manager and bcrypt. I've added them to the table. The three existing rows (BitLocker, USB Block, Microsoft 365) are about staff devices and email, not the application, so I've left those for Femi to confirm.

**Edit — add these rows to the table:**

| Use Case | Primary Technique | Specific Requirements | Key Management |
|---|---|---|---|
| Database (Amazon RDS PostgreSQL) | AES-256 encryption at rest | RDS storage encryption, including all automated and manual snapshots | AWS KMS (AWS-managed key) |
| Cloud object storage (Amazon S3) | AES-256 encryption at rest | Default server-side encryption (SSE-S3) on all buckets | AWS-managed keys |
| Sensitive customer fields (BVN) | AES-256-GCM application-layer encryption | Authenticated encryption with a unique nonce per value | Key held in AWS Secrets Manager |
| Data in Transit | TLS 1.2 or higher | Application Load Balancer allows TLS 1.2 and 1.3 only; HSTS enforced | Certificates issued by AWS Certificate Manager |
| Certificate Management | X.509 digital certificates (RSA-2048) | AWS Certificate Manager (ACM), DNS-validated, automatic renewal | Managed by ACM |
| Passwords, transaction PINs and one-time codes | bcrypt hashing | Salted, adaptive hashing within the application | Not applicable (one-way hash) |
| Application secrets and credentials | Encryption at rest | AWS Secrets Manager | AWS KMS (AWS-managed key) |
| Session tokens and webhook integrity | HMAC-SHA256 / HMAC-SHA512 | Session tokens signed with HMAC-SHA256; provider webhook signatures verified using constant-time comparison | Signing keys held in AWS Secrets Manager |

---

## 4. Approved Algorithms (section 6.1)

**Deejay:** Confirm which algorithms and hashing methods are actually used.

**Reply:**

In use: AES-256 (AES-256-GCM for encryption in the application; AES-256 for RDS and S3 storage encryption), RSA-2048 (TLS certificates from ACM), SHA-256 (HMAC-SHA256 token signing and webhook checks, and one-way hashing of identifiers), SHA-512 (HMAC-SHA512 webhook checks) and bcrypt (passwords, PINs, one-time codes). Not in use: ChaCha20, ECDSA, Ed25519, SHA-3 and Argon2id. They can stay on the list as permitted options, or be removed if the list should show only what is in use.

**Edit:** none.

---

## 5. Argon2id (section 6.1)

**Deejay:** Should bcrypt be formally approved, and is Argon2id used or planned?

**Reply:**

Yes, bcrypt should be approved. It is used for all passwords, transaction PINs and one-time codes. Argon2id is not currently used; it can stay approved for future use. I've also added a documented exception for HMAC-SHA1, which we use only to verify webhook signatures from Anchor because that provider requires it.

**Edit 1 — add to the end of the Argon2id line:**

Not currently in use; approved for future implementations.

**Edit 2 — add a new bullet under Approved Hash Functions:**

bcrypt: For password, transaction PIN and one-time code hashing. In use across the Riverly platform.

**Edit 3 — add a new bullet under Prohibited Algorithms, after the MD5, SHA-1 line:**

Documented exception: HMAC-SHA1 is used only to verify webhook signatures received from Anchor, as required by that provider, and for no other purpose.

---

## 6. Cryptographic Libraries / Random Number Generation (section 6.2)

**Deejay:** Does Riverly manage its own cryptographic libraries and random number generation, or rely on AWS services and frameworks?

**Reply:**

We rely on platform and AWS-managed cryptography and don't implement our own. The application uses the .NET platform cryptography libraries and BCrypt.Net-Next. Random values come from the platform's cryptographically secure generator. Database, storage and secrets encryption use AWS-managed services (KMS). FIPS 140-2 Level 3 is stated as preferred, not required; our libraries do not run in FIPS mode.

**Edit — replace these two bullets under Random Number Generation:**

Proper entropy seeding from hardware sources.
Regular entropy pool monitoring and maintenance.

**with this one bullet:**

Entropy is supplied by the operating system; applications use the platform CSPRNG and do not implement their own random number generation or entropy management.

---

## 7. Penetration testing of cryptographic implementations (section 7.2)

**Deejay:** How does Riverly validate its cryptographic controls, and who monitors certificate expiry and cryptographic configuration?

**Reply:**

TLS is enforced by the load balancer security policy (TLS 1.2 and 1.3 only). Encryption of RDS, snapshots, S3 and Secrets Manager is confirmed from the AWS configuration. Certificates are issued by ACM, DNS-validated, and renew automatically; the current certificate is valid to 9 January 2027. An OWASP Top 10 (2025) assessment on 22 September 2026 covered the cryptographic controls. No penetration test of the cryptographic implementation has been done yet. AWS configuration is currently managed by the Fluxus engineering team.

**Edit:** none.

---

## 8. Algorithm validation and compliance testing (section 7.2)

**Deejay:** Same as 7.2 above.

**Reply:**

Algorithms are set by the platform libraries and AWS services listed under 6.1. No separate algorithm compliance testing is done today. See the reply on penetration testing above.

**Edit:** none.

---

## 9. Certificate and key expiration monitoring (section 7.2)

**Deejay:** Same as 7.2 above.

**Reply:**

Certificates renew automatically through ACM (DNS-validated, eligible for renewal). There is no separate certificate-expiry alarm. KMS keys are AWS-managed, and AWS rotates them automatically.

**Edit:** none.

---

## 10. Trust Store Management (section 7.3)

**Deejay:** Do the trust store and certificate requirements reflect how certificates are managed in AWS, including renewal, expiry monitoring and access?

**Reply:**

Confirmed. One ACM certificate covers api.riverly.ng and api-staging.riverly.ng. It is DNS-validated and renews automatically. Riverly does not keep a custom trust store; outbound connections use the application runtime's default trust store.

**Edit:** none.

---

## 11. Roles and Responsibilities (section 8.3)

**Deejay:** Who is responsible for AWS KMS, key management, ACM, TLS configuration and monitoring of cryptographic controls?

**Reply:**

Today, AWS KMS, ACM, TLS configuration and monitoring of cryptographic controls are handled by the Fluxus engineering team. KMS keys are AWS-managed, so AWS handles key generation and rotation. Formal ownership is for Femi to confirm.

**Edit:** none.
