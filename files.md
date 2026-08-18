# Free course script

Five lessons. Built from `agentfile/NOTES.md`, written while things were
broken.

**How to read this.** Every beat is marked:

- **[FACE]** you look at the camera and say it your way. Bullets only, never a
  script. One or two sentences at a time, then cut.
- **[VO]** you are not on screen. Read the words exactly as written. This is
  where you cannot make a mistake because nobody is watching your mouth.
- **[SCREEN]** screen recording, re-recorded clean after the build, not
  captured live.
- **[GFX]** motion graphic over your voice.

The rule that makes this work: **you only look at the camera when you are
saying something you already believe.** Everything explanatory is voiceover.

---

## Lesson 1 · Set up your AI coding environment

**Target: 6 to 8 minutes.**

**[FACE]** Open cold, no intro, no logo.
- I am a doctor. I taught myself to build.
- The thing I am about to show you is how I built a health platform that runs
  in Rwanda, with no engineering team.
- By the end of this course you will have shipped something real and put it
  on the internet.

**[GFX]** Board 7, the laptop with the arrow leaving frame. Title card over it.

**[VO]** Over graphics.
> There are two ways to use an AI coding agent. Most people open one and say
> "build me an app." They get a pile of code. It runs. They cannot change it,
> they cannot explain it, and they cannot tell whether it is any good.
> This course teaches the other way.

**[GFX]** The two roads. Top road scribbles into a tangle. Bottom road builds
in phases.

**[SCREEN]** Installing VS Code. Installing the agent. The first `--version`
that proves it works.

**[VO]**
> Everything in this course is free. No API key, no credit card, no
> subscription. If a step ever asks you for money, you are on the wrong step.

**[FACE]** Close the lesson.
- Next we do the one thing that separates the two roads.

---

## Lesson 2 · Plan before you code

**Target: 8 to 10 minutes. This is the most important lesson in the course.**

**[FACE]**
- The single move that changes everything is this: you make it write the plan
  before it writes any code.

**[GFX]** Pull quote, held still.
> You build a plan the AI must obey, before the AI writes any code.

**[VO]**
> The plan is a markdown file. It lives in the repo. It gets reviewed, argued
> with, and revised. When code is finally written, it is written against that
> file, and the comments in the code point back at it.
> That one move changes your role from passenger to the person in charge.

**[SCREEN]** Asking the agent to write `PROJECT.md`. Not code. The plan.

**[VO]**
> Notice what was not asked for. No code. No files. A document.

**[GFX]** Step list, step 2 lit.

### The part nobody teaches

**[FACE]**
- Then you do something that feels like extra work and is not.
- You take that plan to a completely fresh chat and ask it what is wrong.

**[GFX]** The fresh chat diagram. Chat A loops back on itself. The teal path
goes A, to the file, to a new chat, and five contradictions type out.

**[VO]**
> A chat that has spent an hour defending a set of choices cannot review them.
> A fresh one has never seen your reasoning, so it argues with the file
> instead of defending it.

**[SCREEN]** The real review. Show the actual findings, unedited.

**[VO]**
> On the project you are about to build, a fresh chat found five contradictions
> in a plan that looked finished. The registry read itself. The document
> claimed two different architectures at the same time. A promise had no
> mechanism behind it.
> On the bigger project, the same trick found sixteen, including one where the
> document contradicted its own numbers table. The chat that wrote it had read
> that table a dozen times and never noticed.

**[FACE]** The important caveat.
- Do not accept the review blindly either.
- Send it back to the first chat and say: tell me which of these are actually
  valid, and ignore any that do not have enough context.
- Permission to reject is what makes it real instead of theatre.

---

## Lesson 3 · Give the AI proper context

**Target: 7 to 9 minutes.**

**[FACE]**
- Your agent starts every session knowing nothing about your project.

**[GFX]** Guessing versus being told. Four dashed arrows fire at the wrong
folders. Then one teal arrow hits the right one.

**[VO]**
> Without a context file it fans out across your repo on probability. It picks
> one answer and sounds completely certain. With one, it goes straight to the
> right place, because you wrote it down.

**[GFX]** Term definition: **Context file**. "A markdown file your coding agent
reads before it touches a single line of your code. Not documentation.
Instructions."

**[SCREEN]** Open agentfile. Answer the eight questions. Download the files.

**[VO]** Over the screen recording, hitting each question as it appears.
> Eight questions. They are not a survey. Each one is there because it stopped
> a real mistake.
> The one most people leave out is the third: what looks wrong but is
> deliberate. Every codebase has decisions that read as bugs. Without that
> section the agent helpfully undoes them.
> And the eighth: what has to be re-run after certain changes. Codegen,
> migrations, lockfiles. Those are obligations with a trigger, not commands you
> run when you feel like it.

**[FACE]** The honest bit.
- I built that tool while making this course, because I needed it.
- It is free, it is open source, and the link is below.

**[GFX]** The product loop. Questions, browser, two files, your repo, the
agent. Then the long curve sweeping back to the start.

---

## Lesson 4 · Build the product

**Target: 12 to 15 minutes. The longest lesson.**

**[FACE]**
- One rule: build in phases, and every phase has to end with something that
  runs.

**[GFX]** Step list, phases lighting one at a time.

**[VO]**
> Not "build the app." Build phase one, and stop. Look at it. Then phase two.
> Six small arguments instead of one big disappointment.

**[SCREEN]** Phase 1. The skeleton, deployed, doing almost nothing.

**[VO]**
> That is deliberately boring. It deploys. That is the entire point of phase
> one: prove the ground holds before you build on it.

### Where it goes wrong, on camera

**[FACE]**
- Now the part most tutorials cut out.

**[SCREEN]** The build failing. The real error, unedited.

**[GFX]** Terminal replay, retyped large enough to read on a phone.

**[VO]**
> This is not a mistake in the video. This is the rule working. The plan said a
> missing template must fail the build, and it did, and it named the file and
> both ways to fix it.

**[FACE]** The overruling story.
- Twice during this build the agent told me I was wrong.
- Both times I overruled it, and both times I was right, for the same reason.
- It was optimising the thing in front of it. I was optimising what the thing
  is for.

**[VO]**
> An agent that is never overruled is not being used properly. It is very good
> locally. It does not know what your project is for unless you tell it, and
> even then it will argue.

---

## Lesson 5 · Test, deploy, and your turn

**Target: 8 to 10 minutes.**

**[FACE]**
- Never trust the word "done" until you have clicked the thing yourself.

**[VO]**
> On the other project I am building, an agent reported a finished build. The
> main button did nothing. My entire bug report was five words: "done, generate
> project does nothing so far."
> Two causes. One was configuration. The other was its own bug, and that one
> was worse: when the button failed, the app showed nothing at all. No error,
> no message. It just sat there.

**[GFX]** Before and after: a silent failure, then the same failure explaining
itself.

**[VO]**
> A broken app that tells you what is broken is a five minute fix. A broken app
> that stays silent is an evening.

**[SCREEN]** Deploying. The live URL. Clicking through it for real.

### The wall

**[FACE]** This is the cliff the free course ends on. Do not resolve it.
- You have shipped something. Now the hard part starts.
- The moment you add users, a database, payments, or you open a codebase
  somebody else wrote, all of this gets harder.
- That is what the full course is.

**[SCREEN]** Show the wall for real. Something breaking that this method alone
does not fix.

**[GFX]** Board 6, the bricked-up doorway.

**[FACE]** The ask.
- The tool you used in lesson 3 is open source and it needs more stacks.
- Adding one is a single markdown file. That is a real first pull request on a
  real project, and it takes about thirty minutes.
- Link below. Go and put your name on something.

---

## Still to write

- Exact wording for the lesson 5 wall. It has to be honest, not a cliffhanger
  trick, or the paid course starts on a lie.
- The screen recording shot list, once the build is re-recorded clean.
- Element list for the graphics, which comes from this file once the wording
  is locked.
