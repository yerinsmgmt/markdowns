<a id="top"></a>

# External Audit — Backend Guide

**ISO/IEC 27001:2022 certification audit by TNV**
**Mon 19 – Thu 22 October 2026**
Lead auditor: Adebayo Akinlabi
Also: Oluwaseun Adekoya, Olumide Owolabi

All facts checked live on 19 Oct 2026.

**Your sessions:**
- **Tue 20 Oct**, 11:30–1:00 and 2:00–4:00: A.5 organisational controls (access, cloud, incidents, continuity). You may be called.
- **Wed 21 Oct**, 10:00–11:00: A.8.1–A.8.15. **Your main day.**
- **Wed 21 Oct**, 12:30–1:00 and 2:00–3:30: A.8.16–A.8.34
- **Thu 22 Oct**, 2:00–2:30: close-out meeting

Every "Show" has two ways: **AWS console** (click), or **Terminal** (paste one command). Use Terminal if the console is slow or you can't find the page. All Terminal commands are read-only: they look, they never change anything.

---

## Contents

**Setup**
- [1. Before each session](#setup)
- [2. Rules while sharing your screen](#rules)
- [3. Numbers to know](#numbers)
- [4. What the backend uses](#stack)
- [5. What we fixed since the internal audit](#fixed)

**Tuesday: A.5 organisational controls**
- [5.15–5.18 Access control and identities](#a515)
- [5.19–5.22 Suppliers](#a519)
- [5.23 Cloud services](#a523)
- [5.24–5.28 Incident management](#a524)
- [5.29–5.30 Business continuity](#a529)
- [5.33–5.34 Records and personal data](#a533)
- [5.37 Written procedures](#a537)

**Wednesday morning: A.8.1–A.8.15**
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

**Wednesday afternoon: A.8.16–A.8.34**
- [8.16 Monitoring](#c816)
- [8.17 Clock sync](#c817)
- [8.18 / 8.19 Admin tools, software installs](#c818)
- [8.20–8.22 Network security](#c820)
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

## 1. Before each session

[↑ Back to top](#top)

**30 minutes before:**

1. Log in to AWS: `https://132597214585.signin.aws.amazon.com/console`, user **YERINS**, with your MFA code.
2. Top right must say **Europe (Stockholm)**.
3. Log in to GitHub as **Yerinsfluxus**.
4. Log in to Cloudflare, and switch to **Info@riverly.ng's Account** (top left).
5. Open VS Code on the `riverly-api` folder.
6. Check that Terminal can reach AWS. Paste this:

```
aws sts get-caller-identity --profile riverly-live --query Arn --output text
```

It should print `arn:aws:iam::132597214585:user/YERINS`. If it errors, use the console only.

7. Open all the pages as tabs at once. Paste into Terminal:

```
open "https://console.aws.amazon.com/iam/home#/users" "https://eu-north-1.console.aws.amazon.com/rds/home?region=eu-north-1#database:id=riverly-prod-db;is-cluster=false" "https://eu-north-1.console.aws.amazon.com/cloudwatch/home?region=eu-north-1#alarmsV2:" "https://eu-north-1.console.aws.amazon.com/cloudwatch/home?region=eu-north-1#logsV2:log-groups" "https://eu-north-1.console.aws.amazon.com/guardduty/home?region=eu-north-1#/summary" "https://eu-north-1.console.aws.amazon.com/cloudtrail/home?region=eu-north-1#/trails" "https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#SecurityGroups:" "https://eu-north-1.console.aws.amazon.com/acm/home?region=eu-north-1#/certificates/list" "https://dash.cloudflare.com/b8ef98d67e4641a5d6a4c45037153f5a/riverly.ng/dns/records" "https://github.com/DRPFL-RIVERLY/riverly_backend/pulls?q=is%3Apr+is%3Amerged"
```

8. Have these open in Finder:
   - `Desktop/Riverly_OWASP_Assessment/` (OWASP report and screenshots)
   - `Downloads/Backup_Restoration_Test_Report_2026-09-11.pdf`
   - `Downloads/riverly-system-network.drawio.pdf` (system diagram)
   - `Desktop/cloudflare-dns.png` and `Desktop/cloudflare-analytics.png`
9. Close email, WhatsApp and unrelated tabs.

---

<a id="rules"></a>

## 2. Rules while sharing your screen

[↑ Back to top](#top)

- **You click, they watch.** Never hand over control.
- **Never open a secret's value.** In Secrets Manager, show the list only.
- **Never show customer data.** Show settings, not database rows.
- **Never open IAM "Security credentials".** It shows access keys.
- **Say it before you click it.**
- **Answer what's asked.** Don't volunteer extra problems.

---

<a id="numbers"></a>

## 3. Numbers to know

[↑ Back to top](#top)

- **AWS account:** 132597214585, region eu-north-1 (Stockholm)
- **AWS console users:** 2 (YERINS, Fatai), both with MFA. Root also has MFA.
- **Service accounts:** 2, no console access
- **Backups:** daily at 02:00 UTC, kept **14 days**, plus a snapshot before every production deploy
- **Restore time (tested):** about **6.5 minutes**
- **Production logs kept:** **365 days**
- **Alarms:** **15**, all OK
- **Customer login lockout:** 5 wrong tries, locked for up to **30 min**
- **Admin login lockout:** 5 wrong tries, locked for **15 min**
- **Session:** token **5 min**, logs out after **15 min** idle, **12 h** maximum
- **TLS:** **1.2 and 1.3 only**
- **Automated tests:** **225** (187 run every time, 38 need a database, 0 failing)
- **Raw SQL sites:** 39, all parameterised, **0 unsafe**

---

<a id="stack"></a>

## 4. What the backend uses

[↑ Back to top](#top)

**Application**
- .NET 8 API, one application for Personal, SME and Corporate
- PostgreSQL database (Amazon RDS), Redis cache (Amazon ElastiCache)

**In front of everything**
- **Cloudflare:** firewall, attack blocking and flood protection for the API, website and admin dashboard

**AWS**
- ECS Fargate (runs the app), Application Load Balancer, RDS, ElastiCache, S3, ECR
- Secrets Manager, KMS, Certificate Manager
- CloudWatch, CloudTrail, GuardDuty, SNS, EventBridge
- One EC2 bastion (database access only), reached through Systems Manager
- IAM, VPC

**Elsewhere**
- **Vercel:** hosts the website, admin dashboard and corporate web app
- **GitHub (DRPFL-RIVERLY):** code, gitleaks, Dependabot, deploys via GitHub Actions with OIDC

**Third parties that handle data**
- Providus / XpressWallet (wallets), Anchor (SME accounts), Dojah (identity checks), Sendchamp (SMS/WhatsApp OTP), Resend / SendGrid (email), Firebase (push), Flutterwave (bills, not live yet)

---

<a id="fixed"></a>

## 5. What we fixed since the internal audit

[↑ Back to top](#top)

The auditors check what was done about the internal audit's findings. These are done, and verified live:

- **Web firewall (was "no WAF"):** Cloudflare now sits in front of the API, website and admin dashboard. It blocks hacking probes and floods, and forces HTTPS with TLS 1.2 minimum.
- **Cloudflare can't be bypassed:** both AWS load balancers only accept Cloudflare's addresses.
- **Staging can't be reached directly (was a gap):** the staging app only accepts its load balancer now.
- **Real caller IP can't be faked:** an attacker could previously fake their IP to dodge login limits. Fixed and verified on production.
- **New High-severity library advisories:** two crypto packages, patched and pinned (see 8.8).
- **Antimalware confirmed:** GuardDuty malware scanning is on.
- **Cryptography Policy:** updated to match what we actually use.

---

<a id="a515"></a>

## 5.15–5.18 Access control and identities

[↑ Back to top](#top)

**Q:** How do you control who can access systems?

**Say:** Every person has their own named login; nothing is shared. AWS has two engineer logins, both with MFA, and the root account has MFA too. Service accounts only have the permissions their job needs, and can't log in to the console. The admin dashboard uses named logins with roles, so every approval traces to a person. Customers' passwords and PINs are stored as bcrypt hashes.

**Show:** see [8.2](#c82) and [8.5](#c85).

---

<a id="a519"></a>

## 5.19–5.22 Suppliers

[↑ Back to top](#top)

**Q:** Which suppliers handle your data, and how is that secured?

**Say:** On the technical side, every supplier is reached only over HTTPS, and their keys are kept in AWS Secrets Manager, never in code. Incoming messages from payment and identity providers are checked for a valid signature before we accept them. Supplier contracts and evaluations are Femi's.

The list is in [section 4](#stack).

---

<a id="a523"></a>

## 5.23 Cloud services

[↑ Back to top](#top)

**Q:** How do you manage security of your cloud services?

**Say:** We run on AWS in Stockholm. Under AWS's shared responsibility model, AWS secures the data centres and hardware, and we secure our configuration: access, encryption, network rules and monitoring. AWS is itself ISO 27001 certified. Cloudflare protects our public addresses, and Vercel hosts the websites.

**Show AWS's ISO certificate:**
1. Search bar: **Artifact**, then click **AWS Artifact**
2. **Reports**, then search **ISO 27001**

---

<a id="a524"></a>

## 5.24–5.28 Incident management

[↑ Back to top](#top)

**Q:** How do you detect and handle incidents?

**Say:** We detect them through GuardDuty, 15 alarms and Cloudflare. Alerts email the engineering team. We contain first, then find the cause, fix it, verify the fix, and record what happened.

**Real examples, if asked:**

**1. Duplicate bank-transfer payments, 6–8 Oct 2026**
- A slow payment provider plus automatic retries in the Personal app caused some transfers to pay out more than once.
- **Contained the same day:** we switched off only that one endpoint at the load balancer. Everything else kept working.
- **Fixed:** payments are now reserved before sending, and a reconciliation job checks every one against the provider.
- **Verified** on staging, released to production on 8 Oct, then the endpoint was switched back on.
- Only if asked about impact: it affected staff test accounts. Details are with Fatai and Femi.

**2. Attackers probing the staging database, August 2026**
- GuardDuty detected known-malicious IPs probing the staging database. Every login attempt failed.
- **Fixed:** the database was made private. No probes since.

**3. Hacking probe blocked, 17 Oct 2026**
- An outside IP probed our site for a secrets file (`/.env`). **Cloudflare blocked it.**

---

<a id="a529"></a>

## 5.29–5.30 Business continuity

[↑ Back to top](#top)

**Q:** How would you recover from an outage?

**Say:** The database is backed up daily, kept 14 days, and can be restored to any point within about 5 minutes. A snapshot is also taken before every production release. We've tested a full restore twice, in September: about 6.5 minutes, with all data intact. The app itself is rebuilt from code in minutes.

**Show:** the backup restoration test report, then [8.13](#c813).

**Gap, only if asked:** the database is in one zone. See [8.14](#c814).

---

<a id="a533"></a>

## 5.33–5.34 Records and personal data

[↑ Back to top](#top)

**Q:** How do you protect personal data?

**Say:** It's encrypted at rest and in transit. BVN is encrypted again inside the app, NIN is stored only as a hash, and passwords are hashed. Admin screens and logs mask personal data. Records have audit trails, and every AWS change is logged in CloudTrail. The legal side (NDPA) is Femi's.

**Show:** see [8.11](#c811) and [8.24](#c824).

---

<a id="a537"></a>

## 5.37 Written procedures

[↑ Back to top](#top)

**Q:** Are your operating procedures written down?

**Say:** Yes. Technical procedures are in the code repository, under version control:
- `docs/database-access.md`: how engineers reach the database
- `docs/production-rollout-plan.md`: how releases go to production
- `docs/security-hardening-backlog.md`: open security work

The deploy steps themselves are written as code in GitHub Actions.

---

<a id="c81"></a>

## 8.1 Staff laptops

[↑ Back to top](#top)

**Say:** Not a backend control. HR/IT or Femi.

---

<a id="c82"></a>

## 8.2 Privileged access

[↑ Back to top](#top)

**Q:** Who has admin access to AWS?

**Say:** Two engineers, me and Fatai, both with MFA. The root account also has MFA. Service accounts only have the permissions their job needs, and can't log in to the console.

**Show, AWS console:**
1. Search bar: **IAM** → left menu **Users**
2. Point at the **MFA** column

**Show, Terminal:**
```
aws iam list-users --profile riverly-live --query 'Users[].UserName' --output text | tr '\t' '\n' | while read u; do echo "$u   MFA devices: $(aws iam list-mfa-devices --profile riverly-live --user-name $u --query 'length(MFADevices)' --output text)"; done; echo "Root account MFA on: $(aws iam get-account-summary --profile riverly-live --query 'SummaryMap.AccountMFAEnabled' --output text)"
```
You'll see both engineers with 1 MFA device, and "Root account MFA on: 1".

**If asked "why do both engineers have full admin?":** small team, every action logged in CloudTrail. Narrowing it is on our improvement list.

---

<a id="c83"></a>

## 8.3 Access to data

[↑ Back to top](#top)

**Q:** How do you stop one customer seeing another's data?

**Say:** Every request is checked on the server, and the app denies by default: an endpoint is locked unless it's deliberately public. Every query filters by the logged-in customer's own ID.

**Show (code):** VS Code → **Cmd+P** → `Program.cs` → search `FallbackPolicy`: "this locks every endpoint by default".

**Q:** Can staff read customer data in the database?

**Say:** The database is private, with no internet access. The only way in is through the bastion, with AWS login and MFA. Admin screens mask personal data.

---

<a id="c84"></a>

## 8.4 Access to source code

[↑ Back to top](#top)

**Say:** All repos are private, in Riverly's own GitHub organisation, with access per named person.

**Show, Terminal:**
```
gh api repos/DRPFL-RIVERLY/riverly_backend/collaborators --jq '.[] | "\(.login): \(.role_name)"'
```
Today: Femi-fluxx and Yerinsfluxus are admin, fatai-sanni maintain, oltoch and thesarahoba read-only.

**Gaps, only if asked:** no branch protection, and GitHub 2FA isn't enforced across the organisation. See [gaps](#gaps).

---

<a id="c85"></a>

## 8.5 Login security

[↑ Back to top](#top)

**Q:** How is customer login protected?

**Say:**
- Passwords and PINs stored as bcrypt hashes
- 5 wrong tries locks the account
- Two layers of rate limiting: Cloudflare, plus the app's own limit per IP address. The IP can't be faked.
- A new device must be verified with a one-time code
- Sessions end after 15 minutes idle, and after 12 hours maximum

**Show, Terminal (staging, weekdays 6am–10pm):**
```
for i in $(seq 1 14); do printf "%s " $(curl -s -o /dev/null -w "%{http_code}" -X POST -H "Content-Type: application/json" -d '{}' https://api-staging.riverly.ng/api/v1/identity/login); done; echo
```
**Say:** "Ten requests go through, then 429: blocked."

---

<a id="c86"></a>

## 8.6 Capacity

[↑ Back to top](#top)

**Say:** We have alarms for high CPU, high memory, database connections, low database storage and unhealthy servers.

**Show:** see the alarm list in [8.16](#c816).

**Only if asked:** we run one app container, scaled up by hand. The alarms warn us first.

---

<a id="c87"></a>

## 8.7 Malware

[↑ Back to top](#top)

**Say:** We use AWS GuardDuty, with malware protection on. It scans our server automatically if suspicious activity is detected, and watches the whole account. The app runs in short-lived containers rebuilt on every deploy, and nobody logs into them. Laptop antivirus is HR/IT.

**Show, AWS console:** **GuardDuty** → left menu **Protection plans** → **Malware Protection for EC2** → **Enabled**. (If there's no "Protection plans", click **Malware Protection**.)

**Show, Terminal:**
```
aws guardduty get-detector --profile riverly-live --region eu-north-1 --detector-id $(aws guardduty list-detectors --profile riverly-live --region eu-north-1 --query 'DetectorIds[0]' --output text) --query '{ThreatDetection:Status,MalwareScanning:Features[?Name==`EBS_MALWARE_PROTECTION`].Status|[0]}' --output table
```
Both say **ENABLED**.

**Not enabled, only if asked:** scanning of uploaded files, container monitoring, image scanning.

---

<a id="c88"></a>

## 8.8 Vulnerabilities

[↑ Back to top](#top)

**Say:**
- Dependabot checks our libraries weekly against public vulnerability databases.
- gitleaks scans every pull request for leaked secrets.
- We tested the backend against the OWASP Top 10 (2025): 9 issues found, 8 fixed.
- When two new High advisories appeared in crypto libraries, we patched them.

**Show, Terminal (scans the code on this Mac):**
```
cd ~/Desktop/riverly-api && dotnet list riverly.sln package --vulnerable --include-transitive 2>&1 | grep -E "vulnerable packages"
```
Every line should say **"has no vulnerable packages"**.

**Only true once the crypto fix is merged.** Until then, this shows two packages. If so, say: "Two new advisories came out this month. They're patched, and the patch is being released."

**Also show:** the OWASP report, `Desktop/Riverly_OWASP_Assessment/`.

---

<a id="c89"></a>

## 8.9 Configuration

[↑ Back to top](#top)

**Say:** App settings are version-controlled with the code. Secrets are in AWS Secrets Manager, never in code. Every AWS change is recorded in CloudTrail, with who made it and when.

**Show, Terminal (names only, never values):**
```
aws secretsmanager list-secrets --profile riverly-live --region eu-north-1 --query 'SecretList[].{Secret:Name}' --output table
```

**Gap, only if asked:** infrastructure isn't written as code yet (no Terraform). Changes are manual, but every one is logged.

---

<a id="c810"></a>

## 8.10 Data deletion

[↑ Back to top](#top)

**Say:** The app has admin tools to remove a customer's records. A formal retention and deletion schedule is a policy decision for Femi.

---

<a id="c811"></a>

## 8.11 Data masking

[↑ Back to top](#top)

**Say:** Personal data is masked in three places: admin screens, logs, and dedicated masked database views for analysis. NIN is stored only as a hash, and BVN is encrypted.

**Show (code):** **Cmd+P** → `PiiMask.cs`, `LogRedactor.cs`, `MaskedViewsSql.cs`

---

<a id="c812"></a>

## 8.12 Data leakage

[↑ Back to top](#top)

**Say:** Storage can't be made public, the database isn't reachable from the internet, logs strip personal data, error messages reveal nothing internal, gitleaks catches secrets in code, and Cloudflare blocks attempts to grab secret files.

**Show, Terminal:**
```
aws s3api get-public-access-block --profile riverly-live --bucket riverly-prod-assets --query 'PublicAccessBlockConfiguration' --output table
```
All four lines say **True**.

---

<a id="c813"></a>

## 8.13 Backups

[↑ Back to top](#top)

**Say:** Daily automatic backups, kept 14 days, encrypted, plus a snapshot before every production release. Restore tested twice: about 6.5 minutes.

**Show, AWS console:** **RDS** → **riverly-prod-db** → **Maintenance & backups**

**Show, Terminal:**
```
aws rds describe-db-snapshots --profile riverly-live --region eu-north-1 --db-instance-identifier riverly-prod-db --query 'reverse(sort_by(DBSnapshots,&SnapshotCreateTime))[:6].{Snapshot:DBSnapshotIdentifier,Taken:SnapshotCreateTime,Encrypted:Encrypted}' --output table
```
Daily snapshots, plus `predeploy` ones, all **Encrypted: True**.

Then open the backup restoration test report.

---

<a id="c814"></a>

## 8.14 Redundancy

[↑ Back to top](#top)

**Say:** The load balancer runs across several zones. The database is in one zone today. If that zone failed, we'd restore from backup, which we've tested at about 6.5 minutes. Multi-AZ is on our improvement list.

**Show, Terminal:**
```
aws rds describe-db-instances --profile riverly-live --region eu-north-1 --db-instance-identifier riverly-prod-db --query 'DBInstances[0].{Encrypted:StorageEncrypted,BackupDays:BackupRetentionPeriod,DeletionProtection:DeletionProtection,PublicAccess:PubliclyAccessible,MultiAZ:MultiAZ}' --output table
```

---

<a id="c815"></a>

## 8.15 Logging

[↑ Back to top](#top)

**Say:** The app logs logins, failed logins, lockouts, new devices and every refused request, with user, time, action and real IP address. Logs are kept 365 days. CloudTrail records every AWS action, in all regions, with tamper detection on. Passwords and personal data are never logged.

**Show, Terminal:**
```
aws logs describe-log-groups --profile riverly-live --region eu-north-1 --log-group-name-prefix /ecs/riverly-api --query 'logGroups[].{LogGroup:logGroupName,KeptDays:retentionInDays}' --output table; aws cloudtrail describe-trails --profile riverly-live --region eu-north-1 --query 'trailList[].{Trail:Name,AllRegions:IsMultiRegionTrail,TamperCheck:LogFileValidationEnabled}' --output table
```
Production: **365** days. CloudTrail: **AllRegions True, TamperCheck True**.

---

<a id="c816"></a>

## 8.16 Monitoring

[↑ Back to top](#top)

**Say:** GuardDuty watches for threats, 15 alarms cover security and operations, and Cloudflare shows every blocked attack. Alerts email the engineering team straight away.

**Show, Terminal:**
```
aws cloudwatch describe-alarms --profile riverly-live --region eu-north-1 --query 'MetricAlarms[].{Alarm:AlarmName,State:StateValue}' --output table
```
15 alarms, all **OK**.

**Also show:** `Desktop/cloudflare-analytics.png` (128 requests blocked by Cloudflare in 24 hours).

**Before opening GuardDuty findings:** read [GuardDuty explained](#guardduty).

---

<a id="c817"></a>

## 8.17 Clock sync

[↑ Back to top](#top)

**Say:** AWS syncs all our services to the Amazon Time Sync Service. Logs are in UTC.

**Show, Terminal (logs into the bastion read-only and prints its clock status):**
```
aws ssm start-session --profile riverly-live --region eu-north-1 --target i-01b8d2a01568dec17 --document-name AWS-StartInteractiveCommand --parameters command="chronyc tracking"
```
Point at **Reference ID (169.254.169.123)**, which is Amazon's time source, and **System time**, which is off by less than a microsecond.

---

<a id="c818"></a>

## 8.18 / 8.19 Admin tools and software installs

[↑ Back to top](#top)

**Say:** Nobody installs software on production by hand. Every deploy replaces the app container completely. The only server is the bastion, reached through AWS Systems Manager with MFA. It has no open ports.

**Show:** see the firewall table in [8.20](#c820). The bastion shows no port.

---

<a id="c820"></a>

## 8.20–8.22 Network security

[↑ Back to top](#top)

**Q:** How is the network secured and separated?

**Say:**
- All public traffic goes through Cloudflare first. It blocks attacks and forces HTTPS.
- The AWS load balancer only accepts Cloudflare, so nobody can go around it.
- The app only accepts the load balancer. The database only accepts the app and the bastion. Redis only accepts the app.
- The bastion has no open ports.
- Production and staging have separate network rules, databases and caches.

**Show, Terminal (firewalls):**
```
aws ec2 describe-security-groups --profile riverly-live --region eu-north-1 --group-ids sg-02e1fd628fb3ee742 sg-052c62c4455a0cb5e sg-08f1271c75ea53b84 sg-0d40b9e41b06fca30 sg-020e6ba2051be6bdd --query 'SecurityGroups[].{Firewall:GroupName,Port:IpPermissions[0].FromPort,OpenToWholeInternet:length(IpPermissions[].IpRanges[?CidrIp==`0.0.0.0/0`][])}' --output table
```
**OpenToWholeInternet: 0** on every one.

**Show, Terminal (live proof):**
```
for v in 1.0 1.1 1.2; do c=$(curl -s -o /dev/null -w "%{http_code}" --tlsv$v --tls-max $v https://api.riverly.ng/health); [ "$c" = "200" ] && echo "TLS $v: ACCEPTED" || echo "TLS $v: REFUSED"; done; echo "Hacking probe via Cloudflare: $(curl -s -o /dev/null -w '%{http_code}' https://api.riverly.ng/.env) (403 = blocked)"; echo "Direct to AWS, skipping Cloudflare: $(curl -s -o /dev/null -w '%{http_code}' --max-time 8 https://riverly-api-prod-alb-745790027.eu-north-1.elb.amazonaws.com/health) (000 = blocked)"
```
You'll see TLS 1.0 and 1.1 refused, 1.2 accepted, the probe blocked (403), and going around Cloudflare blocked (000).

**Also show:** `Desktop/cloudflare-dns.png` (orange "Proxied" next to api, www, admin).

---

<a id="c823"></a>

## 8.23 Web filtering

[↑ Back to top](#top)

**Say:** Filtering of staff web browsing sits with HR/IT. For our own websites and API, Cloudflare filters incoming traffic and blocks known attacks.

---

<a id="c824"></a>

## 8.24 Cryptography

[↑ Back to top](#top)

**Say:**
- **In transit:** TLS 1.2 and 1.3 only, at Cloudflare and AWS. Cloudflare checks AWS's certificate on every connection. The database forces encrypted connections.
- **At rest:** the database, backups and files are AES-256, with AWS KMS.
- **Inside the app:** BVN is encrypted again (AES-256-GCM), NIN is hashed, and passwords and PINs use bcrypt.
- **Certificates:** AWS Certificate Manager renews automatically.

This matches the updated Cryptography Policy.

**Show, Terminal:**
```
aws acm list-certificates --profile riverly-live --region eu-north-1 --query 'CertificateSummaryList[?InUse].{Domain:DomainName,Status:Status,AutoRenew:RenewalEligibility,Expires:NotAfter}' --output table; aws rds describe-db-instances --profile riverly-live --region eu-north-1 --query 'DBInstances[].{Database:DBInstanceIdentifier,Encrypted:StorageEncrypted}' --output table
```

**Gaps, only if asked:** the Redis cache and the bastion's disk aren't encrypted. Neither holds customer records. See [gaps](#gaps).

---

<a id="c825"></a>

## 8.25–8.27 Secure development

[↑ Back to top](#top)

**Say:** We follow the Riverly Secure Code Standard, based on the OWASP Top 10. Work goes in through pull requests, is tested on staging, then released to production. We tested the whole backend against OWASP Top 10 (2025) and fixed what we found.

**Show:** GitHub → merged pull requests → **#295** (OWASP fixes), **#329** (real-IP fix). Then the OWASP report.

---

<a id="c828"></a>

## 8.28 Secure coding

[↑ Back to top](#top)

**Say:** All database queries are parameterised, error messages are generic, security headers are on every response, and access is denied by default.

**Show, Terminal:**
```
cd ~/Desktop/riverly-api && echo "Raw SQL sites (all parameterised): $(grep -rn --include='*.cs' -E 'FromSqlRaw|FromSqlInterpolated' src/ | wc -l | tr -d ' ')"; echo "String-built SQL: $(grep -rn --include='*.cs' -E 'FromSqlRaw\("[^"]*"\s*\+' src/ | wc -l | tr -d ' ')"; echo "Shell commands run by the app: $(grep -rn --include='*.cs' 'Process.Start' src/ | wc -l | tr -d ' ')"
```
**String-built SQL: 0**, **Shell commands: 0**.

---

<a id="c829"></a>

## 8.29 Security testing

[↑ Back to top](#top)

**Say:** 225 automated tests, including security tests, such as tampered encrypted data being rejected and faked IPs being ignored. Plus the OWASP Top 10 assessment with live testing. No external penetration test yet.

**Show, Terminal (takes about a minute):**
```
cd ~/Desktop/riverly-api && dotnet test riverly.sln --nologo 2>&1 | tail -3
```
Look for **Failed: 0**.

---

<a id="c830"></a>

## 8.30 Outsourced development

[↑ Back to top](#top)

**Say:** Fluxus builds and runs the platform inside Riverly's own GitHub organisation and Riverly's own AWS account, so Riverly owns the code and the infrastructure. Access is per named person, with MFA on AWS. The contract is Femi's.

---

<a id="c831"></a>

## 8.31 Separate environments

[↑ Back to top](#top)

**Say:** Staging and production have separate databases, caches, servers, load balancers, secrets and logs. Code reaches production only after it's been tested on staging. Staging switches itself off outside working hours.

**Show, Terminal:**
```
aws rds describe-db-instances --profile riverly-live --region eu-north-1 --query 'DBInstances[].{Database:DBInstanceIdentifier,Size:DBInstanceClass,Encrypted:StorageEncrypted}' --output table; aws events list-rules --profile riverly-live --region eu-north-1 --name-prefix riverly-staging --query 'Rules[].{Rule:Name,Schedule:ScheduleExpression}' --output table
```
Two separate databases, and the staging on/off schedule.

**Only if asked:** both environments are in the same AWS account, separated by resources and permissions. Don't say staging has no real customer data; confirm after the session.

---

<a id="c832"></a>

## 8.32 Change management

[↑ Back to top](#top)

**Say:** Every change goes through a pull request and deploys to staging automatically. We test there. Production is a separate, manual release of that exact tested version, not rebuilt. A database snapshot is taken before every release, and we can roll back to the previous version quickly.

**Show, Terminal:**
```
gh run list -R DRPFL-RIVERLY/riverly_backend --workflow deploy-production.yml --limit 5
```

**If they notice the 18 Oct release says "failure":** the release itself completed and production was healthy. Only the final check failed, because it tried to reach the server directly, which Cloudflare protection now blocks. We changed the check to go through Cloudflare (#330), and staging has passed with it since.

**Gaps, only if asked:** pull requests aren't independently reviewed yet (I merge my own, with Femi's approval), and there's no branch protection.

---

<a id="c833"></a>

## 8.33 Test data

[↑ Back to top](#top)

**Say:** Automated tests use made-up data, never customer data. Staging has its own separate database.

---

<a id="c834"></a>

## 8.34 Audit testing

[↑ Back to top](#top)

**Say:** I'm only showing read-only screens and commands today. Nothing is being changed, and I control the screen.

---

<a id="guardduty"></a>

## GuardDuty findings, explained

[↑ Back to top](#top)

There are **26 open findings**, none since September, and none is an active attack.

**HIGH x1: "anomalous behaviour" by riverly-staging-scheduler-role (31 Aug)**
**Say:** That's our own automation switching staging off at night. GuardDuty flags stopping services as an attack pattern. Reviewed: expected.

**MEDIUM x24: malicious IPs probing the staging database (last seen 25 Aug)**
**Say:** Staging's database was reachable from the internet then. GuardDuty caught bots probing it, and every login failed. We made it private, and there have been no probes since.

**LOW x1: root account login (last seen 30 Sep)**
**Say:** The root account is used rarely, always with MFA. See [gaps](#gaps) item 9.

---

<a id="gaps"></a>

## Known gaps, honest answers

[↑ Back to top](#top)

Only raise these if asked. Honest answer, then the plan.

1. **No independent pull request review.** I merge my own, with Femi's approval. Plan: a second reviewer.
2. **No branch protection.** Needs the paid GitHub plan.
3. **GitHub 2FA isn't enforced** across the organisation. It's free to switch on; an owner can do it.
4. **Infrastructure changes are manual,** but every one is logged in CloudTrail. Plan: infrastructure as code.
5. **Database in one zone.** Restore tested at about 6.5 min. Plan: Multi-AZ.
6. **Redis cache not encrypted.** It's private, and only the app can reach it. Plan: encrypted cluster.
7. **Bastion disk not encrypted.** It holds only the operating system, no customer data. Plan: replace with an encrypted one.
8. **No external penetration test, and no automated code-scanning tools (SAST/DAST).** Plan: external pen test.
9. **Root account used occasionally, always with MFA.** Last seen 30 Sep.
10. **Both engineers have full AWS admin.** Small team, all logged. Plan: narrower roles.
11. **An old supplier API key is still in git history** (from March). It's not the key we use now. We're confirming with the supplier that it's revoked.
12. **The corporate web app isn't behind Cloudflare yet,** because it doesn't have a riverly.ng address.
13. **Two staging secrets are plain settings** rather than in Secrets Manager. Production is correct.
14. **26 old GuardDuty findings aren't archived yet.** All reviewed and explained above.
15. **.NET 8 support ends in November 2026.** Upgrade planned.

---

<a id="dontknow"></a>

## If you don't know an answer

[↑ Back to top](#top)

**Say:** "I don't want to guess. Let me confirm and send it to you after the session."

Write it down, and follow up. Never guess in an audit.

[↑ Back to top](#top)
