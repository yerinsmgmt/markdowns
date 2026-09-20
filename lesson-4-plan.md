# Lesson 4 — shooting plan

**Title:** It works. That does not mean it is right.

**Length:** 60 to 75 minutes. One topic.

**What this lesson actually teaches:** how to find out what is wrong with
something you just built, when nobody is there to tell you. Not three fixes.
Three *questions*, which work on any project, forever.

The app is live. People can sign up and log in. It looks finished. This lesson
is what a real engineer does next, which is not building the next feature.

---

## Contents

1. [Before you press record](#before)
2. [The three questions (this is the lesson)](#questions)
3. [Running order](#order)
4. [Exact prompts, in order](#prompts)
5. [Read this before recording, do not read it on camera](#private)
6. [What to say about jobs](#jobs)
7. [Two habits to watch](#habits)

---

<a id="before"></a>

## 1. Before you press record

- [ ] On the **PC**: `git push`. Confirm on github.com/Creovine-Labs/simbai
      that your newest commit is there.
- [ ] On the **MacBook**: clone, `npm install`, `npm run dev`. Check it runs.
      Then delete the folder and do it again on camera. All the teaching value,
      none of the risk of a live setup fighting you.
- [ ] Restart Claude Code so Playwright MCP is actually live.
- [ ] Names decided in advance, do not invent these while talking:
      database **Vercel Postgres**, branch **main**, test password **test1234**.
- [ ] Have a small PDF on the desktop ready to upload.
- [ ] Have the gaps file from lesson 3 open.

---

<a id="questions"></a>

## 2. The three questions

Teach these as a habit, by name. Say them out loud before you type each one.
This is the part a learner writes down.

> **Question 1. Does the code do what the screen promises?**
> A button that is drawn is not a button that works. The screen is a promise
> to the user, and the code either keeps it or it does not.

> **Question 2. What breaks when this succeeds?**
> Everything works with one user. Ask what happens with fifty at once. Most
> things built quickly are built for an audience of one.

> **Question 3. What are we sending to the browser that we should not be?**
> Anything the browser receives, the user can read. Always. Open the network
> tab and look, do not assume.

Then say the important part: **you do not need to know the answer to ask the
question.** That is the whole point. You ask, the agent investigates, and you
read what it found and decide.

---

<a id="order"></a>

## 3. Running order

| Time | What happens |
|---|---|
| 0:00 | New machine. Clone from GitHub, install, run. It works. Lesson 2 paying off. |
| 0:05 | One honest minute on what this course is. Section 6. |
| 0:07 | Restart Claude Code. Confirm Playwright MCP is live. Closes lesson 3. |
| 0:10 | "The app works. Here is what I do before building anything else." Teach the three questions. |
| 0:15 | **Question 1** on the share link flow. Let the agent investigate. Read what it says out loud. |
| 0:22 | Prove it with Playwright, live. This is the moment of the lesson. |
| 0:30 | Fix it. To-do list first, as in lesson 3. |
| 0:42 | **Question 3** on the same flow. Open the network tab together and look. |
| 0:50 | **Question 2** on how the app stores data. |
| 0:58 | Fix that. To-do list first. |
| 1:08 | Playwright walks the whole thing again and proves it. |
| 1:12 | Recap: the three questions, and what you now have. |

---

<a id="prompts"></a>

## 4. Exact prompts, in order

Say **why** before each one, then type it.

**Question 1, on the share link feature:**

> Walk through the share link feature end to end, from creating a link to a
> stranger opening it. Compare what the interface offers the user against what
> the code actually does. List anything the screen promises that the code does
> not deliver. Do not change anything yet.

**Then prove whatever it says, with Playwright, before you fix it:**

> Using Playwright: create a share link with the password `test1234`, then open
> that link in a fresh browser context and try to view the file without
> entering the password. Tell me exactly what happened.

Let it run. Do not narrate over it. Let people watch the browser.

**Fixing it:**

> Write a to-do list, then fix it. After each item, use Playwright to confirm
> the behaviour changed.

**Question 3, same feature:**

> Open the public share endpoint. List every field it sends to the browser.
> For each one, tell me why a person who is not logged in needs it.

Then open the network tab in the browser yourself and show them the response.
Seeing it is worth more than being told.

**Question 2, on storage:**

> We are about to add more features. Before we do: if fifty people used this
> app at the same time right now, what would go wrong? Look at how data is
> stored and be specific.

**Then:**

> Move that to Vercel Postgres. Write a to-do list first and work through it.
> Keep the existing API routes working so the front end does not change.

---

<a id="private"></a>

## 5. Read this before recording. Do not read it on camera.

This is your safety net so you are never stuck, not a script. If the agent
finds these on its own, which it should, let it, and act on what it says.

I read the repository. There are three real problems and they map to the three
questions exactly. That is why these questions and not others.

**Question 1 will find this.** `web/src/app/page.tsx` draws a field labelled
"Optional password" and saves what the user types. `validateShareLink` in
`web/src/lib/server-store.ts` then checks four things: link exists, file
exists, link is enabled, link is not expired. The password is never compared.
So the lock is drawn and never fitted, and Playwright will walk straight in.

**Question 3 will find this.** That same function returns
`{ ok: true, link, file }`, and the route sends it straight to the browser.
`link` contains `password`. The app does not check the password and then
publishes it.

**Question 2 will find this.** `server-store.ts` keeps every user, file, link,
session and tracking event in **one JSON file**. Two people at once read it,
change their part, and write it back; the second erases the first. And near the
top of that file, when `VERCEL === "1"` it writes to `os.tmpdir()`, which is
wiped between requests, so without Vercel Blob configured everything a user
does disappears.

**If the agent misses one**, nudge with the smallest hint that keeps it honest,
in this order:

1. "Look at `validateShareLink` specifically."
2. "What does the link form let the user set, and where is that used?"
3. "Read the type `ShareLink`. Is every field on it used?"

Never say "the password is not checked". Ask a smaller question instead. The
learner is watching how you corner it.

---

<a id="jobs"></a>

## 6. What to say about jobs (one minute, near the start)

> Quick thing before we start. This course teaches you to build and ship your
> own product. That is what you have at the end: something live that people can
> use. It is not interview preparation. If what you want is a job at a company,
> you will also need data structures, algorithms and interview practice, and
> there are free places for that. I have put the links on the course page. Both
> are worth doing. This one is about building the thing.

---

<a id="habits"></a>

## 7. Two habits to watch

**Decide names before you say them.** In lesson 3 you made a folder called
"keys" and changed it mid-sentence to "gitignore folder". Anyone following
along now has a folder with the wrong name. Your names are in section 1.

**"Like".** 1.4 times a minute in lesson 1, 3.0 in lesson 3, which is once
every twenty seconds. Nothing else about your delivery drifted, so this is the
only one worth thinking about. Lesson 1 proves you can do it.

---

## What a learner has at the end

- Three questions they can ask about any project they ever build
- Their app running on a second machine, pulled from GitHub
- A share link whose password is actually enforced
- A public endpoint that does not hand out secrets
- A real database, so two users do not erase each other
- An agent that tests the app by using it, not by reading it
