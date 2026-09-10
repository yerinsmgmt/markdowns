# LinkedIn: click-by-click

Ordered by impact. If you stop after task 2 you will still have fixed most of it.

Everything in a fenced block is paste-ready. Do not retype it.

---

## TASK 1 — Headline (2 minutes, highest impact)

**Where:** Go to your profile. In the top card with your photo, click the small
**pencil icon** on the right. A window opens called **Edit intro**. The second
field down is **Headline**.

**Delete what is there.** Paste this:

```
Polymath: AI/Application Engineer & Medical Doctor | Agents, RAG, Evals | Production AI in fintech and health
```

109 characters, limit is 220.

**Why "Polymath" leads rather than being dropped or appended:** LinkedIn cuts
headlines off around 60 characters in search results and on mobile. What a
recruiter actually sees is `Polymath: AI/Application Engineer & Medical
Doctor | Agents,…` so the claim and both things that prove it all land inside
the visible window. Putting it at the end would have pushed it past the cut,
invisible in the one place it matters. And it stays the strong form: the word
appears, then pays for itself in the same breath.

**Why this one first:** the headline is the only text that appears in recruiter
search results, under your name in every connection request, and beside every
comment you leave. You had 2 search appearances in 7 days. That is this field.

While the same **Edit intro** window is open, also set:

- **Current position:** it will offer a dropdown once you finish Task 2. Come
  back and set it to Creovine.
- **Location:** set **Country/Region** to Nigeria if that is your legal work
  base, and put `Remote worldwide` in the **Location within this area** field.

Click **Save**.

---

## TASK 2 — Add Creovine (5 minutes, the biggest gap)

Creovine is not on your profile at all. Lira, Oystar and Brydg therefore do not
exist to a recruiter.

**Where:** scroll to the **Experience** section. Click the **+ (plus)** icon at
the top right of that section. Choose **Add position**.

Fill in exactly:

- **Title:** `Co-founder & Principal Engineer`
- **Employment type:** Full-time
- **Company:** `Creovine`
- **Start date:** January 2020 · **I am currently working in this role:** tick
- **Location:** Remote
- **Description:** paste the block below

```
Architect and primary engineer of a multi-product AI platform. Four live products run on one API I designed and still run: 155 service modules against a 46-model PostgreSQL schema on AWS, with tenants isolated by table prefix and product-scoped JWT claims.

Lira Intelligence (liraintelligence.com), AI support that answers from a company's own knowledge base and then acts across chat, email, voice and WhatsApp:

• Production RAG on Qdrant. Hybrid search combining vector kNN with keyword retrieval, ranked by source-authority precedence and filtered by knowledge-base segment. Degrades to keyword retrieval when the vector store is down rather than failing the turn.

• Agent tool-use architecture: a tool registry with per-organisation packs, plan gating, and a seven-tier risk model from read_public to human_only, plus maker-checker approval where the agent parks a privileged action, a second person authorises it out of band, and the tool executes server-side.

• An MCP gateway letting a customer connect their own remote tool server: off by default, KMS-backed credentials with OAuth refresh, SSRF protection through DNS resolution and private-IP blocking, per-tool rate limits and a full config audit trail.

• An LLM eval harness gating CI: golden datasets for retrieval, tool selection and groundedness, deterministic recall@k / nDCG / MRR scoring, LLM-as-judge for hallucination, and prompt-injection rows that fail the build above zero. Open sourced as evalgate.

• A realtime voice agent in Python on Pipecat with AWS Nova Sonic, and nine enterprise integration adapters including Salesforce, HubSpot, Slack and Teams.

Oystar (oystar.app), a specialist referral platform live in Rwandan hospitals. Carries a patient's full case from a frontline clinic to the right specialist and brings the clinical answer back, tracking six referral stages so a patient who never arrives is flagged rather than lost. FHIR-compatible, real authorisation, nothing mocked on the clinical path.

Brydg (brydg.app), AI-native hiring: applications, AI-assisted interview pipelines, scheduling, offers and analytics.

Creovine Academy (academy.creovine.com), teaching AI in real engineering work. 120+ people trained.

Stack: TypeScript, Fastify, Prisma, PostgreSQL, Python, Pipecat, Qdrant, DynamoDB, AWS, Next.js, React, Docker.
```

- **Skills:** LinkedIn will prompt you to add skills to this role. Add:
  `Artificial Intelligence (AI)`, `Large Language Models (LLM)`,
  `Retrieval-Augmented Generation (RAG)`, `TypeScript`, `Python`, `AWS`,
  `System Design`

Click **Save**.

---

## TASK 3 — Fix the Fluxus entry (3 minutes)

Your current bullets are generic and contain none of your evidence.

**Where:** Experience section, find **Senior Developer, FLUXUS NG**, click the
**pencil icon** on that entry.

- **Title:** change `Senior Developer` to `Senior Backend Engineer`
- **Description:** replace everything with:

```
Lead backend engineer on Riverly (riverly.ng), a .NET 8 core banking platform on clean architecture across Domain, Application, Infrastructure and API, serving personal, SME and corporate customers. Authored roughly 85% of the codebase across 600+ commits.

Production reliability over the 30 days to 9 September 2026: 2 server errors across 65,942 requests, p95 latency 284ms, p50 2ms, running on ECS with RDS PostgreSQL and CloudTrail auditing.

• Built roughly 40 API surfaces: onboarding, KYC and KYB, accounts, transfers, bill payments, fixed investments, reporting, and the admin plane for fee configuration, KYB review and security monitoring.

• Delivered corporate internet banking with org-scoped JWTs and a role-based maker/checker approval chain (Owner, Admin, Maker, Checker, Viewer) for authorising high-value transactions.

• Shipped an MCP controller and AI support endpoints into the live banking API, putting a governed AI agent inside a regulated financial product.

• Contributed to eight Go microservices covering gateway, auth, finops/wallet, marketplace, notification, validation and back office, with Eureka discovery, Kafka and Redis.

Stack: C#, .NET 8, Go, PostgreSQL, Redis, Kafka, Docker, AWS ECS and RDS, OpenAPI, Next.js.
```

Click **Save**.

---

## TASK 4 — Add LykLuk (2 minutes)

**Where:** Experience → **+** → **Add position**

- **Title:** `Frontend Engineer & Brand Marketing Lead`
- **Company:** `LykLuk`
- **Dates:** start 2025, end 2026, untick "currently working"
- **Location:** Remote

```
Flutter engineer on a live-shopping marketplace shipped to the App Store and Play Store: live streaming, end-to-end encrypted messaging, e-commerce and creator flows, wallet and payouts.

Built multi-currency checkout where FX is locked at order creation and settled at seller payout, integrating card, bank-transfer and USSD payments via Flutterwave alongside Apple and Google in-app purchase, and took the app through App Store review including IAP-compliance rework.

Stack: Flutter, Dart, hooks_riverpod, WebRTC, AWS MediaLive, Flutterwave.
```

---

## TASK 5 — Three corrections (5 minutes)

**5a. Giddle is listed as current.** You told me it closed. Leaving a shut-down
company as a present role is the kind of thing that unravels in a reference
check.

Experience → **Giddle** → pencil → untick **I am currently working in this
role** → set the real end date → Save.

**5b. Metart Africa, CEO, Nov 2019 to Present.** Only you know if this is still
true. If it is, leave it, it is honest. If it has wound down, give it an end
date. Do not remove a true entry just because it is off-message.

**5c. "Global Remote Engineering Collective, 2022 to 2024."** I flagged this in
my very first review. It reads as a placeholder, and it is now the only thing
covering 2022 to 2024.

Your call, and be honest with yourself about which:

- If those were **real named clients**, replace it with one or two entries under
  their actual names, even short ones.
- If it was **freelance and contract work**, rename the company to
  `Freelance / Contract` and use this description:

```
Backend, full-stack and blockchain contract work for startups and growing technology companies: REST APIs, payment integrations, authentication systems and cloud infrastructure, delivered across multiple engagements. Built the early versions of what later became the Creovine product line.
```

- If it was **neither**, delete it. A visible two-year gap is more defensible
  than an entry that cannot be verified.

---

## TASK 6 — About (3 minutes)

**Where:** scroll to **About**, click the **pencil icon**.

Delete everything and paste:

```
I build AI systems that take real actions in production, and the controls that make that safe. Two server errors across 65,942 requests on the banking platform I lead backend for, in the 30 days to September 2026.

Most of my work is agents that do more than answer: production RAG on Qdrant with hybrid retrieval and authority-ranked sources, tool-calling under a seven-tier risk model with maker-checker approval, an MCP gateway that lets a customer plug in their own tool server without handing it the keys, and an LLM eval harness that fails the build when safety metrics move at all.

That work runs across four live products on one API I designed and still run: 155 service modules against a 46-model PostgreSQL schema, on AWS.

I am also a medical doctor, six years of general medicine in Ukraine. That is not a detour. It is why I built Oystar, a referral platform now running in Rwandan hospitals that carries a patient's full case from a frontline clinic to the right specialist and brings the clinical answer back. The medicine tells me what has to be true. The engineering makes it true.

Outside all of it I draw, in pen and ink, at some scale. Work exhibited in Kyiv, Sumy, Lagos, Abuja and Dubai.

Open source: github.com/yerinsabraham/evalgate
Engineering write-ups: yerinsabraham.com/engineering

Open to senior AI and backend engineering roles. Remote worldwide, EOR or contract.
yerinssaibs@gmail.com
```

The first two lines are what shows before "see more", so the reliability figure
lands before anyone clicks.

**In the same window, find "Top skills"** and replace the current five. This is
the field that fixes your 2 search appearances:

```
Artificial Intelligence (AI)
Large Language Models (LLM)
Retrieval-Augmented Generation (RAG)
Backend Development
System Design
```

Note what leaves: Blockchain and Web3 drop out of the top five. They stay in
your full Skills list. In 2026 an NFT-forward profile reads as someone who
chased the last cycle, which is the opposite of the point.

---

## TASK 7 — Skills (5 minutes)

**Where:** scroll to **Skills**, click **+** to add. Add any missing:

```
Artificial Intelligence (AI)
Large Language Models (LLM)
Retrieval-Augmented Generation (RAG)
AI Agents
Prompt Engineering
Model Context Protocol (MCP)
Machine Learning Operations (MLOps)
TypeScript
Node.js
Python
C#
.NET
Go
PostgreSQL
Amazon Web Services (AWS)
Docker
System Design
API Design
Next.js
React
Flutter
Fintech
```

Then click the **pencil** on the Skills section and **reorder** so the first
three are AI, LLM and RAG. Only the top few show by default.

---

## TASK 8 — Featured (3 minutes)

Right now it shows a dating app launch, a blockchain post and a Brian Eno
quote. None of it is engineering.

**Where:** the **Featured** section → **+** → **Add a link**

Add these three:

```
https://yerinsabraham.com/engineering/mcp-gateway
https://github.com/yerinsabraham/evalgate
https://oystar.app
```

Then remove the Giddle and blockchain posts from Featured. They stay on your
profile as activity, they just stop being the first thing shown.

Keep your Oystar field-research post if you would rather feature four.

---

## TASK 9 — Open to work (2 minutes)

**Where:** the **Open to** button under your headline → **Edit** on the "Open to
work" card.

- **Job titles:** `AI Engineer`, `AI/Application Engineer`,
  `Senior Backend Engineer`, `Full Stack Engineer`, `Forward Deployed Engineer`
- **Locations:** add **Remote**, and keep the countries you already have
- **Start date:** Immediately
- **Visibility:** Recruiters only, which is what you already have. Correct while
  you are employed.

`Forward Deployed Engineer` is on that list deliberately. It is one of the
fastest-growing roles in AI right now and your profile fits it: agents, evals,
guardrails, enterprise integrations and a customer-facing deployment into a
bank.

---

## TASK 10 — Recommendations (10 minutes, do not skip)

You have none. Everything on your CV, site and GitHub is written by you. This
is the cheapest outside validation available to you anywhere.

**Where:** scroll to the very bottom of your profile → **Recommendations** →
**Ask for a recommendation**.

Ask three people, and tell each one what to write about. An open-ended ask
usually produces nothing:

1. Someone at **Fluxus NG**, on the banking platform and its reliability.
2. A **Creovine Academy** participant, on the teaching.
3. A **LykLuk** teammate, on shipping the app through App Store review.

Two or three specific recommendations do more than another month of polishing
the copy.

---

## Order if you are short on time

Task 1 and Task 2 are 7 minutes together and fix most of it.
Task 6 and Task 7 are the next 8 minutes.
Task 10 pays off slowest and matters most.
