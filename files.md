# Batch 01, for review

**2026-09-10. 7 drafts. Nothing sent.**

Reply per item: **send** / **change X** / **hold**.

- **#1 AiMi** and **#6 CyberAtlas** are real emails, sent from `yerinssaibs@gmail.com` once the Gmail connector is reconnected and the sender identity is verified (`SENDER.md`).
- **#6 CyberAtlas** is blocked until a query is run on cyberatlas.ai/finder — its posting requires the query and results in the email body.
- **#2 Axmed, #3 Mastra, #4 GitLab, #5 Oyster, #7 Mintlify** apply through a form (Teamtailor / Ashby / Greenhouse). The text below is written to go in the form's cover-letter / message field. Yerins submits these, or approves and I walk him through each form. CV: `cv/Yerins-Abraham-CV.pdf`.

Sender identity verified: _pending — connector expired at last check_.

---

## #1 AiMi — Full Stack AI Engineer

- **Channel:** email — `vishnu.swaroop@aimi.technology`
- **Remote:** Remote (Everywhere)
- **Why now:** live agentic platform for capital-markets ops; posting asks specifically for MCP connectors, agent evals, agent observability, and resilience on long-running LLM/SSE calls
- **Fit:** the closest match in the batch — those four items are most of Yerins's last year
- **File:** `companies/aimi.md`

```
Subject: Full Stack AI Engineer — Yerins Abraham

Hi Vishnu,

Applying for the Full Stack AI Engineer role you posted on Hacker News.

I'm Yerins Abraham, a backend engineer building AI systems that take real
actions in production. I run the platform behind Lira Intelligence, an AI
support agent that answers from a company's knowledge base and then acts on
their systems across chat, voice and WhatsApp.

MCP connectors, evals on agent accuracy, and making long-running LLM and SSE
calls survive timeouts and partial failure - that is most of what I have built
this year. Lira runs customer-owned tools through an MCP gateway with SSRF
checks and per-tool rate limits, gates every merge on an eval harness with
tool-selection and prompt-injection datasets, and puts a seven-tier risk model
with maker-checker approval in front of anything privileged. TypeScript,
Fastify, Node, AWS. I have also shipped a governed agent into a live
core-banking API.

CV attached. Is the role still open, and is there a task or a call you would
want to start with?

Yerins Abraham
yerinsabraham.com
github.com/yerinsabraham
```

---

## #2 Axmed — AI Engineer

- **Channel:** Teamtailor form — https://axmed.teamtailor.com/jobs/8175859-ai-engineer (text goes in the message field)
- **Remote:** fully remote, global team of ~55; no visa sponsorship/relocation (fine)
- **Why now:** past product-market fit, scaling; Gates Foundation grant Feb 2026; agents now run real marketplace steps on real money with a human in the loop
- **Fit:** strongest in the batch — M.D. + Oystar (LMIC health, shipped) + maker-checker/human-in-the-loop is their core sentence
- **File:** `companies/axmed.md`

```
Subject: AI Engineer — Yerins Abraham

Hi,

Applying for the AI Engineer role.

I'm Yerins Abraham. I'm a software engineer and a medical doctor - an M.D. in
general medicine, six years - and I build AI systems full time now. I run the
platform behind Lira Intelligence, an AI support agent that answers from a
company's knowledge base and then takes action on their systems, with a
maker-checker step that parks anything risky for a second person to authorise.

Agents running real steps of a marketplace - sourcing, quoting, order matching -
on real money with a human in the loop is the exact shape of what I have built,
and the human-in-the-loop part is the piece I have spent the most time getting
right. The healthcare context is also mine: I built Oystar, a clinic-to-
specialist referral platform live in Rwanda, FHIR-compatible, that carries a
patient's case to the right specialist and brings the answer back.

Python and an orchestration framework is fine - Lira's agent layer is
TypeScript, but the retrieval and eval pipeline is Python.

CV attached. Happy to walk through the maker-checker design, or do a task.

Yerins Abraham
yerinsabraham.com
oystar.app
```

---

## #3 Mastra — Customer Engineer

- **Channel:** Ashby form — https://jobs.ashbyhq.com/Mastra (Customer Engineer). Note addressed to Shane Thomas (co-founder/CPO, leads customer engineering)
- **Remote:** AMER or EMEA hours — WAT works
- **Why now:** open-source TS agent framework, YC W25, $13M seed; hiring the role that is half framework / half embedded-with-customers
- **Fit:** TS agent work, evalgate mirrors their built-in evals, enterprise-embedded delivery done under the banking contract
- **File:** `companies/mastra.md`

```
Subject: Customer Engineer — Yerins Abraham

Hi Shane,

Applying for the Customer Engineer role you posted on Hacker News.

I'm Yerins Abraham, a TypeScript engineer who builds AI agents in production. I
run the platform behind Lira Intelligence - RAG, a tool-calling agent layer,
and an eval harness that gates every merge - and I have taken that work into
other people's codebases, most recently shipping a governed agent into a live
core-banking API alongside the bank's own engineers.

The half of the role that is framework work is the half I would want. I
maintain evalgate, an open-source regression gate for LLM systems with golden
datasets for retrieval and tool selection and a hard zero on prompt-injection.
It exists for the same reason Mastra has evals and tracing built in, which is
that agent regressions are silent otherwise. The embedded half I have done
under an enterprise contract, PRs and architecture calls included.

Async from Nigeria on WAT, which lines up with your EU hours.

CV attached. What does the first conversation usually cover?

Yerins Abraham
yerinsabraham.com
github.com/yerinsabraham/evalgate
```

---

## #4 GitLab — AI Engineer, Enterprise Technology & AI

- **Channel:** Greenhouse form — https://job-boards.greenhouse.io/gitlab/jobs/8556658002 (text in cover-letter field)
- **Remote:** all-remote, but GitLab hires from a fixed country list — **Nigeria/Kenya/UAE eligibility unverified; this is the main risk.** Answer the form's visa/eligibility question honestly.
- **Why now:** live posting; the role is "Customer Zero" for GitLab's own AI adoption, owned end-to-end on flow metrics
- **Fit:** owns Lira end-to-end, agentic architecture with risk model + maker-checker, enterprise-integration half already done
- **File:** `companies/gitlab.md`

```
Subject: AI Engineer, Enterprise Technology & AI — Yerins Abraham

Hi,

Applying for the AI Engineer role on the Enterprise Technology & AI team.

I'm Yerins Abraham. I build and run the platform behind Lira Intelligence, an
AI support agent that answers from a company's knowledge base and then takes
action on their systems - I own it end to end, from the RAG pipeline to the
eval harness that gates CI.

The role's shape - diagnose the workflow first, own the initiative through
deployment, measure it on flow metrics - matches how I work. Lira's agent layer
has a tool registry with per-org packs, a seven-tier risk model, and
maker-checker approval; the eval harness scores retrieval and tool selection
deterministically and fails the build on a prompt-injection regression. I have
also integrated a governed agent into a live core-banking API under role-based
controls and audit trails, which is the enterprise-integration half of this
job. Python and TypeScript, REST and GraphQL.

CV attached. I work remotely from Nigeria - happy to confirm eligibility early
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
- **Fit:** medium on stack, high on everything else — he runs the exact ops surface, and has moved internal workflows to agentic already
- **File:** `companies/oysterhr.md`

```
Subject: Senior Engineer, Platform — Yerins Abraham

Hi,

Applying for the Senior Platform Engineer role on the Platform Flow Engineering
team.

I'm Yerins Abraham, a backend engineer in Nigeria. I run the platform behind
Lira Intelligence - a Fastify and TypeScript service on AWS - and I own its
production operations: ECS and RDS, CI/CD, observability, nightly encrypted
backups with weekly restore rehearsals I actually run.

The part of the posting about using AI to cut engineering toil is something I
have built rather than planned. Lira's own internal workflows - triage,
classification, routing - moved from manual to agentic, gated by an eval
harness so a change makes them better and not just quieter. I would bring that
to the space between code and production.

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
- **Fit:** backend-and-scale role, lighter on AI — carried by his banking throughput numbers, Go microservices, and Qdrant search work
- **File:** `companies/cyberatlas.md`

```
Subject: HN Software Engineer

Hi,

Applying for the Software Engineer role from your Hacker News post.

Anti-bot check:
1. Finder query: [ TO RUN on cyberatlas.ai/finder ]
2. First-page results: [ TO RUN ]

I'm Yerins Abraham, a backend engineer. Most of my work is high-throughput
services and data systems: a core-banking API running roughly 66,000 requests
over 30 days at a p95 of 284ms on ECS and RDS, eight Go microservices behind
Eureka with Kafka and Redis, and a retrieval pipeline on Qdrant with hybrid
search over a large document corpus.

Billions of domains, fingerprinting, search and detection pipelines is the
scale I want to work at, and Python with FastAPI and Go are both stacks I use.

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
- **Fit:** "define how we evaluate and improve agent performance" is what evalgate is for; retrieval infra is Lira's RAG layer
- **File:** `companies/mintlify.md`

```
Subject: Senior Applied AI Engineer — Yerins Abraham

Hi,

Applying for the Senior Applied AI Engineer role.

I'm Yerins Abraham. I run the platform behind Lira Intelligence, an AI support
agent that answers from a customer's knowledge base and then acts on their
systems. The retrieval side is production RAG on Qdrant - hybrid search,
source-authority precedence so a marketing page cannot outrank a policy
document, segment filtering, keyword fallback when the vector store is down.

"Define how we evaluate and improve agent performance" is the line I would take
this role for. I maintain evalgate, an open-source regression gate for LLM
systems: golden datasets for retrieval, tool selection and groundedness,
deterministic recall@k and nDCG, LLM-as-judge for hallucination, and
prompt-injection rows that fail the build above zero. It came out of needing
exactly that for Lira.

CV attached. Two questions: is the role open to remote outside the US, and what
does your evaluation setup look like today?

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
| Interview Resources | Full Stack AI Engineer | Fit is fine; comp is "$30k–$90k, adjusted per capita" — at Nigeria rates likely below the range worth pursuing. Hold. |
| Pagelove | Founding Software Engineer | Rust codebase; not in his stack. Would be a learning role. Hold unless he wants it. |
| Deeter Analytics | ML Engineer (junior) | Explicitly junior; seniority mismatch. Skip. |
| Anthropic, OpenAI, Ramp, Hex, Linear | various | "Remote" but effectively US / UK / EU-hub. Low probability from Nigeria. Park unless a specific posting opens the door. |

Full discovery output: `scripts/out/candidates-2026-09-09.md` (55 roles after filtering).

---

## Sent — for reference

_(none yet)_
