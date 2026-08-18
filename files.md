# Free course script

Three recording sessions, in this order. Do session 1 first and send it to me
before you do the rest, so we can fix anything about how it feels before you
have recorded forty minutes of it.

| Session | What | How |
| --- | --- | --- |
| 1 | 15 face lines | One video file per line. Rehearse as much as you like. |
| 2 | 14 read lines | One single take. Camera at anything, you are not on screen. |
| 3 | 8 screen recordings | Separate captures, after the build is finished. |

Motion graphics are mine. They are not in the sessions below, they are listed
at the end so you can see where everything lands.

---

# Session 1 · Face

**On camera. One video file per line, named exactly as the heading says.**

Take as many attempts as you want. Only send me the good one. If a line does
not sound like you, change the words. The meaning is what matters, not the
wording.

Do not record these in one take. Fifteen separate files:

```
L1-FACE-01.mov
L1-FACE-02.mov
...
L5-FACE-04.mov
```


## Lesson 1 · Set up your AI coding environment


### L1-FACE-01

> Hey. If you have ever wanted to build an app but you cannot code, this is
> for you. Over the next five lessons we are going to build a real product
> using an AI coding agent, and put it on the internet.
> You will not be typing code. You will be directing something that types it
> for you. The whole skill is knowing what to tell it, when to stop it, and how
> to catch it being wrong, and that is what I am going to teach you.


### L1-FACE-02

> I built a health platform that is running in Rwanda right now. I built a VPN.
> I built a payments app. I did all of it with AI agents and no engineering
> team. Everything I told them, and everything I stopped them doing, is what
> this course is.


### L1-FACE-03

> That is your workshop set up. In the next lesson we do the one thing that
> separates people who build with AI from people who just generate code with
> it.


## Lesson 2 · Plan before you code


### L2-FACE-01

> Here is the single move that changes everything. Before you let it write one
> line of code, you make it write the plan.


### L2-FACE-02

> Now the part almost nobody teaches, and it feels like extra work until the
> first time it saves you. You take that plan, you open a completely fresh
> chat, and you ask it what is wrong with it.


### L2-FACE-03

> But do not accept the review blindly either. Take those findings back to the
> first chat and say: tell me which of these are actually valid, and ignore any
> that do not have enough context about what we are building. Giving it
> permission to reject is what makes this real instead of theatre.


## Lesson 3 · Give the AI proper context


### L3-FACE-01

> Every time you open your agent, it starts knowing nothing about your project.
> Nothing. So it guesses.


### L3-FACE-02

> I built that tool while making this course, because I needed it and it did
> not exist. It is free, it is open source, and the link is in the description.


## Lesson 4 · Build the product


### L4-FACE-01

> One rule for this whole lesson. You are still not typing code. You are
> telling the agent what to build, one phase at a time, and every single phase
> has to end with something that actually runs before you ask for the next
> one.


### L4-FACE-02

> Now the part most tutorials cut out. Watch what happens when it breaks.


### L4-FACE-03

> Twice while building this, the agent told me I was wrong. Both times I
> overruled it, and both times I was right. Not because I am smarter than it.
> Because it was solving the problem in front of it, and I was thinking about
> what the whole thing is for.


## Lesson 5 · Test, deploy, and your turn


### L5-FACE-01

> Never trust the word "done" until you have clicked the thing yourself.


### L5-FACE-02

> So you have shipped something. It is live, anyone can open it. Now I have to
> be honest with you about what happens next.


### L5-FACE-03

> The moment you add real users, a database, payments, or you open a project
> somebody else wrote, all of this gets harder. Everything you just learned
> still applies, but it is not enough on its own. That is what the full course
> is for, and it is linked below.


### L5-FACE-04

> One last thing. That tool you used in lesson three is open source and it
> needs more stacks added to it. Adding one is a single markdown file, it takes
> about thirty minutes, and it is a real contribution to a real project that
> other people use. Link is below. Go and put your name on something.


---

# Session 2 · Read

**Not on camera. One single take, all five passages.** Point the camera at your
desk, a wall, anything. I strip the picture and keep the sound.

**You do not need to say any markers.** You are reading these word for word, so
I match the transcript against this document and find every piece exactly. Just
read.

**Pause for a breath between paragraphs.** Each paragraph becomes a separate
clip in the finished lesson, so a small gap makes the cut clean. You never have
to stop recording.

**Pause a little longer between lessons.** Two or three seconds.

One file, any name, any length:

```
ALL-READ.mov
```


## Lesson 1 · Set up your AI coding environment

There are two ways to use an AI coding agent. Most people open one and type
"build me an app." They get a pile of code. It runs. They cannot change it,
they cannot explain it, and they cannot tell whether it is any good.
This course teaches the other way.

Everything in this course is free. No API key, no credit card, no
subscription. If a step ever asks you for money, you are on the wrong step.


## Lesson 2 · Plan before you code

The plan is a markdown file. It lives in the project. It gets reviewed,
argued with, and revised. When code is finally written, it is written against
that file, and the comments in the code point back at it.
That one move changes your role from passenger to the person in charge.

Notice what was not asked for. No code. No files. Just a document.

A chat that has spent an hour defending its own choices cannot review them.
A fresh one has never seen your reasoning, so it argues with the file instead
of defending it.

On the project you are about to build, a fresh chat found five contradictions
in a plan that looked finished. The registry read itself. The document
claimed two different architectures at the same time. A promise had nothing
behind it.
On a bigger project of mine the same trick found sixteen problems, including
one where the document contradicted its own numbers. The chat that wrote it
had read those numbers a dozen times and never noticed.


## Lesson 3 · Give the AI proper context

Without a context file it spreads out across your project on probability. It
picks an answer and it sounds completely certain. With one, it goes straight
to the right place, because you told it.

Eight questions. They are not a survey. Every one of them is there because it
stopped a real mistake.
The one most people leave out is the third: what looks wrong but is
deliberate. Every project has decisions that look like bugs. Without that
section your agent will helpfully undo them.
And the eighth: what has to be re-run after certain changes. Code generation,
migrations, lock files. Those are obligations with a trigger, not commands you
run when you feel like it.


## Lesson 4 · Build the product

Not "build the app." Build phase one, and stop. Look at it. Then phase two.
Six small arguments instead of one big disappointment.

That is deliberately boring, and it deploys. That is the whole point of phase
one. Prove the ground holds before you build anything on it.

That is not a mistake in this video. That is the rule working. The plan said
a missing file must fail the build, and it did, and it named the file and
both ways to fix it.

An agent that is never overruled is not being used properly. It is very good
at the thing directly in front of it. It does not know what your project is
for unless you tell it, and even then it will argue with you.


## Lesson 5 · Test, deploy, and your turn

On another project of mine, an agent reported a finished build. The main
button did nothing. My entire bug report was five words: done, generate
project does nothing so far.
There were two causes. One was a setting. The other was its own bug, and that
one was worse: when the button failed, the app showed nothing at all. No
error, no message. It just sat there.

A broken app that tells you what is broken is a five minute fix. A broken app
that stays silent is your whole evening.
---

---

# Session 3 · Screen recordings

**After the build is finished, not while you are building.** Re-record each one
clean and short. Nobody wants to watch you wait for an agent to think.

Separate files, named as the headings say.


## Lesson 1 · Set up your AI coding environment


### L1-SCREEN-01

Installing VS Code. Installing the agent. The first version command that proves
it is working.


## Lesson 2 · Plan before you code


### L2-SCREEN-01

Asking the agent to write PROJECT.md. Not code. A document.


### L2-SCREEN-02

The real review. The actual findings, unedited.


## Lesson 3 · Give the AI proper context


### L3-SCREEN-01

Open agentfile. Answer the eight questions. Download the two files. Drop them
into the project.


## Lesson 4 · Build the product


### L4-SCREEN-01

Phase 1. The skeleton, deployed, doing almost nothing.


### L4-SCREEN-02

The build failing. The real error, unedited.


## Lesson 5 · Test, deploy, and your turn


### L5-SCREEN-01

Deploying. The live URL. Clicking through it for real.


### L5-SCREEN-02

Show the wall for real. Something breaking that this method alone does not fix.


---

# Reference · What goes where

You do not need this while recording. It is how the pieces get assembled, so
you can see the shape of each finished lesson.


## Lesson 1 · Set up your AI coding environment

- **L1-FACE-01** Hey. If you have ever wanted to build an app but you are not a developer,
- **L1-FACE-02** I built a health platform that is running in Rwanda right now. I built a VPN.
- **GFX-01** Title card. "Build real software with AI." Over L1-READ-01.
- **L1-READ-01** There are two ways to use an AI coding agent. Most people open one and type
- **GFX-02** The two roads. Top road scribbles into a tangle. Bottom road builds in phases.
- **L1-SCREEN-01** Installing VS Code. Installing the agent. The first version command that prove
- **L1-READ-02** Everything in this course is free. No API key, no credit card, no
- **L1-FACE-03** That is your workshop set up. In the next lesson we do the one thing that

## Lesson 2 · Plan before you code

- **L2-FACE-01** Here is the single move that changes everything. Before you let it write one
- **GFX-03** Pull quote, held still.
- **L2-READ-01** The plan is a markdown file. It lives in the project. It gets reviewed,
- **L2-SCREEN-01** Asking the agent to write PROJECT.md. Not code. A document.
- **L2-READ-02** Notice what was not asked for. No code. No files. Just a document.
- **L2-FACE-02** Now the part almost nobody teaches, and it feels like extra work until the
- **GFX-04** The fresh chat diagram. Chat A loops back on itself uselessly. The teal path
- **L2-READ-03** A chat that has spent an hour defending its own choices cannot review them.
- **L2-SCREEN-02** The real review. The actual findings, unedited.
- **L2-READ-04** On the project you are about to build, a fresh chat found five contradictions
- **L2-FACE-03** But do not accept the review blindly either. Take those findings back to the

## Lesson 3 · Give the AI proper context

- **L3-FACE-01** Every time you open your agent, it starts knowing nothing about your project.
- **GFX-05** Guessing versus being told. Dashed arrows fire at the wrong folders. Then one
- **L3-READ-01** Without a context file it spreads out across your project on probability. It
- **GFX-06** Term definition. "Context file. A markdown file your coding agent reads before
- **L3-SCREEN-01** Open agentfile. Answer the eight questions. Download the two files. Drop them
- **L3-READ-02** Eight questions. They are not a survey. Every one of them is there because it
- **L3-FACE-02** I built that tool while making this course, because I needed it and it did
- **GFX-07** The product loop. Questions, browser, two files, your project, the agent. Then

## Lesson 4 · Build the product

- **L4-FACE-01** One rule for this whole lesson. Build in phases, and every single phase has
- **GFX-08** Step list, phases lighting one at a time.
- **L4-READ-01** Not "build the app." Build phase one, and stop. Look at it. Then phase two.
- **L4-SCREEN-01** Phase 1. The skeleton, deployed, doing almost nothing.
- **L4-READ-02** That is deliberately boring, and it deploys. That is the whole point of phase
- **L4-FACE-02** Now the part most tutorials cut out. Watch what happens when it breaks.
- **L4-SCREEN-02** The build failing. The real error, unedited.
- **GFX-09** Terminal replay, retyped large enough to read on a phone.
- **L4-READ-03** That is not a mistake in this video. That is the rule working. The plan said
- **L4-FACE-03** Twice while building this, the agent told me I was wrong. Both times I
- **L4-READ-04** An agent that is never overruled is not being used properly. It is very good

## Lesson 5 · Test, deploy, and your turn

- **L5-FACE-01** Never trust the word "done" until you have clicked the thing yourself.
- **L5-READ-01** On another project of mine, an agent reported a finished build. The main
- **GFX-10** Before and after. A silent failure, then the same failure explaining itself.
- **L5-READ-02** A broken app that tells you what is broken is a five minute fix. A broken app
- **L5-SCREEN-01** Deploying. The live URL. Clicking through it for real.
- **L5-FACE-02** So you have shipped something. It is live, anyone can open it. Now I have to
- **L5-SCREEN-02** Show the wall for real. Something breaking that this method alone does not fix
- **GFX-11** Board 6, the bricked-up doorway.
- **L5-FACE-03** The moment you add real users, a database, payments, or you open a project
- **L5-FACE-04** One last thing. That tool you used in lesson three is open source and it


---

## Still to write

- Exact wording for the lesson 5 wall, once we know what actually breaks.
- Element list for the graphics, generated from this file once the wording is
  locked.
