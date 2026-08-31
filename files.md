# WHOLESNACK™ — Project Onboarding Requirements

**Prepared by:** Creovine LTD
**Prepared for:** Wholesnack™
**Document version:** 1.0

---

## How to read this document

This is not a list of questions. Most of the decisions on this project are ours to make, and we have made them — they are recorded here so you know what is being built and can object if anything doesn't match your intent.

The document has three parts:

| Part | What it contains | Action needed from you |
| --- | --- | --- |
| **Part 1** | Information and assets we need from you to begin | **Yes — sections 1 to 4** |
| **Part 2** | Decisions we have already made on your behalf | No — read for awareness |
| **Part 3** | One item that requires your decision | **Yes — section 13** |

If you only have ten minutes, read **Section 1** and **Section 13**. Those two are the only things that can delay the project.

---
---

# PART 1 — WHAT WE NEED FROM YOU

---

## 1. Company & Legal Details

> ### ⚠️ START THIS SECTION TODAY
> The **D-U-N-S Number** below is the single item most likely to delay your launch, because it depends on a third party's processing time, not ours. Everything else on this project can move in parallel — this one cannot be rushed. Please begin it immediately.

Publishing an app on the Apple App Store and Google Play under a company name (rather than an individual's personal name) requires both platforms to independently verify that your business legally exists. We need the following to complete that verification.

| # | Item | Notes |
| --- | --- | --- |
| 1.1 | **Registered company name** | Exactly as it appears on your CAC documents — spelling, spacing, suffix (LTD / Limited) all must match precisely. This becomes the developer name shown publicly on both app stores. |
| 1.2 | **CAC Certificate of Incorporation** | PDF or clear scan. |
| 1.3 | **Tax Identification Number (TIN)** | |
| 1.4 | **Registered company address** | Must match your CAC records exactly. |
| 1.5 | **Company phone number** | Must be reachable — Apple and Google may call this number to verify the business. |
| 1.6 | **Name, title and email of the signing authority** | The person legally authorised to enter agreements on behalf of the company. Apple requires this and may contact them directly. |
| 1.7 | **D-U-N-S Number** | Required by both Apple and Google. **We can obtain this for you at no extra cost**, or you can do it yourselves — see below. |

### About the D-U-N-S Number

A D-U-N-S Number is a nine-digit business identifier issued by Dun & Bradstreet. **Both Apple and Google require one to open an organisation developer account.** There is no way around it.

- It is **free** to obtain.
- It typically takes **5 to 30 business days**, depending on how quickly Dun & Bradstreet can verify your business.
- Your company may already have one without knowing — it can be looked up before applying, and we will check this first either way.

### You have two options — choose whichever you prefer

**Option 1 — We obtain it for you.** ✅ *Recommended if you'd rather not deal with it*

We have done this before and we are happy to handle the entire process on your behalf at no additional cost. We check whether your company already has a number, submit the application, monitor its progress, and follow up with Dun & Bradstreet if it stalls.

All we need to proceed is **items 1.1 to 1.6 above** — your company details, CAC certificate, TIN, address, phone number and signing authority. Send those and consider it handled.

**Option 2 — You obtain it yourselves.**

Entirely reasonable if you prefer to keep this in-house. The application is made free of charge through Dun & Bradstreet, and Apple provides a dedicated lookup and request form for developers on their website. Once you receive the number, send it to us and we proceed.

Please avoid third-party services that charge a fee for this or promise expedited processing. The application is free, and the waiting time is Dun & Bradstreet's verification process — nobody can genuinely shorten it.

> **One thing to expect either way:** Dun & Bradstreet may contact your company directly by phone or email to verify that the business is real and active. This happens whether we apply or you do — they are verifying *you*, not us. **Please watch for it and respond promptly.** An unanswered verification call is the most common reason these applications sit idle for weeks.

**Whichever option you choose, please begin this week.** We can build the entire application while it processes, but neither store will accept a submission without it.

### If the company is not yet incorporated

Tell us now rather than later. There are workable alternatives — including publishing initially under an individual developer account and transferring ownership to the company once incorporation completes. That path has trade-offs we should discuss before we start, not after.

---

## 2. Domain & Official Email Address

We understand from our earlier conversation that a domain may already exist. Please confirm.

| # | Item | Notes |
| --- | --- | --- |
| 2.1 | **The domain name** | Confirm the exact domain, and that you control it. |
| 2.2 | **An official email address on that domain** | For example `dev@wholesnack.com` or `admin@wholesnack.com`. |
| 2.3 | **The password for that email address** | Shared securely — not over WhatsApp or plain email. We will send you a secure link. |

### Why we need the email password

Every account this product depends on — Apple Developer, Google Play, cloud infrastructure, AI provider, analytics — must be created **in Wholesnack's name, using a Wholesnack email address.** These accounts hold your app, your users, and your data.

To create and verify them, we need to receive confirmation emails at that address. That is the only reason we need access.

**This protects you, not us.** If we created these accounts on a Creovine email, Wholesnack would be permanently dependent on Creovine to access its own App Store listing, its own database, and its own users. We do not build projects that way. You should own everything from day one.

Once each account is live, you can change the password at any time and we will continue working through delegated administrator access.

### If you don't have a domain or business email yet

Say so and we will handle setup. We only need you to confirm the exact domain name you want to use — this becomes your website, your app store listing URL, and your brand email, so it is worth deciding deliberately.

---

## 3. Brand Assets

Please create a **Google Drive folder** named `Wholesnack — Brand Assets` and grant edit access to the Creovine email address provided separately.

Upload whatever exists of the following:

| # | Item | Notes |
| --- | --- | --- |
| 3.1 | **Logo** | Any format. Vector files (`.svg`, `.ai`, `.eps`, `.pdf`) are far better than screenshots or JPEGs — they scale to any size without quality loss. If you only have a JPEG or PNG, upload it anyway. |
| 3.2 | **Existing brand colours** | Hex codes if you have them, or just images showing the colours. |
| 3.3 | **Existing fonts** | Names, or files if licensed. |
| 3.4 | **Any designs, sketches, mockups or moodboards** | Including rough phone-camera photos of paper sketches. Nothing is too informal — it tells us how you picture this. |
| 3.5 | **Reference apps** | Three to five apps whose look and feel you admire, and **one you dislike**, with a sentence on why. The dislike is often more useful to us than the likes. |
| 3.6 | **Final app name** | Confirm the exact spelling and capitalisation: `Wholesnack`, `WholeSnack`, or `WHOLESNACK`. |
| 3.7 | **Trademark status** | The blueprint uses `™` throughout. Confirm whether the mark is formally registered, in progress, or aspirational. This affects what we can legally print inside the app and on the store listing. |

**If none of this exists yet, that is completely fine.** Say so and we design the full identity from scratch — that work is already part of this engagement. We simply need to know which situation we're in before we begin.

---

## 4. App Store Listing Information

We can draft all of this and send it to you for approval. We need your input on the following.

| # | Item | Our position |
| --- | --- | --- |
| 4.1 | **Final app name for the stores** | We will check availability on both stores and flag conflicts. |
| 4.2 | **One-line tagline** | Our suggestion: *"Don't just get fit. Become the snack."* Confirm or replace. |
| 4.3 | **Public support email address** | Both stores require a working support contact. Can be on your domain. |
| 4.4 | **Privacy Policy and Terms of Service** | **We will draft both.** You need a lawyer to review and approve them before submission. Please confirm you have legal counsel available, or tell us and we will recommend options. This is required by both stores — an app cannot be published without it. |
| 4.5 | **Age rating** | **Our recommendation: 18+.** The app scores physical progress, analyses body photographs, and includes social comparison between users. Rating it 18+ is both the responsible choice and the one least likely to cause problems in store review. Please confirm you accept this. |
| 4.6 | **Launch market** | **Our assumption: Nigeria first, then broader Africa and international.** This directly shapes the food database, the payment method and the pricing. Please confirm or correct. |

---
---

# PART 2 — DECISIONS WE HAVE ALREADY MADE

These are ours to decide, and they are decided. They are documented here for transparency. **No action is needed** — but if any of them conflicts with your intent, tell us now rather than after we've built it.

---

## 5. Version 1 centres on the AI Coach. Human coaches are not in Version 1.

The original blueprint describes a network of verified human coaches with client accounts, direct chat, published programs and revenue sharing.

**We are not building that in Version 1**, and we recommend you don't want us to.

**Why:**

A coach network is a two-sided marketplace. It only works when both sides are already full — coaches won't join a platform with no users, and users won't pay for coaches who aren't there. Building it before Wholesnack has an audience means building infrastructure that sits empty. It also introduces payouts, coach verification, refunds, disputes and revenue splits — a large amount of engineering that produces no value on day one.

**What we're building instead:**

The AI Coach carries the entire coaching experience in Version 1. It is available instantly, to every user, at any hour, in a way no human coach network can match at launch.

**And the human element is not lost — it is repositioned as the growth engine.**

When a recognisable person — an athlete, a trainer, a creator, anyone with an audience — uses Wholesnack and their transformation is visibly working, they will share it. Their Snack Score, their Day 1 → Day 90 card, their progress. They are not sharing to promote Wholesnack; they are sharing because it makes *them* look good.

That is the point. It markets them, and it markets the platform at the same time. Their followers see a real transformation and a Wholesnack score attached to it, and they come looking. Every share is an advertisement that costs nothing and carries more credibility than any advertisement we could buy.

This means Version 1 should invest in **making progress worth showing off** — the share cards, the Snack Score visual, the transformation comparison — rather than in coach account management. That is where the growth is.

Formal coach accounts, program sales and revenue sharing remain on the roadmap. They are a later phase, built once there is an audience worth building them for.

---

## 6. The AI Coach will be unlimited in Version 1

Users will not face message limits, daily caps or usage restrictions on the AI Coach in Version 1.

**Why:**

The AI Coach is the product. Version 1's job is to prove that people find it genuinely useful and keep coming back — and we cannot learn that from users who are being rationed. We also need real usage data to design a sensible structure later; capping usage now means guessing at limits with no evidence.

**How this stays under control:**

We are not leaving it unmanaged. The architecture includes intelligent model routing from day one — matching the strength of the AI model to what each task actually requires:

| Task | Approach |
| --- | --- |
| Weekly Snack Score verdict, "Why" Engine explanations, initial program design at onboarding | Our most capable model. These are the moments users remember and screenshot — they need to be excellent. |
| Daily Workout Recipe and Daily Menu generation | A strong, efficient model. High quality, run once or twice a day per user. |
| Everyday coach chat, exercise substitutions, meal photo scanning | A fast, lightweight model. High frequency, straightforward tasks. |

Alongside this we build in response caching, context optimisation, usage monitoring per user, and automated alerts — from the first commit, not retrofitted later.

**When subscriptions launch**, we will structure AI access using real data on how people actually use it, rather than a limit invented before launch.

---

## 7. Food Database — our approach

The local food engine is, in our assessment, the strongest genuine differentiator in the entire Wholesnack concept. Almost every major fitness app fails outside Western markets because it assumes the user buys salmon, quinoa and Greek yoghurt. Getting this right matters more than most of the feature list.

**We researched the available options. Our approach is a hybrid:**

**Layer 1 — Licensed global database.** A commercial nutrition database (FatSecret or equivalent) covering international and packaged foods, barcode data and restaurant items. Mature, reliable, well-maintained.

**Layer 2 — A Creovine-curated West African food set.** We compile this ourselves from authoritative sources: the **FAO/INFOODS Africa Food Composition Database**, the **Nigerian Food Composition Table**, and **USDA FoodData Central**. This covers jollof rice, egusi, moimoi, suya, ofada rice, pounded yam, plantain, akara, tuwo, waakye and the rest of the everyday foods people actually eat — with real macronutrient data, realistic Nigerian portion sizes, and common preparation variants.

**A note on the free alternatives:** There are public "Nigerian food API" projects available. We reviewed them. They are hobby projects — small, inconsistently sourced, unmaintained, and in some cases nutritionally inaccurate. They are not something a commercial product should depend on. We are building the curated layer properly.

**How it is structured:** as an expandable regional system, not a hardcoded Nigerian list. Adding Ghana, Kenya, South Africa, India or Latin America later becomes a data exercise, not an engineering rebuild.

**No action needed from you.**

---

## 8. Exercise Library & Demonstration Media — our approach

**Version 1:** approximately 120 to 150 exercises, covering every major movement pattern, muscle group and equipment situation — full gym, dumbbells only, bodyweight only. Each exercise includes written instructions, target muscles, difficulty, equipment required, common form errors, and a visual demonstration.

**For the visual demonstrations we recommend licensed exercise animations** rather than commissioning a custom video shoot. Licensed libraries are consistent, immediately available, professionally produced, and a fraction of the cost. A custom shoot means booking a studio, a model, a videographer, and several weeks of production and editing — for a result users largely cannot distinguish from good animation.

**Custom branded video is worth doing later**, once Wholesnack has traction and its visual identity is established. At that point it becomes a content production project with its own plan. It is not a Version 1 priority.

**No action needed from you.**

---

## 9. Device & Platform Support — our approach

**Both iOS and Android at launch.**

Nigeria and most of the African market are overwhelmingly Android, so an iOS-only launch would miss the majority of the target audience. But an Android-only launch would miss the segment most likely to subscribe, and would leave the product absent from the App Store — which still carries meaningful credibility. We are building both.

**Minimum supported versions: iOS 16+ and Android 10+.** This covers effectively the entire active market on both platforms while allowing us to use modern development tools rather than working around obsolete ones.

**On low-end devices:** this is not a concern for Version 1. Version 1 does no heavy processing on the phone itself — the intelligence runs on our servers, and the app is a well-optimised interface to it. It will run comfortably on inexpensive Android hardware.

Device performance becomes a genuine consideration only when camera-based form analysis arrives in a later version, since that runs live on the phone. **We will raise it then, with specific recommendations, before that work begins.** It does not need a decision now.

**No action needed from you.**

---

## 10. Wearables & Health Integrations — for your awareness

**Version 1 includes:** Apple Health (iOS) and Google Health Connect (Android). These give us steps, activity, heart rate and sleep from the phone itself and from most wearables users already own — including many Fitbit and Garmin devices, since those typically sync into Apple Health and Health Connect anyway. This covers the large majority of real-world users.

**Version 1 does not include:** direct Fitbit and Garmin API integrations.

We want to be transparent about why, because it is not a technical limitation. **Fitbit and Garmin require approved developer partnerships to access their health data directly.** That is a business approval process run by those companies, on their timeline, with their criteria — not something we can complete by writing code. Garmin in particular gates its health API behind a commercial agreement.

We are flagging this now so it is a known plan rather than a surprise. If direct integration with those platforms becomes important, we should begin the application process early, because approval time is outside anyone's control.

**No action needed from you.**

---

## 11. What Creovine Handles

You do not need to think about, set up, or manage any of the following. This is our responsibility:

- Source code repository and version control
- Cloud infrastructure, database and file storage
- AI provider setup and management
- Apple Developer Program registration and configuration
- Google Play Console registration and configuration
- Server infrastructure, deployment and monitoring
- Automated backups
- Analytics implementation
- Security configuration
- Store submission for both platforms

**On ownership:** every account above is registered in Wholesnack's name wherever platform rules allow, using the Wholesnack email address from Section 2. The source code is yours. If at any point you want the repository moved to a Wholesnack-controlled account, we transfer it — no negotiation, no exit process, no cost. You are never locked in.

---
---

# PART 3 — AWAITING YOUR DECISION

---

## 12. ⏳ PENDING — How subscriptions are collected

**This is the one open item.** Everything else proceeds without it, but we need your decision before we build the subscription layer.

### The situation

Apple requires digital subscriptions sold inside an iOS app to go through Apple's own in-app purchase system, and takes **15% to 30%** of every payment. Apple also prohibits an app from linking to, or even mentioning, an external payment page for digital content. Google Play operates similarly.

This is a business decision with real revenue consequences, so it is yours to make. Here are the two viable paths.

### Option A — In-app purchase

The user subscribes inside the app, in a few taps, using the card already saved to their Apple or Google account.

**Advantages:** the smoothest possible experience and the highest conversion rate. Users trust it. Apple handles billing, renewals, refunds and failed payments. Nothing to build or maintain on the payment side.

**Disadvantages:** Apple and Google take their cut of all subscription revenue. Payouts arrive on their schedule, in their currency, subject to their thresholds.

### Option B — Web-based subscription

The user subscribes on the Wholesnack website using Paystack, Flutterwave or Stripe. The app recognises their active subscription and unlocks.

**Advantages:** no platform commission — the revenue is yours. Local Nigerian payment methods work properly: bank transfer, USSD, local cards. Money settles into a Nigerian account on your terms. Full control over pricing, promotions and trials.

**Disadvantages:** more friction, which means lower conversion. And critically — **the app is not permitted to link to the payment page, or tell the user where to go.** Users must find it themselves. This is Apple's rule, and apps get rejected for breaking it.

### Our observation

For a Nigeria-first launch, Option B has a strong case: the commission saved is significant, and local payment rails matter more here than in markets where everyone has a card on file with Apple.

A common approach is a hybrid — web subscription as the primary path, with in-app purchase available as a convenience for users who prefer it. It captures both, at the cost of maintaining two payment systems.

### What we need

**Your decision: A, B, or hybrid.**

If you accept Apple's commission, we build Option A and it is straightforward. If you do not, we build Option B and design the app to comply carefully with the linking restrictions. Either is fine — we simply cannot build the subscription layer until we know which.

This does not block us today. Onboarding, the AI Coach, workouts, nutrition, Snack Score and the dashboard all proceed regardless. **We need your answer before the subscription system is built.**

---
---

# SUMMARY CHECKLIST

## Needed from you

- [ ] **1.1–1.6** Company details, CAC certificate, TIN, address, phone, signing authority
- [ ] **1.7** D-U-N-S Number — **longest lead time on the project.** Tell us whether you want us to obtain it for you (send 1.1–1.6 and we handle it) or you will obtain it yourselves
- [ ] **2.1–2.3** Domain, official email address, and secure password handover
- [ ] **3** Google Drive folder created and shared, with whatever brand assets exist
- [ ] **4.4** Confirmation that legal counsel is available to review Privacy Policy and Terms
- [ ] **4.5** Confirmation of 18+ age rating
- [ ] **4.6** Confirmation of launch market
- [ ] **12** Subscription method decision — Option A, B, or hybrid

## For your awareness only — no action needed

- [ ] **5** Human coach network is not in Version 1
- [ ] **6** AI Coach is unlimited in Version 1
- [ ] **7** Food database approach
- [ ] **8** Exercise library and media approach
- [ ] **9** Device and platform support
- [ ] **10** Fitbit and Garmin are not in Version 1

---

# WHAT HAPPENS NEXT

Once Sections 1 through 4 are received, we begin immediately:

1. **Technical kickoff and architecture** — system design, data architecture, AI architecture
2. **Brand direction** — visual identity work begins from your assets, or from scratch
3. **Developer account applications** — submitted as soon as the D-U-N-S Number arrives
4. **Design and engineering** — running in parallel from week one

You will receive regular development updates and working builds throughout, so you can see the product taking shape rather than waiting for a reveal at the end.

---

**Creovine LTD**
*One team. One project. One delivery partner.*
