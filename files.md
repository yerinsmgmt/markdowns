# AI Software Engineering, lesson 2

Topics to talk about. Not a script. The order is the argument, so keep the
order even if you say all of it differently.

## Where lesson 1 left you, and why that is not finished

Lesson 1 ends with something running on your own machine and nowhere else.
That is a real achievement and it is also the most fragile state software can
be in. One deleted folder, one laptop that will not boot, and twelve hours of
work is gone with nothing to show anybody.

Open with that, because it is the reason for everything in this lesson.

## First, fix what the review already found

The review at the end of lesson 1 found five issues. One of them was that the
PDF page count was hardcoded to eight pages, so every upload claimed to have
eight pages whatever it actually had.

Start the lesson by fixing them, on camera. Two reasons, and say both:

- Never build on top of something you already know is broken. It is cheaper
  now than after three more features are sitting on it.
- It shows what the validate habit is *for*. In lesson 1 it looked like extra
  work with no payoff. Here is the payoff.

## Saving your work

**Git and GitHub are two different things.** People use the words as if they
were one. Git is the thing on your computer that remembers every version.
GitHub is a website that holds a copy. You can have one without the other.
Say it once, plainly, and move on. Do not teach Git properly, teach the four
words they will actually see: repository, commit, push, pull.

**A commit is an undo button you set yourself.** This is the framing that
makes it stick for someone who does not code. Before you let the AI change
anything big, commit. If the AI wrecks it, you go back to the last commit and
nothing is lost. Without that you are trusting an agent with no way back.

**Let the AI do the work.** They do not need to memorise commands. Show what
you actually type: tell the agent to set up the repository and make the first
commit. Then show the same thing on GitHub in the browser, so they can see the
two halves are connected.

**Private, and why.** Public means the whole internet can read it. Show the
toggle. Say plainly that a half-built product with your business logic in it
is not something you publish by accident.

## The one that ends careers: secrets

This deserves its own segment and its own slow pace.

An API key in your code, pushed to GitHub, is scraped by bots within minutes.
People have woken up to five-figure cloud bills. Cover:

- What a secret looks like: keys, tokens, passwords, connection strings.
- `.gitignore` and the `.env` file. Why the file stays on your machine.
- What to actually tell the AI: never put a key in the code, always read it
  from the environment.
- Deleting a key from your code does not remove it from history. If you push
  one, you rotate it, you do not just delete it.

Say the last one twice. It is the part everyone gets wrong.

## Branches, only as much as they need

One idea: a branch lets you try something without breaking the thing that
already works. If it works out you keep it, if it does not you throw the
branch away. Do not teach merge conflicts. They do not need them yet and it
will scare people off.

## Organizations on GitHub

Be honest here: most people watching do not need one yet. Explain what it is
in one line, when it starts to matter (a team, a company, work you want to
keep separate from your name), and move on. Do not spend ten minutes on
something a solo builder will not touch for six months.

## Putting it online

**Connect the repository to Vercel and deploy.** This is the moment of the
lesson. Get to a real URL on the open internet and open it on your phone on
camera. That is the shot people will remember.

**Then the thing that will bite them.** It worked on your machine and it is
broken on the internet, and the reason is almost always environment
variables. The keys live on your laptop in a file you deliberately did not
upload, so the deployed copy has none. Show adding them in Vercel. This is
the single most common first-deploy failure and it will save them an evening.

**Failed builds are normal.** Show one. Show where the log is. Show yourself
copying the log into the AI and letting it fix it. What you are teaching is
that a red failure is information, not a wall.

**Your own domain.** Short segment. Buying one, pointing it, waiting for it.
Say the wait is normal so nobody thinks it is broken.

## GitHub Actions, kept small

One sentence: it runs something automatically every time you push. Then give
them the only one a beginner needs, which is running the build on every push
so a broken deploy is caught before their users find it. Anything more than
that belongs in a later lesson.

## What "backend" actually means, and whether they need one

You told people in lesson 1 not to build a backend yet. Close that loop here
or it stays an unexplained rule.

Explain it as: where the data lives and who is allowed to see it. Then be
honest about when it becomes unavoidable, which is roughly when more than one
person uses the thing and their data has to stay theirs. Show the smallest
version that works rather than the architecture diagram.

## Making it look right

Fine-tuning the UI, and responsive on a phone. Best taught by showing the app
looking broken on a phone first, then fixing it, rather than by describing
what responsive means.

Worth saying out loud: this is the part where taste matters and the AI is
only as good as what you tell it. "Make it look better" gets you nothing.
Point at a specific thing and say what is wrong with it.

## Close

What they can now do that they could not before: their work is saved, it is
online, other people can use it, and they can change it without fear because
they can always go back.

Then what lesson 3 covers.

---

## An honest note on length

Everything above is more than one lesson. Lesson 1 was 66 minutes and that was
already long. Cramming Git, secrets, deployment, Actions, backend and UI into
one video gives you a two hour lesson that nobody finishes.

Suggested split:

- **Lesson 2, saved and shipped.** Fix the review findings, Git and GitHub,
  private, secrets and `.gitignore`, commits as an undo button, connect to
  Vercel, environment variables, first live URL, custom domain. Ends with the
  thing on the internet. Around 45 to 55 minutes.
- **Lesson 3, making it real.** Branches, GitHub Actions, what a backend is
  and when you need one, the UI and responsive pass, what breaks after launch.

The split also gives lesson 2 a clean promise you can put on the page: you
start with something on your laptop and you end with a link you can send to
anybody.
