# Lesson 4

**Title:** Core features: planning them, building one at a time, testing as you go

**Summary:** Your app can log people in and it does nothing yet. This lesson
turns the idea into working features. How to break a product into pieces and
pick the order, how to describe one piece well enough that the AI builds what
you meant, and how to check each one before moving to the next.

**Length:** 75 to 90 minutes.

**Note on the demo:** the app on screen is a file sharing tool. Every time you
show a feature, say the general version out loud first, then show yours. People
watching are building other things.

---

## Running order

### 1. New machine (0:00)

Clone from GitHub on the MacBook, install, run. The app comes up.

Point: the code was never on the laptop. This is why lesson 2 mattered.

### 2. What we are building today (0:05)

Open the plan you wrote in lesson 1. Read it back.

Say the general rule: **a product is not one thing, it is a list of features,
and you build them one at a time.** Then show your list on screen.

### 3. Picking the order (0:08)

Do not build in the order you thought of them. Build in the order that lets you
use the app.

Ask the agent:

> Here is my product plan. List the features in the order I should build them,
> so that after each one I have something I can actually use. Say why.

Show the answer. Disagree with part of it out loud if you do. The point is that
you decide, not it.

### 4. Describing one feature so you get what you meant (0:15)

This is the main skill of the lesson. Slow down here.

A bad ask: *"add file uploads."*

A good ask says what it does, what it refuses, and what the person sees:

> Add file upload. Any file up to 50MB. Reject bigger ones with a message that
> says the limit. Show progress while it uploads. If it fails, keep the file
> selected so they can retry without picking it again.

Say the general rule: **the AI fills in anything you leave out, and it fills it
in with whatever is most common, not whatever you wanted.** Every sentence you
add is a decision you are taking back off it.

Then let it build. Watch it work.

### 5. Test it before you move on (0:25)

Two ways, and do both.

Use it yourself, in the browser, right now. Upload something. Upload something
too big. Cancel halfway.

Then Playwright, which you installed last lesson:

> Using Playwright, upload a small file, then try a 60MB file, and tell me what
> happened each time.

Say why both: **you find the things that feel wrong, it finds the things you
would not have bothered to try again.**

### 6. Commit it (0:32)

Small commit, clear message, push. Say the rule: **one working feature, one
commit.** If the next one goes badly you can get back to here.

### 7. Now the same loop again, faster (0:35)

Second feature. Same four steps: describe it properly, build, test, commit.
Narrate less this time. Let people see the rhythm.

Third feature. Faster again.

By now they should be able to say the loop back to you.

### 8. When it builds the wrong thing (0:55)

This will happen naturally. Do not fake it, but when it does, stop and stay on
it, because it is the most useful part of the video.

Read what it built. Work out which sentence you left out. Say that out loud.
Then add the missing sentence and ask again.

Say the general rule: **when it builds the wrong thing, it is usually answering
a question you did not know you were asking.**

### 9. The full flow, end to end (1:05)

Everything is built. Now walk the whole product as a new user, out loud, in the
browser. Then have Playwright do the same run.

Point: features that each work on their own can still fail together.

### 10. Where we are (1:15)

Look back at the plan from lesson 1 and tick off what is done.

Next lesson: connecting other services to it.

---

## Before you press record

- [ ] Push from the PC, confirm the commit is on GitHub.
- [ ] Clone and run on the MacBook once, off camera.
- [ ] Restart the agent so Playwright is live.
- [ ] Have your lesson 1 product plan open in a tab.
- [ ] A small test file and a 60MB test file on the desktop.
