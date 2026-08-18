# Free course script

Five lessons. Everything you say is written out. Read it, then say it your own
way, but the words are here so you never have to remember them.

## How the clips are named

Name every file the moment you record it. Then editing is sorting, not
hunting.

```
L2-CAM-03.mov     lesson 2, camera, third camera clip
L2-VO-05.wav      lesson 2, voiceover, fifth voice clip
L2-SCR-02.mov     lesson 2, screen recording, second screen clip
```

Numbers run in order down this document. The clip name is printed above every
block, so you never have to decide.

- **CAM** you are on screen. Say it your way.
- **VO** you are not on screen. Read it as written, you cannot fumble it.
- **SCR** screen recording, re-recorded clean after the build, never live.
- **GFX** motion graphic. Nothing for you to do, it goes over a VO clip.

---

# Lesson 1 · Set up your AI coding environment

Target 6 to 8 minutes.

### L1-CAM-01

> Hey. If you have ever wanted to build an app but you are not a developer,
> this is the course for you. Over the next five lessons we are going to build
> a real product together, put it on the internet, and you are going to
> understand every part of it. Not copy and paste it. Understand it.

### L1-CAM-02

> I built a health platform that is running in Rwanda right now. I built a VPN.
> I built a payments app. And I did most of it without an engineering team.
> Everything I used to do that, I am going to show you.

### GFX-01
Title card. "Build real software with AI." Over L1-VO-01.

### L1-VO-01

> There are two ways to use an AI coding agent. Most people open one and type
> "build me an app." They get a pile of code. It runs. They cannot change it,
> they cannot explain it, and they cannot tell whether it is any good.
> This course teaches the other way.

### GFX-02
The two roads. Top road scribbles into a tangle. Bottom road builds in phases.

### L1-SCR-01
Installing VS Code. Installing the agent. The first version command that proves
it is working.

### L1-VO-02

> Everything in this course is free. No API key, no credit card, no
> subscription. If a step ever asks you for money, you are on the wrong step.

### L1-CAM-03

> That is your workshop set up. In the next lesson we do the one thing that
> separates people who build with AI from people who just generate code with
> it.

---

# Lesson 2 · Plan before you code

Target 8 to 10 minutes. This is the most important lesson in the course.

### L2-CAM-01

> Here is the single move that changes everything. Before you let it write one
> line of code, you make it write the plan.

### GFX-03
Pull quote, held still.
> You build a plan the AI must obey, before the AI writes any code.

### L2-VO-01

> The plan is a markdown file. It lives in the project. It gets reviewed,
> argued with, and revised. When code is finally written, it is written against
> that file, and the comments in the code point back at it.
> That one move changes your role from passenger to the person in charge.

### L2-SCR-01
Asking the agent to write PROJECT.md. Not code. A document.

### L2-VO-02

> Notice what was not asked for. No code. No files. Just a document.

### L2-CAM-02

> Now the part almost nobody teaches, and it feels like extra work until the
> first time it saves you. You take that plan, you open a completely fresh
> chat, and you ask it what is wrong with it.

### GFX-04
The fresh chat diagram. Chat A loops back on itself uselessly. The teal path
goes A, to the file, to a new chat, and the problems type out one by one.

### L2-VO-03

> A chat that has spent an hour defending its own choices cannot review them.
> A fresh one has never seen your reasoning, so it argues with the file instead
> of defending it.

### L2-SCR-02
The real review. The actual findings, unedited.

### L2-VO-04

> On the project you are about to build, a fresh chat found five contradictions
> in a plan that looked finished. The registry read itself. The document
> claimed two different architectures at the same time. A promise had nothing
> behind it.
> On a bigger project of mine the same trick found sixteen problems, including
> one where the document contradicted its own numbers. The chat that wrote it
> had read those numbers a dozen times and never noticed.

### L2-CAM-03

> But do not accept the review blindly either. Take those findings back to the
> first chat and say: tell me which of these are actually valid, and ignore any
> that do not have enough context about what we are building. Giving it
> permission to reject is what makes this real instead of theatre.

---

# Lesson 3 · Give the AI proper context

Target 7 to 9 minutes.

### L3-CAM-01

> Every time you open your agent, it starts knowing nothing about your project.
> Nothing. So it guesses.

### GFX-05
Guessing versus being told. Dashed arrows fire at the wrong folders. Then one
teal arrow hits the right one.

### L3-VO-01

> Without a context file it spreads out across your project on probability. It
> picks an answer and it sounds completely certain. With one, it goes straight
> to the right place, because you told it.

### GFX-06
Term definition. "Context file. A markdown file your coding agent reads before
it touches a single line of your code. Not documentation. Instructions."

### L3-SCR-01
Open agentfile. Answer the eight questions. Download the two files. Drop them
into the project.

### L3-VO-02

> Eight questions. They are not a survey. Every one of them is there because it
> stopped a real mistake.
> The one most people leave out is the third: what looks wrong but is
> deliberate. Every project has decisions that look like bugs. Without that
> section your agent will helpfully undo them.
> And the eighth: what has to be re-run after certain changes. Code generation,
> migrations, lock files. Those are obligations with a trigger, not commands you
> run when you feel like it.

### L3-CAM-02

> I built that tool while making this course, because I needed it and it did
> not exist. It is free, it is open source, and the link is in the description.

### GFX-07
The product loop. Questions, browser, two files, your project, the agent. Then
the long curve sweeping back to the start.

---

# Lesson 4 · Build the product

Target 12 to 15 minutes. The longest lesson.

### L4-CAM-01

> One rule for this whole lesson. Build in phases, and every single phase has
> to end with something that actually runs.

### GFX-08
Step list, phases lighting one at a time.

### L4-VO-01

> Not "build the app." Build phase one, and stop. Look at it. Then phase two.
> Six small arguments instead of one big disappointment.

### L4-SCR-01
Phase 1. The skeleton, deployed, doing almost nothing.

### L4-VO-02

> That is deliberately boring, and it deploys. That is the whole point of phase
> one. Prove the ground holds before you build anything on it.

### L4-CAM-02

> Now the part most tutorials cut out. Watch what happens when it breaks.

### L4-SCR-02
The build failing. The real error, unedited.

### GFX-09
Terminal replay, retyped large enough to read on a phone.

### L4-VO-03

> That is not a mistake in this video. That is the rule working. The plan said
> a missing file must fail the build, and it did, and it named the file and
> both ways to fix it.

### L4-CAM-03

> Twice while building this, the agent told me I was wrong. Both times I
> overruled it, and both times I was right. Not because I am smarter than it.
> Because it was solving the problem in front of it, and I was thinking about
> what the whole thing is for.

### L4-VO-04

> An agent that is never overruled is not being used properly. It is very good
> at the thing directly in front of it. It does not know what your project is
> for unless you tell it, and even then it will argue with you.

---

# Lesson 5 · Test, deploy, and your turn

Target 8 to 10 minutes.

### L5-CAM-01

> Never trust the word "done" until you have clicked the thing yourself.

### L5-VO-01

> On another project of mine, an agent reported a finished build. The main
> button did nothing. My entire bug report was five words: done, generate
> project does nothing so far.
> There were two causes. One was a setting. The other was its own bug, and that
> one was worse: when the button failed, the app showed nothing at all. No
> error, no message. It just sat there.

### GFX-10
Before and after. A silent failure, then the same failure explaining itself.

### L5-VO-02

> A broken app that tells you what is broken is a five minute fix. A broken app
> that stays silent is your whole evening.

### L5-SCR-01
Deploying. The live URL. Clicking through it for real.

### L5-CAM-02

> So you have shipped something. It is live, anyone can open it. Now I have to
> be honest with you about what happens next.

### L5-SCR-02
Show the wall for real. Something breaking that this method alone does not fix.

### GFX-11
Board 6, the bricked-up doorway.

### L5-CAM-03

> The moment you add real users, a database, payments, or you open a project
> somebody else wrote, all of this gets harder. Everything you just learned
> still applies, but it is not enough on its own. That is what the full course
> is for, and it is linked below.

### L5-CAM-04

> One last thing. That tool you used in lesson three is open source and it
> needs more stacks added to it. Adding one is a single markdown file, it takes
> about thirty minutes, and it is a real contribution to a real project that
> other people use. Link is below. Go and put your name on something.

---

## Still to write

- Exact wording for the lesson 5 wall, once we know what actually breaks.
- Screen recording shot list, after the build is re-recorded clean.
- Element list for the graphics, generated from this file once the wording is
  locked.
