<a id="top"></a>

# Audit Day 3 — Backend Guide

**Wed 30 Sept 2026**
**Technological controls (Annex A.8)**
9:00–1:00 · A.8.1–A.8.22
2:00–3:30 · A.8.23–A.8.34
Auditors: Abdulraqeeb Andu, Michael Loya

All facts checked live on 29 Sept 2026.

---

## Contents

**Setup**
- [1. Before the session](#setup)
- [2. Rules while sharing your screen](#rules)
- [3. Numbers to know](#numbers)
- [4. What the backend uses](#stack)

**Controls, 9:00–1:00**
- [8.1 Staff laptops](#c81)
- [8.2 Privileged access](#c82)
- [8.3 Access to data](#c83)
- [8.4 Access to source code](#c84)
- [8.5 Login security](#c85)
- [8.6 Capacity](#c86)
- [8.7 Malware](#c87)
- [8.8 Vulnerabilities](#c88)
- [8.9 Configuration](#c89)
- [8.10 Data deletion](#c810)
- [8.11 Data masking](#c811)
- [8.12 Data leakage](#c812)
- [8.13 Backups](#c813)
- [8.14 Redundancy](#c814)
- [8.15 Logging](#c815)
- [8.16 Monitoring](#c816)
- [8.17 Clock sync](#c817)
- [8.18 / 8.19 Admin tools, software installs](#c818)
- [8.20–8.22 Network security](#c820)

**Controls, 2:00–3:30**
- [8.23 Web filtering](#c823)
- [8.24 Cryptography](#c824)
- [8.25–8.27 Secure development](#c825)
- [8.28 Secure coding](#c828)
- [8.29 Security testing](#c829)
- [8.30 Outsourced development](#c830)
- [8.31 Separate environments](#c831)
- [8.32 Change management](#c832)
- [8.33 Test data](#c833)
- [8.34 Audit testing](#c834)

**If things get hard**
- [GuardDuty findings, explained](#guardduty)
- [Known gaps, honest answers](#gaps)
- [If you don't know an answer](#dontknow)

---

<a id="setup"></a>

## 1. Before the session

[↑ Back to top](#top)

**30 minutes before:**

1. Log in to AWS: `https://132597214585.signin.aws.amazon.com/console` with user **YERINS** and your MFA code.
2. Check the region, top right: **Europe (Stockholm)**. If it's wrong, click it and pick Stockholm.
3. Log in to GitHub as **Yerinsfluxus**.
4. Open VS Code on the `riverly-api` folder.
5. Open all the tabs at once. On the laptop, paste this into Terminal:

```
open "https://console.aws.amazon.com/iam/home#/users" "https://eu-north-1.console.aws.amazon.com/rds/home?region=eu-north-1#database:id=riverly-prod-db;is-cluster=false" "https://eu-north-1.console.aws.amazon.com/cloudwatch/home?region=eu-north-1#alarmsV2:" "https://eu-north-1.console.aws.amazon.com/cloudwatch/home?region=eu-north-1#logsV2:log-groups" "https://eu-north-1.console.aws.amazon.com/guardduty/home?region=eu-north-1#/summary" "https://eu-north-1.console.aws.amazon.com/cloudtrail/home?region=eu-north-1#/trails" "https://eu-north-1.console.aws.amazon.com/sns/v3/home?region=eu-north-1#/topics" "https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#LoadBalancers:" "https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#SecurityGroups:" "https://eu-north-1.console.aws.amazon.com/acm/home?region=eu-north-1#/certificates/list" "https://s3.console.aws.amazon.com/s3/buckets?region=eu-north-1" "https://eu-north-1.console.aws.amazon.com/secretsmanager/listsecrets?region=eu-north-1" "https://eu-north-1.console.aws.amazon.com/ecs/v2/clusters/riverly-cluster-prod/services?region=eu-north-1" "https://github.com/DRPFL-RIVERLY/riverly_backend/pulls?q=is%3Apr+is%3Amerged" "https://github.com/DRPFL-RIVERLY/riverly_backend/actions"
```

6. Open these documents in Finder, ready to share:
   - `Desktop/Riverly_OWASP_Assessment/` (the OWASP report and screenshots)
   - `Downloads/Backup_Restoration_Test_Report_2026-09-11.pdf`
   - `Downloads/backup-restoration-test-2026-09-03.pdf`
   - `Downloads/riverly-system-network.drawio.pdf` (the system diagram)
   - `Downloads/Riverly ISMS Cryptography Policy v1.0.docx`
7. Close email, WhatsApp, Slack and any unrelated tabs.

---

<a id="rules"></a>

## 2. Rules while sharing your screen

[↑ Back to top](#top)

- **You click, they watch.** Never hand over control.
- **Never open a secret's value.** In Secrets Manager, show the list only. Never click "Retrieve secret value".
- **Never show customer data.** Show settings, not database rows.
- **Never show access keys.** In IAM, don't open the "Security credentials" tab.
- **Say it before you click it.** "I'm opening the database settings to show encryption."
- **If a page is slow, talk while it loads.**
- **Don't volunteer extra problems.** Answer what's asked, honestly.

---

<a id="numbers"></a>

## 3. Numbers to know

[↑ Back to top](#top)

- **AWS account:** 132597214585
- **Region:** eu-north-1 (Stockholm)
- **AWS console users:** 2 (YERINS, Fatai). Both have MFA.
- **Root account:** has MFA
- **Service accounts:** 2 (S3 uploads, security monitoring read-only). No console access.
- **Backups:** daily at 02:00 UTC, kept **14 days**, plus a manual snapshot before every production deploy
- **Restore time (tested):** about **6.5 minutes**
- **Log retention:** production **365 days**
- **Alarms:** **15**
- **Customer login lockout:** **5** wrong tries locks the account for up to **30 minutes**
- **Admin login lockout:** **5** wrong tries locks it for **15 minutes**
- **Session:** access token **5 min**, logs out after **15 min** idle, **12 hours** maximum
- **Admin session:** **8 hours**
- **TLS:** **1.2 and 1.3 only**
- **Automated tests:** **125** (95 run every time, 30 need a database, 0 failing)

---

<a id="stack"></a>

## 4. What the backend uses

[↑ Back to top](#top)

**Application**
- .NET 8 API, one application serving Personal, SME and Corporate
- PostgreSQL database (Amazon RDS)
- Redis cache (Amazon ElastiCache)

**AWS**
- ECS Fargate: runs the app
- Application Load Balancer: HTTPS entry point
- RDS: database
- ElastiCache: cache
- S3: file storage
- ECR: app images
- Secrets Manager: passwords and API keys
- KMS: encryption keys
- ACM: HTTPS certificates
- CloudWatch: logs and alarms
- CloudTrail: record of every AWS action
- GuardDuty: threat detection
- SNS: alert emails
- EventBridge: staging on/off schedule, security alerts
- EC2: one bastion server, for database access only
- Systems Manager: bastion access (no SSH)
- IAM: users and permissions
- VPC: private network

**GitHub**
- Organisation: DRPFL-RIVERLY (free plan)
- Backend repo: riverly_backend
- gitleaks: scans every commit for leaked secrets
- Dependabot: weekly dependency security updates
- GitHub Actions: deploys, using OIDC (no stored AWS keys)

**Third parties that handle data**
- Providus / XpressWallet: wallets
- Anchor: SME accounts
- Dojah: identity checks (BVN, NIN, liveness)
- Sendchamp: SMS/WhatsApp OTP
- Resend / SendGrid: email
- Firebase: push notifications

---

<a id="c81"></a>

## 8.1 Staff laptops

[↑ Back to top](#top)

**Q:** How are engineering laptops protected?

**Say:** Not a backend control. Laptop policy sits with HR/IT. Femi to answer.

---

<a id="c82"></a>

## 8.2 Privileged access

[↑ Back to top](#top)

**Q:** Who has admin access to AWS?

**Say:** Two engineers, me and Fatai. Both have MFA. The root account also has MFA. Service accounts only have the permissions their job needs, and none of them can log in to the console.

**Show:**
1. IAM tab (or search bar → type **IAM** → click IAM)
2. Left menu → **Users**
3. Point at the **MFA** column: YERINS and Fatai show MFA
4. Point out the two service accounts (riverly-prod-s3, riverly-security-monitoring), which have no console access

**If asked "why do both engineers have full admin?"**
**Say:** Small team, two engineers who run the whole platform. Every action we take is recorded in CloudTrail. Narrowing it is on our improvement list.

**If asked "who uses the root account?"**
See [known gaps](#gaps) item 10.

**App admins:**
**Say:** The admin dashboard uses named logins with roles (SuperAdmin, Compliance, Operations). KYC and business approvals need a named Compliance or SuperAdmin login, so every decision traces to a person.

---

<a id="c83"></a>

## 8.3 Access to data

[↑ Back to top](#top)

**Q:** How do you stop one customer seeing another's data?

**Say:** Every request is checked on the server. The app denies by default, so an endpoint is locked unless it's deliberately made public. Each query filters by the logged-in user's own ID, so you can't fetch someone else's record by changing an ID.

**Show (code, if asked):**
1. VS Code → **Cmd+P** → type `Program.cs:439` → Enter
2. Point at `FallbackPolicy`: "this locks every endpoint by default"
3. **Cmd+P** → `AdminRoleRequiredAttribute.cs`: "admin decisions need a named role"

**Q:** Can staff read customer data directly in the database?

**Say:** The database is private, with no internet access. The only way in is through the bastion server, using AWS login plus MFA. Admin screens mask personal data like phone, email and ID numbers.

---

<a id="c84"></a>

## 8.4 Access to source code

[↑ Back to top](#top)

**Q:** Who can access the code?

**Say:** All repos are private, in the DRPFL-RIVERLY GitHub organisation. Access is per named person.

Backend repo access (GitHub usernames):
- Admin: Femi-fluxx, oltoch, Yerinsfluxus
- Maintain: fatai-sanni
- Read only: thesarahoba

**Show:**
1. `github.com/DRPFL-RIVERLY/riverly_backend`
2. **Settings** → **Collaborators and teams**

**Honest gaps (only if asked):** GitHub 2FA isn't enforced across the organisation, and there's no branch protection. See [known gaps](#gaps).

---

<a id="c85"></a>

## 8.5 Login security

[↑ Back to top](#top)

**Q:** How is customer login protected?

**Say:**
- Passwords and PINs are stored as bcrypt hashes, never plain text.
- 5 wrong tries locks the account for up to 30 minutes.
- Login and OTP requests are rate-limited per IP address.
- A new device must be verified with a one-time code.
- Sessions expire after 15 minutes idle, and after 12 hours no matter what.

**Show (live, if asked):**
Terminal on the laptop:
```
for i in $(seq 1 14); do printf "%s " $(curl -s -o /dev/null -w "%{http_code}" -X POST -H "Content-Type: application/json" -d '{}' https://api-staging.riverly.ng/api/v1/identity/login); done; echo
```
**Say:** "Ten requests go through, then 429: blocked." Or show OWASP screenshot **E-14**.

Staging sleeps overnight. It's up weekdays from about 6am to 10pm Lagos time.

---

<a id="c86"></a>

## 8.6 Capacity

[↑ Back to top](#top)

**Q:** How do you know you won't run out of capacity?

**Say:** We have alarms for high CPU, high memory, database connections, low database storage, and the service going unhealthy.

**Show:** Alarms tab → point at `riverly-prod-ecs-cpu-high`, `riverly-prod-ecs-mem-high`, `riverly-prod-rds-low-storage`, `riverly-prod-rds-high-connections`, `riverly-prod-alb-no-healthy-hosts`.

---

<a id="c87"></a>

## 8.7 Malware

[↑ Back to top](#top)

**Q:** How are servers protected from malware?

**Say:** We don't run our own servers. The app runs on AWS Fargate: containers rebuilt from a clean image on every deploy, and nobody logs into them. AWS GuardDuty watches the account for threats. Laptop antivirus is HR/IT.

---

<a id="c88"></a>

## 8.8 Vulnerabilities

[↑ Back to top](#top)

**Q:** How do you find and fix vulnerabilities?

**Say:**
- Dependabot checks our libraries weekly and raises updates.
- gitleaks scans every commit for leaked secrets.
- We ran an OWASP Top 10 (2025) assessment on 22 Sept: 9 issues found, 8 fixed and verified in production.
- Last dependency scan: 0 known vulnerable packages.

**Show:**
1. The OWASP report: `Desktop/Riverly_OWASP_Assessment/`
2. GitHub → riverly_backend → **Actions** → click **gitleaks** → recent runs

---

<a id="c89"></a>

## 8.9 Configuration

[↑ Back to top](#top)

**Q:** How do you control configuration?

**Say:** App configuration is version-controlled with the code. Secrets are in AWS Secrets Manager, never in code. AWS changes are made by the two engineers, and CloudTrail records every change with who made it and when.

**Show:** CloudTrail tab → **Event history**. Filter **Event name** = `PutMetricAlarm`, which shows my changes with my name and time.

**Honest gap:** Infrastructure isn't defined as code yet (no Terraform). Changes are manual but fully logged.

---

<a id="c810"></a>

## 8.10 Data deletion

[↑ Back to top](#top)

**Q:** How is data deleted?

**Say:** The app has admin tools to remove a customer's records. A formal data retention and deletion schedule isn't defined yet. That's a policy decision for Femi.

---

<a id="c811"></a>

## 8.11 Data masking

[↑ Back to top](#top)

**Q:** Do you mask personal data?

**Say:** Yes, in three places:
1. Admin screens mask email, phone, name and ID numbers.
2. The database has masked views, so an analyst never sees raw personal data.
3. Logs automatically remove BVN, NIN, date of birth, phone and address before anything is written.

**Show (code):**
- **Cmd+P** → `PiiMask.cs`
- **Cmd+P** → `LogRedactor.cs`
- **Cmd+P** → `MaskedViewsSql.cs`

---

<a id="c812"></a>

## 8.12 Data leakage

[↑ Back to top](#top)

**Q:** How do you prevent data leaking?

**Say:**
- All storage buckets block public access.
- The database is private.
- Logs strip personal data.
- gitleaks catches secrets in code before they spread.
- Error messages to users are generic, so internal details never leak.

**Show:** S3 tab → click **riverly-prod-assets** → **Permissions** tab → "Block all public access: **On**".

---

<a id="c813"></a>

## 8.13 Backups

[↑ Back to top](#top)

**Q:** How is data backed up, and have you tested restoring?

**Say:** Daily automatic backups, kept 14 days, plus point-in-time restore to within about 5 minutes. A manual snapshot is taken before every production deploy. All backups are encrypted. We did full restore tests on 3 and 11 September: the restore took about 6.5 minutes, with all data intact.

**Show:**
1. RDS tab (riverly-prod-db)
2. Tab **Maintenance & backups**
3. Point at: Automated backups **Enabled**, retention **14 days**
4. Scroll to **Snapshots**: daily + pre-deploy ones
5. Open `Backup_Restoration_Test_Report_2026-09-11.pdf`

---

<a id="c814"></a>

## 8.14 Redundancy

[↑ Back to top](#top)

**Q:** What if a data centre fails?

**Say:** The load balancer runs across multiple availability zones. The database is currently single-zone. If its zone failed, we'd restore from backup, which we've tested at about 6.5 minutes. Enabling Multi-AZ is on our improvement list.

**Show (if asked):** RDS tab → **Configuration** tab → **Multi-AZ: No**.

---

<a id="c815"></a>

## 8.15 Logging

[↑ Back to top](#top)

**Q:** What do you log, and for how long?

**Say:**
- The app logs logins, failed logins, lockouts, new devices, and every refused request, with user, time, action and IP.
- Logs go to AWS CloudWatch and are kept 365 days.
- CloudTrail logs every AWS action, in all regions, with tamper-detection switched on.
- Passwords, tokens and personal data are never logged.

**Show:**
1. Log groups tab → `/ecs/riverly-api-prod` → **Retention: 12 months**
2. CloudTrail tab → **riverly-audit-trail**. Point at: **Multi-region: Yes**, **Log file validation: Enabled**
3. Live logs (optional): CloudWatch → **Log Analytics** → log group `/ecs/riverly-api-prod` → paste:
```
fields @timestamp, @message
| filter @message like "SECURITY"
| sort @timestamp desc
| limit 20
```

---

<a id="c816"></a>

## 8.16 Monitoring

[↑ Back to top](#top)

**Q:** How do you detect and respond to attacks?

**Say:** GuardDuty watches the account for threats. We have 15 alarms, including spikes in refused requests, login lockout clusters, and critical security events. Alerts email the engineering team straight away. There's also a security dashboard in the admin app.

**Show:**
1. Alarms tab → 15 alarms, all "OK"
2. SNS tab → **riverly-security-alerts** → Subscriptions → **Confirmed**
3. GuardDuty tab → **Findings**. See [GuardDuty explained](#guardduty) first.

---

<a id="c817"></a>

## 8.17 Clock sync

[↑ Back to top](#top)

**Q:** Are server clocks synchronised?

**Say:** Yes. AWS keeps all our services in sync automatically with the Amazon Time Sync Service. Logs are recorded in UTC.

---

<a id="c818"></a>

## 8.18 / 8.19 Admin tools and software installs

[↑ Back to top](#top)

**Q:** Who can run admin tools or install software on production?

**Say:** Nobody installs software on production by hand. The app runs as a container image built by our pipeline, and every deploy replaces it completely. The only server we have is the bastion, reached through AWS Systems Manager with MFA. It has no SSH and no open ports.

**Show:** Security Groups tab → **riverly-bastion-prod-sg** → **Inbound rules: none**.

---

<a id="c820"></a>

## 8.20–8.22 Network security

[↑ Back to top](#top)

**Q:** How is the network secured and segregated?

**Say:**
- Only the load balancer is open to the internet, and only on HTTPS. HTTP is redirected to HTTPS.
- The app only accepts traffic from the load balancer.
- The database only accepts the app and the bastion.
- Redis only accepts the app.
- Production and staging have separate databases, caches and firewalls.

**Show:**
1. Security Groups tab
2. **riverly-db-prod-sg** → Inbound: port 5432 from the app and bastion groups only
3. **riverly-api-prod-sg** → Inbound: port 80 from the load balancer group only
4. Load Balancers tab → **riverly-api-prod-alb** → **Listeners**: 80 = redirect to HTTPS, 443 = HTTPS

---

<a id="c823"></a>

## 8.23 Web filtering

[↑ Back to top](#top)

**Q:** Do you filter staff web access?

**Say:** Not a backend control. HR/IT or Femi to answer.

---

<a id="c824"></a>

## 8.24 Cryptography

[↑ Back to top](#top)

**Q:** How do you encrypt data?

**Say:**
- **Database:** encrypted with AWS KMS, including backups.
- **Files (S3):** AES-256.
- **Customer BVN:** encrypted again inside the app with AES-256-GCM.
- **In transit:** TLS 1.2 and 1.3 only.
- **Certificates:** AWS Certificate Manager, which renews them automatically.
- **Passwords, PINs, OTPs:** bcrypt.
- **Secrets:** AWS Secrets Manager.

This matches the Cryptography Policy updates.

**Show:**
1. RDS tab → **Configuration** → **Encryption: Enabled**
2. Load Balancers → riverly-api-prod-alb → Listeners → HTTPS:443 → security policy `ELBSecurityPolicy-TLS13-1-2-2021-06`
3. Certificate Manager tab → api.riverly.ng → **Issued**, **Renewal: Eligible**
4. Secrets Manager tab → list only

**Honest gap:** the Redis cache isn't encrypted yet. See [known gaps](#gaps).

---

<a id="c825"></a>

## 8.25–8.27 Secure development

[↑ Back to top](#top)

**Q:** How is security built into development?

**Say:** We follow the Riverly Secure Code Standard, based on the OWASP Top 10. Work happens on branches and goes in through pull requests. Changes are tested on staging before production. We tested the whole backend against OWASP Top 10 (2025) and fixed what we found.

**Show:**
1. GitHub → Pull requests (merged): PR #295, the OWASP security fixes
2. The OWASP report PDF

---

<a id="c828"></a>

## 8.28 Secure coding

[↑ Back to top](#top)

**Q:** How do you make sure code is secure?

**Say:**
- All database queries are parameterised. No query is built from user input. We checked all 20 raw-SQL sites.
- Error messages are generic.
- Security headers are sent on every response.
- Access is denied by default.

**Show (code):**
- **Cmd+P** → `GlobalExceptionHandler.cs`: generic errors
- **Cmd+P** → `SecurityHeadersMiddleware.cs`: security headers
- OWASP screenshot **E-13**: injection check, 0 unsafe

---

<a id="c829"></a>

## 8.29 Security testing

[↑ Back to top](#top)

**Q:** How do you test security?

**Say:** 125 automated tests, including security tests (for example, that tampered encrypted data is rejected). Plus the OWASP Top 10 assessment with live testing on staging and production. No external penetration test yet.

**Show (if asked):** Terminal:
```
cd ~/Desktop/riverly-api && dotnet test riverly.sln --nologo
```
Last line should show **Failed: 0, Passed: 95, Skipped: 30, Total: 125**. Or show OWASP screenshot **E-12**.

---

<a id="c830"></a>

## 8.30 Outsourced development

[↑ Back to top](#top)

**Q:** Development is done by Fluxus. How is that controlled?

**Say:** Fluxus works inside Riverly's own GitHub organisation and Riverly's AWS account, so Riverly owns the code and the infrastructure. Access is per named person with MFA on AWS. The contract side is for Femi.

---

<a id="c831"></a>

## 8.31 Separate environments

[↑ Back to top](#top)

**Q:** Are development, test and production separate?

**Say:** Yes. Staging and production have separate databases, caches, load balancers, secrets and logs. Staging runs only in working hours and switches off automatically at night.

**Show:**
1. RDS → two databases: riverly-prod-db and riverly-staging-db
2. Search bar → **EventBridge** → **Rules** → `riverly-staging-start` and `riverly-staging-stop`

---

<a id="c832"></a>

## 8.32 Change management

[↑ Back to top](#top)

**Q:** How do changes reach production?

**Say:**
1. The change goes in through a pull request.
2. Merging deploys to staging automatically.
3. We test on staging.
4. Production is a separate, manual deploy of that exact tested version. It isn't rebuilt.
5. A database snapshot is taken before each production deploy.
6. GitHub Actions deploys with short-lived credentials (OIDC), so no AWS keys are stored in GitHub.

**Show:**
1. GitHub → **Actions** → **Deploy to Production** → a run → shows the commit it deployed
2. RDS → Snapshots → the `predeploy` snapshots

**Honest gap:** PRs aren't independently reviewed yet. I merge my own with Femi's approval. See [known gaps](#gaps).

---

<a id="c833"></a>

## 8.33 Test data

[↑ Back to top](#top)

**Q:** Do you use real customer data for testing?

**Say:** Automated tests use made-up data, never customer data. Staging has its own separate database.

---

<a id="c834"></a>

## 8.34 Audit testing

[↑ Back to top](#top)

**Q:** How do you protect systems during audits like this?

**Say:** Today I'm showing read-only screens. Nothing is being changed. Auditors don't get their own login, and I control the screen.

---

<a id="guardduty"></a>

## GuardDuty findings, explained

[↑ Back to top](#top)

There are **26 open findings**. None is an active attack.

**1. HIGH x1: "anomalous behaviour" by riverly-staging-scheduler-role (31 Aug)**
**Say:** That's our own automation. It switches staging off at night to save cost. Stopping services looks like an attack pattern to GuardDuty. We reviewed it, and it's expected.

**2. MEDIUM x24: malicious IPs probing the staging database (last seen 25 Aug)**
**Say:** Until late August the staging database was reachable from the internet. GuardDuty caught bots probing it. Every login attempt failed. We then made it private, and there have been no probes since.
This is a good example of detection working, then a fix.

**3. LOW x1: root account login**
**Say:** The root account is used occasionally, always with MFA. See [known gaps](#gaps) item 10.

---

<a id="gaps"></a>

## Known gaps, honest answers

[↑ Back to top](#top)

Only raise these if asked. Give the honest answer, then the plan.

1. **No required PR review.** I merge my own PRs with Femi's approval. Plan: a second reviewer.
2. **No branch protection.** Needs the paid GitHub plan.
3. **GitHub 2FA not enforced** across the organisation. The free plan allows it; an owner (Femi) can switch it on.
4. **Members can create public repos** in the organisation. An owner can turn this off.
5. **Infrastructure changes are manual.** CloudTrail logs every one. Plan: infrastructure as code.
6. **Database is single-zone.** Restore tested at about 6.5 min. Plan: Multi-AZ.
7. **Redis cache not encrypted.** It's private, and only the app can reach it. Plan: encrypted cluster.
8. **No penetration test, no SAST/DAST tools.** Plan: external pen test.
9. **Container image scanning is off (ECR).** Plan: turn on scan-on-push.
10. **Root account used about weekly, always with MFA.** Know who uses it before the session. Ask Femi today.
11. **Both engineers have full AWS admin.** Small team, all logged. Plan: narrower roles.
12. **Staging app can be reached directly from the internet** (bypassing the load balancer). Staging only. Plan: close it.
13. **Two staging secrets are plain settings**, not in Secrets Manager. Production is correct.
14. **26 GuardDuty findings not yet archived.** All reviewed and explained above.
15. **.NET 8 support ends November 2026.** Upgrade planned.

---

<a id="dontknow"></a>

## If you don't know an answer

[↑ Back to top](#top)

**Say:** "I don't want to guess. Let me confirm and send it to you after the session."

Then write it down and follow up. Never guess in an audit.

[↑ Back to top](#top)
