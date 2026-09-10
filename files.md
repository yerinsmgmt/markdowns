# Batch 01, for review

**2026-09-10. 7 drafts. Nothing sent. Revised after review — see note below.**

Reply per item: **send** / **change X** / **hold**.

**Revision note, 10 September 2026.** The first version of every draft opened
on "I run the platform behind Lira Intelligence" — the product, not the
capability. Yerins caught it: this is a job application, not a pitch for
Creovine's products, and a reader hears "here is what I built for myself"
instead of "here is what I can build for you." Rewritten to lead with the
outcome and the capability; the product name now appears at most once,
quietly, or only in the signature link. Also removed em dashes throughout.
The rule is recorded in `CANDIDATE.md` and `METHOD.md` so it holds for every
batch after this one.

- **#1 AiMi** and **#6 CyberAtlas** are real emails. Gmail connector is
  connected and verified as `yerinssaibs@gmail.com` (`SENDER.md`).
- **#6 CyberAtlas** is still blocked until a query is run on
  cyberatlas.ai/finder — its posting requires the query and results in the
  email body.
- **#2 Axmed, #3 Mastra, #4 GitLab, #5 Oyster, #7 Mintlify** apply through a
  form (Teamtailor / Ashby / Greenhouse). The text below goes in the form's
  cover-letter / message field. Yerins submits these, or approves and I walk
  him through each form. CV: `cv/Yerins-Abraham-CV.pdf`.

Sender identity verified: **yes — `yerinssaibs@gmail.com`, confirmed 10 September 2026.**

---

## #1 AiMi — Full Stack AI Engineer

- **Channel:** email — `vishnu.swaroop@aimi.technology`
- **Remote:** Remote (Everywhere)
- **Why now:** live agentic platform for capital-markets ops; posting asks specifically for MCP connectors, agent evals, agent observability, and resilience on long-running LLM/SSE calls
- **Fit:** the closest match in the batch — those four items are most of Yerins's last year
- **File:** `companies/aimi.md`

```
Subject: Full Stack AI Engineer, Yerins Abraham

Hi Vishnu,

Applying for the Full Stack AI Engineer role posted on Hacker News.

I build AI systems that run in production without falling over when the model
or the network does. Concretely: agent tool calls that survive timeouts and
partial failures with retries, circuit breakers and fail-fast recovery, an MCP
layer for letting agents reach external tools safely, and an eval harness that
catches a regression before it ships rather than after a customer notices it.

That is close to line for line what the posting asks for, on the same stack:
TypeScript, Node.js, AWS. I have also taken agent work into a regulated
environment, shipping a governed agent into a live core-banking API.

CV attached. Is the role still open, and is there a task or a short call you
would want to start with?

Yerins Abraham
yerinsabraham.com
github.com/yerinsabraham
```

---

## #2 Axmed — AI Engineer

- **Channel:** Teamtailor form — https://axmed.teamtailor.com/jobs/8175859-ai-engineer (text goes in the message field)
- **Remote:** fully remote, global team of ~55; no visa sponsorship/relocation (fine)
- **Why now:** past product-market fit, scaling; Gates Foundation grant Feb 2026; agents now run real marketplace steps on real money with a human in the loop
- **Fit:** strongest in the batch — M.D. plus a shipped LMIC health platform plus a maker-checker design is their core requirement, almost word for word
- **File:** `companies/axmed.md`

```
Subject: AI Engineer, Yerins Abraham

Hi,

Applying for the AI Engineer role.

I build autonomous agents trusted to touch real transactions, with a human
pulled in only where the risk calls for it. That is the same problem your
posting describes for sourcing, quoting and order matching, and it is what I
have spent the most time on: a risk-tiered policy that decides what an agent
can do alone versus what gets parked for a second person to approve.

The healthcare side is mine too. I am a software engineer and a medical
doctor, six years of clinical training, and I built a referral platform that
is live in Rwanda, carrying a patient's case to the right specialist and the
answer back. Low-resource settings are familiar ground.

Python is fine. My agent work is mostly TypeScript; retrieval and evaluation
run in Python.

CV attached. Happy to walk through the approval design, or take on a task.

Yerins Abraham
yerinsabraham.com
oystar.app
```

---

## #3 Mastra — Customer Engineer

- **Channel:** Ashby form — https://jobs.ashbyhq.com/Mastra (Customer Engineer). Note addressed to Shane Thomas (co-founder/CPO, leads customer engineering)
- **Remote:** AMER or EMEA hours — WAT works
- **Why now:** open-source TS agent framework, YC W25, $13M seed; hiring the role that is half framework work, half embedded with customers
- **Fit:** TypeScript agent work, an evaluation harness that mirrors why Mastra ships evals, enterprise-embedded delivery already done under the banking contract
- **File:** `companies/mastra.md`

```
Subject: Customer Engineer, Yerins Abraham

Hi Shane,

Applying for the Customer Engineer role posted on Hacker News.

I build AI agents in TypeScript and have taken that work into other people's
codebases under contract, most recently shipping a governed agent into a live
core-banking API alongside the bank's own engineers, PRs and architecture
calls included.

The framework half of this role is where I would add the most. I built the
evaluation and tracing layer that decides whether an agent change is safe to
ship, with golden datasets for retrieval and tool selection and a hard floor
on prompt-injection regressions, open source, so I understand why that has to
live in the framework rather than get bolted on per customer.

Async from Nigeria on WAT, which overlaps EU hours.

CV attached. What does the first conversation usually cover?

Yerins Abraham
yerinsabraham.com
github.com/yerinsabraham/evalgate
```

---

## #4 GitLab — AI Engineer, Enterprise Technology & AI

- **Channel:** Greenhouse form — https://job-boards.greenhouse.io/gitlab/jobs/8556658002 (text in cover-letter field)
- **Remote:** all-remote, but GitLab hires from a fixed country list — **Nigeria/Kenya/UAE eligibility unverified; this is the main risk.** Answer the form's visa/eligibility question honestly.
- **Why now:** live posting; the role is "Customer Zero" for GitLab's own AI adoption, owned end to end on flow metrics
- **Fit:** owns an agent end to end already, with a risk model and maker-checker approval, and the enterprise-integration half is already done
- **File:** `companies/gitlab.md`

```
Subject: AI Engineer, Enterprise Technology & AI, Yerins Abraham

Hi,

Applying for the AI Engineer role on the Enterprise Technology & AI team.

I take an AI initiative from a workflow problem through to something running
in production and measured on real metrics, not a demo. That has meant owning
a support agent end to end: retrieval, a tool-calling layer with a
risk-tiered approval policy, and an evaluation harness that gates every
change before it reaches a customer. I have also integrated a governed agent
into a live core-banking API under role-based controls and audit trails,
which is close to the enterprise-integration work this role does.

Python and TypeScript, REST and GraphQL.

CV attached. I work remotely from Nigeria, happy to confirm eligibility early
if that is a factor.

Yerins Abraham
yerinsabraham.com
github.com/yerinsabraham
```

---

## #5 Oyster — Senior Engineer (Platform)

- **Channel:** Ashby form — https://www.oysterhr.com/careers (Senior Engineer, Platform)
- **Remote:** Remote EMEA including **Africa**, UTC+0 to UTC+4 — best geographic fit in the batch
- **Why now:** Platform Flow Engineering team hiring; posting explicitly wants AI used to cut engineering toil
- **Fit:** medium on stack, high on everything else — he runs the exact ops surface, and has already moved internal workflows to agentic
- **File:** `companies/oysterhr.md`

```
Subject: Senior Engineer, Platform, Yerins Abraham

Hi,

Applying for the Senior Platform Engineer role on the Platform Flow
Engineering team.

I own production operations end to end for an AI service on AWS: ECS and
RDS, CI/CD, observability, and backups I actually restore on a weekly
rehearsal rather than trust blindly. I have also moved internal workflows,
triage, classification, routing, from manual to agentic, gated by an
evaluation step so a change makes them more reliable rather than just
quieter about failing.

Oyster's premise, that talent is everywhere, is one I have lived on the
applicant side. Remote from Lagos, on EMEA hours.

CV attached. Worth a conversation?

Yerins Abraham
yerinsabraham.com
github.com/yerinsabraham
```

---

## #6 CyberAtlas — Software Engineer  · BLOCKED

- **Channel:** email — `atlas@cyberatlas.ai`
- **Remote:** REMOTE Worldwide
- **BLOCKED ON:** the posting requires (1) a query run on https://cyberatlas.ai/finder and (2) its first-page results, both in the email body. Subject must contain "HN Software Engineer". Yerins runs a real Finder query, or we do it together, before this sends.
- **Fit:** backend-and-scale role, lighter on AI, carried by his banking throughput numbers, Go microservices, and search pipeline work
- **File:** `companies/cyberatlas.md`

```
Subject: HN Software Engineer

Hi,

Applying for the Software Engineer role from your Hacker News post.

Anti-bot check:
1. Finder query: [ TO RUN on cyberatlas.ai/finder ]
2. First-page results: [ TO RUN ]

I build backend services that hold up at real throughput: a core-banking API
running roughly 66,000 requests over 30 days at a p95 of 284ms, eight Go
microservices behind service discovery with Kafka and Redis, and a search
pipeline over a large document corpus with hybrid retrieval.

Billions of domains, fingerprinting and detection pipelines is the scale I
want to work at. Python with FastAPI, and Go, are both stacks I use daily.

CV attached.

Yerins Abraham
yerinsabraham.com
github.com/yerinsabraham
```

---

## #7 Mintlify — Senior Applied AI Engineer

- **Channel:** Ashby form — https://jobs.ashbyhq.com/mintlify (Senior Applied AI Engineer)
- **Remote:** listed San Francisco, `isRemote` not set — **the email asks the remote question directly**
- **Why now:** $45M Series B (a16z, Salesforce Ventures); docs platform turning into an AI-docs product; role owns how they evaluate agent performance
- **Fit:** "define how we evaluate and improve agent performance" is a description of a system he has already built; retrieval infra is work he already owns
- **File:** `companies/mintlify.md`

```
Subject: Senior Applied AI Engineer, Yerins Abraham

Hi,

Applying for the Senior Applied AI Engineer role.

I build the retrieval and evaluation layers that decide whether an AI product
is actually right, not just fluent. On retrieval: hybrid search with
source-authority precedence, so a marketing page cannot outrank a policy
document, and a keyword fallback so the product degrades instead of failing
outright. On evaluation: an open-source harness with golden datasets for
retrieval and tool selection, deterministic scoring, and a hard floor on
prompt-injection regressions, built because agent regressions are otherwise
silent.

That is close to your own "define how we evaluate and improve agent
performance," which is the part of the role I would take it for.

CV attached. Two questions: is the role open to remote outside the US, and
what does your evaluation setup look like today?

Yerins Abraham
yerinsabraham.com
github.com/yerinsabraham/evalgate
```

---

## Considered, not in this batch

| Company | Role | Why held |
|---|---|---|
| ElevenLabs | Full-Stack Engineer (Back-End Leaning) / FDE Spain | Strong fit (voice — his Pipecat + Nova Sonic work). Need the live JD and remote scope. Batch 02. |
| Modal | MTS – Product (Backend) / FDE – Systems | Infra backend, remote. Need full JD. Batch 02. |
| Baseten | AI Engineer / Forward Deployed Engineer | $1.5B Series F, strong. Roles list SF / Hybrid — remote-outside-US doubtful. Try as a stretch in Batch 02. |
| Sourcegraph | Agent Engineer / SWE | All-remote global, good fit. Need JD + apply route from the HN post. Batch 02. |
| Lovable | Forward Deployed Engineer / Fullstack | AI app builder, Sweden. Remote scope unclear. Batch 02. |
| Interview Resources | Full Stack AI Engineer | Fit is fine; comp is "$30k to $90k, adjusted per capita" — at Nigeria rates likely below the range worth pursuing. Hold. |
| Pagelove | Founding Software Engineer | Rust codebase; not in his stack. Would be a learning role. Hold unless he wants it. |
| Deeter Analytics | ML Engineer (junior) | Explicitly junior; seniority mismatch. Skip. |
| Anthropic, OpenAI, Ramp, Hex, Linear | various | "Remote" but effectively US / UK / EU-hub. Low probability from Nigeria. Park unless a specific posting opens the door. |

Full discovery output: `scripts/out/candidates-2026-09-09.md` (55 roles after filtering).

---

## Sent — for reference

_(none yet)_
