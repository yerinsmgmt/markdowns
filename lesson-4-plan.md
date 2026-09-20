# Lesson 4

**Title:** Teaching your agent to check its own work

**Description:** An agent that writes code and never runs it is guessing. In
this lesson you set your project up so the agent proves things instead: it
runs the checks, it opens your app and uses it like a person, and it reviews
what it wrote. Works whether you are building for the web or for mobile.

**Length:** 60 to 75 minutes.

**At the end they can:** make any agent, on any project, check its own work
before saying it is done.

---

## The idea, said once at the start

Your app works. You clicked it yourself. That is one person, on one machine,
on the happy path.

There are three ways to know something works, and you want all three:

1. **The checks.** Does it compile, does it lint, does it build, do the tests pass.
2. **Using it.** Open the app, click the buttons, like a person would.
3. **Reading it.** Someone looks at the code and says what is wrong with it.

You can do all three by hand. This lesson is about making your agent do them,
so they happen every time instead of when you remember.

---

## Running order

### 1. New machine (0:00)

Clone from GitHub on the MacBook, `npm install`, `npm run dev`. It runs.

Say the point out loud: this is why lesson 2 mattered. The code was never on
the laptop, it was on GitHub, and a laptop is just somewhere to work.

### 2. What this course is (0:05)

> This course teaches you to build and ship your own product. It is not
> interview preparation. If you want a job at a company you also need
> algorithms and interview practice, and the free links are on the course page.

### 3. Level one: the checks your project already has (0:07)

Every project has commands that tell you if it is broken. Most people never
run them. Find yours and run them once, on camera.

**Node / Next.js**
```
npx tsc --noEmit      # types
npm run lint          # style and common mistakes
npm run build         # does it actually build
npm test              # tests, if you have any
```

**Flutter**
```
flutter analyze
flutter test
flutter build apk --debug
```

**Python**
```
ruff check .
mypy .
pytest
```

Then the part that makes it stick. Ask the agent:

> What commands does this project have for checking the code, and what does
> each one catch?

### 4. Make the agent run them without being asked (0:14)

This is the most useful five minutes in the lesson.

Your agent reads an instruction file at the top of the project every time it
starts. Claude Code reads `CLAUDE.md`. Codex reads `AGENTS.md`. Put the
commands in there and it stops being something you remember.

> Add a section to CLAUDE.md listing the check commands for this project, and
> say that you must run them after any change and fix what they report before
> telling me you are done.

Then make a change and watch it run them on its own.

### 5. Level two: the agent uses the app (0:22)

Reading code and believing it is not the same as opening the app. This is
where you pick a tool, and the tool depends on what you are building.

**Building for the web → Playwright**

You installed this in lesson 3. Restart your agent so it is live, then:

> Using Playwright, open the app, sign up a new account, log in, upload a
> file, create a share link, open that link in a fresh browser, and tell me
> what happened at each step.

Let it run. Do not talk over it. Let people watch the browser move.

**Building a mobile app → Maestro**

Same idea, on a phone or simulator. Maestro works with Flutter, React Native
and native iOS and Android, all with the same commands.

Install it. Needs Java 17 or newer.

```
# macOS or Linux
curl -fsSL "https://get.maestro.mobile.dev" | bash

# check it
maestro --help
```

On Windows, download the release from GitHub, unzip to `C:\maestro`, and add
`C:\maestro\bin` to your PATH.

Then connect it to your agent. The MCP server is already inside the CLI, so
there is nothing else to install:

```
claude mcp add maestro -- maestro mcp
```

Start your simulator or plug in a phone, restart your agent, and ask for the
same thing you asked Playwright for. It writes the test, runs it on the
device, and fixes it when it fails.

**Neither of those?** The question to ask your agent is always the same shape:

> I am building with [your stack]. What tool would let you open my app and use
> it the way a person does, and is there an MCP server for it?

### 6. Level three: the agent reads the code (0:40)

Three prompts. Run them in this order, because each one finds a different kind
of thing.

**Review**
> Review the code you wrote today. What would you change before anybody else
> depends on it?

**Audit**
> Go through this project as a security reviewer. What would you not ship?

**Document**
> Write down what you found, and what we decided to do about each one, in a
> markdown file in the project.

That last one matters more than it looks. A list of known problems that lives
in the repository is worth more than a clean report, because it is the thing
you pick up next week.

### 7. Now you test it yourself (0:55)

Close the laptop lid on the agent for a minute and use your own app. Sign up
with a real email. Upload something. Send yourself the link. Open it on your
phone.

Anything that surprises you, hand back to the agent and watch it fixed.

### 8. Recap (1:10)

The three levels. The instruction file that makes level one automatic. The
tool for your stack that makes level two possible.

---

## Before you press record

- [ ] `git push` on the PC. Check the commit is on github.com/Creovine-Labs/simbai.
- [ ] Clone and run it on the MacBook once, off camera, so you know it works.
- [ ] Restart Claude Code so Playwright MCP is live.
- [ ] Install Maestro and a simulator, off camera, so the demo is quick.
- [ ] Have a small PDF on the desktop to upload.
