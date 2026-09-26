# Launch posts for trackline

What to post, where, and in what order. Researched 2026-09-26.

Links used in the posts:

- GitHub: https://github.com/yerinsabraham/trackline
- Site: https://trackline.dev
- Write-up: https://yerinsabraham.com/engineering/nothing-notices-when-an-agent-drifts
- X: @yerinsabraham (only where marked; on HN and Reddit it reads as promo)

---

## Read this first (5 rules that came out of the research)

1. **Hacker News bans AI-written text, even AI-edited.** Since March 2026. dang's words:
   "Write your text by hand. Don't use an LLM to generate any of it (not even a
   tiny bit, including to edit or spruce it up)." So for HN below you get the
   facts and the order to say them in. Type it yourself.
2. **awesome-claude-code bans AI-written submissions.** Same: facts only, you type it.
3. **r/cursor and r/mcp ban "AI slop".** The Reddit drafts below are a starting
   point. Read each one aloud and change anything that isn't how you talk before
   you post. Reddit mods and readers are hunting for AI text right now.
4. **Reply to every comment yourself, by hand, fast.** Generated replies get
   called out. "Good catch, fixing it" is a great reply.
5. **Never ask anyone to upvote.** r/ClaudeAI bans permanently for it, and HN
   penalises it.

Things that look AI-written and get posts buried: em dashes, "excited to
announce", "game-changer", "seamless", "robust", "leverage", emoji bullets,
headings in a short post, "it's not X, it's Y", everything in threes.

What works everywhere: one real example, the real numbers, and saying plainly
what it can't do.

---

## Order

| When | Where |
|---|---|
| Day 1 | r/ClaudeCode |
| Day 2 | r/SideProject |
| Day 3 | r/ClaudeAI (needs 50+ karma on your account) |
| Day 4 | r/mcp, and the weekly threads in r/cursor, r/AI_Agents, r/ChatGPTCoding |
| Day 5 | Cursor forum |
| Next Tue, 9am US Eastern (3pm Lagos) | Show HN |
| Any day | mcp.so, Changelog, Console.dev, dev.to |
| After the npm fix below | Glama, then awesome-mcp-servers, then official MCP Registry |
| 1–2 weeks after HN | Product Hunt |
| 14+ days after first commit (done) | awesome-claude-code |

---

## 1. r/ClaudeCode

**Link:** https://www.reddit.com/r/ClaudeCode/submit
**Flair:** Showcase
**Rule:** standalone project posts must say what you built, how Claude Code was
used, and what you learned. Short posts get sent to the weekly showcase thread.

**Title:**

```
I built a hook that stops Claude Code when it drifts off the task, and hands the rule back so it fixes itself
```

**Body:**

```
I build an AI support product (Lira) from Lagos and I use Claude Code every day. The thing that kept biting me wasn't bad code. It was Claude doing things I never asked for: touching files outside the task, adding a package, editing something CLAUDE.md said not to touch. Nothing fails when that happens. The build stays green.

So I built trackline. It runs as a Claude Code hook and checks every tool call against what you actually asked for and your project's rules. Five checks right now:

- off-limits: writes to .env, keys, credential files
- dependency-added: a package you never mentioned
- scope: a write into an area your request didn't mention
- diff-size: a change way bigger than the request
- repetition: the same action over and over (usually means it's stuck)

By default it only writes things down and never interrupts you. You can turn on "auto" for off-limits, and then it blocks the action and tells Claude why. The question I had to answer before building any of this was: does Claude actually correct itself when a hook blocks it and explains? I tested it. 11 out of 11 times it did (Claude Code and Codex), and 0 times did it write the forbidden file.

What I learned:

- The block message matters. "secrets.env is off limits, put it in config.local.json instead" works. I haven't tested a bare "no" yet.
- Speed matters more than I expected because it runs on every single tool call. My first version was Node: 88ms per call. Rewrote the hook in Go: 6.5ms.
- False alarms kill a tool like this on day one, so every check stays quiet unless it can name exactly what it saw. 0 false alarms across 23 ordinary actions in my testing.

What it can't do yet: the scope check stays silent if your request doesn't name a file or folder, and it only partly understands shell commands (installs, rm, mv, cp, redirects, sed -i).

I built most of it with Claude Code itself, which was a bit funny given what it's for.

Free and open source (Apache-2.0):

npm install -g trackline
cd your-project
trackline init

GitHub: https://github.com/yerinsabraham/trackline

Would love to hear what drift you see most often. That decides which check I build next.
```

---

## 2. r/SideProject

**Link:** https://www.reddit.com/r/SideProject/submit
**Rule:** title format is `[Project name] - [Short description]`. The most
promotion-friendly sub. Tell the story, say what stage it's at, ask one question.

**Title:**

```
trackline - watches your AI coding agent and tells you when it stops doing what you asked
```

**Body:**

```
Solo dev from Lagos. I've been building this for about three weeks next to my main job, which is building an AI support product.

The problem: AI coding agents (Claude Code, Codex, Cursor) don't crash when they go off task. They quietly edit files you never mentioned, add packages nobody asked for, or ignore the rules file they read an hour ago. Your tests still pass, because tests check the code works, not that it's the code you asked for.

trackline sits beside the agent through its hooks, checks each action against your request and your project rules, and either writes it down, stops and asks you, or blocks it and tells the agent why so it fixes itself. It works the same across all three agents, which was the whole point. I didn't want a different safety tool per vendor.

Where it's at: v0.6 on npm, open source. The local watcher is solid. Production trace monitoring exists but hasn't met real traffic yet. There's also an optional phone app for approving blocked actions, which I'm still testing.

Try it: npm install -g trackline, then trackline init in a project.

Site: https://trackline.dev
GitHub: https://github.com/yerinsabraham/trackline

One question: if you use a coding agent, what's the thing it does that annoys you most?
```

---

## 3. r/ClaudeAI

**Link:** https://www.reddit.com/r/ClaudeAI/submit
**Flair:** Built with Claude
**Rules:** you need more than 50 karma. You must say you built it, how Claude
helped, and that it's free. Keep promotional language minimal. A screenshot
helps: use the terminal output of a `trackline show` replay.

**Title:**

```
Built a free tool that notices when Claude Code ignores your CLAUDE.md, and can make it fix itself
```

**Body:**

```
There's an open issue on Anthropic's repo titled "Claude ignores explicit CLAUDE.md instructions while claiming to understand them." That's been my experience too, especially in long sessions. The rules are read once, then they drift out of focus.

I built trackline to catch it. It's a Claude Code hook that checks every tool call against your request and your project's rules. In its default mode it just records what it saw (trackline status shows you). You can switch a check to block, and then Claude gets told why and corrects itself. I tested that before building on it: 11/11 corrections.

How Claude helped: most of the code was written with Claude Code, and I used it to run the experiments that decided the design (the self-correction test, and a latency test that made me move the hook from Node to Go, 88ms down to 6.5ms per tool call).

Free and open source (Apache-2.0). Also works with Codex and Cursor.

npm install -g trackline && trackline init

https://github.com/yerinsabraham/trackline

[attach screenshot of a trackline show replay]
```

---

## 4. r/mcp

**Link:** https://www.reddit.com/r/mcp/submit
**Flair:** showcase
**Rules:** self-promotion is fine if you say it's yours. **Security-scare framing
is a ban trigger here**, so keep it plain. Be upfront that MCP mode only advises.

**Title:**

```
trackline mcp: an MCP server an agent can ask before it acts (check_action, get_rules)
```

**Body:**

```
I made this, sharing it here.

trackline is a tool that checks whether a coding agent's actions still match the task and the project's rules. For Claude Code, Codex and Cursor it runs as a hook and can actually block. For every other MCP client, I added trackline mcp, which exposes two tools:

- get_rules: returns the project's rules so the agent has them in context
- check_action: the agent describes what it's about to do and gets a verdict with the reason

The honest limit: over MCP the agent decides whether to ask. An agent that doesn't call check_action isn't watched, so this is advisory, not enforcement. It widens reach to agents without hooks. It doesn't replace hooks.

Runs locally over stdio, no account, no API key.

npm install -g trackline
trackline mcp

https://github.com/yerinsabraham/trackline

Curious if anyone has found a reliable way to get agents to call a "check first" tool consistently. That's the weak point.
```

---

## 5. Weekly threads (r/cursor, r/AI_Agents, r/ChatGPTCoding)

These subs don't allow standalone project posts (r/ChatGPTCoding is
approved-posters only). Find the pinned weekly showcase / project thread and
post a comment.

- r/cursor: https://www.reddit.com/r/cursor/ ("Weekly Cursor Project Showcase Thread")
- r/AI_Agents: https://www.reddit.com/r/AI_Agents/ ("Weekly Thread: Project Display")
- r/ChatGPTCoding: https://www.reddit.com/r/ChatGPTCoding/ (weekly self-promotion thread)

**Comment for r/cursor:**

```
trackline: checks whether the Cursor agent is still doing what you asked. Runs through Cursor's hooks, flags writes to .env/keys, packages you didn't ask for, writes outside the area you mentioned, huge diffs, and loops. Default mode only records; you can make it block, and it tells the agent why. One caveat: start the agent inside your project or Cursor doesn't load the project hooks. Free, open source.

npm install -g trackline && trackline init --host cursor
https://github.com/yerinsabraham/trackline
```

**Comment for r/AI_Agents and r/ChatGPTCoding:**

```
trackline: an open-source watcher for coding agents (Claude Code, Codex, Cursor, or any MCP client). It checks each action against the task and your project rules and can block with a reason so the agent corrects itself (11/11 in my tests). Hook is written in Go so it adds about 6.5ms per tool call.

https://github.com/yerinsabraham/trackline
```

---

## 6. Cursor forum

**Link:** https://forum.cursor.com/c/showcase/built-for-cursor/
**Rule:** "Include setup instructions and a link to the repo or download!"

**Title:**

```
trackline: see when the Cursor agent goes off task, and optionally stop it
```

**Body:**

```
I built trackline to answer one question while an agent works: is it still doing what I asked?

It plugs into Cursor's hooks and checks each action against your request and your project rules. It flags writes to secrets (.env, keys), packages you never named, writes outside the area you mentioned, changes far bigger than the request, and the same action repeated (stuck agent).

Setup:

npm install -g trackline
cd your-project
trackline init --host cursor

Then make one edit with the agent and run trackline status to confirm the hook ran.

Two things to know:
- Start the agent inside the project folder. Cursor loads project hooks from the project, so an agent started elsewhere isn't watched.
- Blocking in Cursor is newer than in Claude Code and Codex. In my one live run it blocked correctly, didn't retry, and told me to make the change by hand.

Repo: https://github.com/yerinsabraham/trackline
Site: https://trackline.dev

Feedback welcome, especially on false alarms.
```

---

## 7. Show HN (you type this yourself)

**Link:** https://news.ycombinator.com/submit
**When:** a Tuesday–Thursday, 9am–12pm US Eastern (3pm–6pm Lagos). Stay in
the comments for 2 hours.

**Before anything else:** HN is currently restricting Show HN for accounts
with little history (https://news.ycombinator.com/showlim). If your account is
new, spend a week or two commenting on other posts first.

**What to put in the form:**

- **title:** `Show HN: Trackline – checks whether your coding agent is still doing what you asked`
- **url:** `https://github.com/yerinsabraham/trackline` (HN readers prefer the repo to a landing page)
- **text:** leave empty, then post your first comment straight away.

**Your first comment, in this order, in your own words (plain and short):**

1. Hi HN, who you are in one line (you build an AI support agent in Lagos).
2. The problem in one or two sentences: agents drift off task and nothing
   fails, the build stays green. You can cite the open Anthropic issue
   "Claude ignores explicit CLAUDE.md instructions while claiming to understand them".
3. What it is: a hook for Claude Code, Codex and Cursor that checks each tool
   call against the request and the project's rules. The five checks.
4. The experiment that decided it: blocked with a reason, agents corrected
   themselves 11 of 11. Say the caveat: one scenario, the message named an alternative.
5. Why Go: 88ms per call in Node vs 6.5ms in Go, and it runs on every tool call.
6. What it can't do: scope is silent when you don't name a path; shell only
   partly parsed; MCP mode is advisory; production traces untested on real traffic.
7. Why it's neutral (not tied to one vendor) in one sentence.
8. Install line, Apache-2.0, "happy to answer questions".

**Expect these questions** (they came up on similar Show HNs):
- "Can the agent just bypass it?" (Answer honestly: hooks run outside the
  model; MCP mode can be ignored.)
- "Default allow with no rules?" (Explain warn mode and why: a tool that
  interrupts wrongly gets uninstalled on day two.)
- "How is this different from nah / Claude Code permissions?" (Permissions
  check the action; trackline checks the action against the *request*.)

---

## 8. dev.to

**Link:** https://dev.to/new
**Rules:** a post must have real substance, not just a link. **AI-assisted
writing must be disclosed.** Up to 4 tags.

Easiest: republish your engineering note.

- **Title:** `Nothing notices when an agent drifts`
- **Tags:** `showdev, ai, opensource, claudecode`
- **canonical_url:** `https://yerinsabraham.com/engineering/nothing-notices-when-an-agent-drifts`
- **Body:** paste the note. Add at the end:

```
trackline is open source: https://github.com/yerinsabraham/trackline
I'm @yerinsabraham on X if you want to follow along.
```

If any of the note was written with AI help, add one line saying so.

---

## 9. Directories and lists

**mcp.so:** https://mcp.so/submit
Type: MCP Server. Repository URL: `https://github.com/yerinsabraham/trackline`.
Name: `trackline`. Free is slow. The $39 option is not needed.

**Changelog News:** https://changelog.com/news/submit (sign in)
- URL: `https://github.com/yerinsabraham/trackline`
- Title: `Trackline: a vendor-neutral watcher for AI coding agents`
- What's interesting about it:

```
Coding agents fail quietly: they edit files nobody asked for or ignore the project's rules, and the build stays green. Trackline hooks into Claude Code, Codex and Cursor, normalises each agent's events into one shape, and checks every action against the request and the rules. It can block and hand the reason back, and agents corrected themselves 11 of 11 times in testing. The hook started in Node at 88ms per tool call and was rewritten in Go at 6.5ms. The repo includes the experiments and raw data behind every design decision. Apache-2.0.
```

**Console.dev:** email **hello@console.dev**. It's a short personal email, so
write it yourself: what it is, it's free and self-serve (no signup), v0.6 so it
fits their beta section, and the GitHub link.

**awesome-claude-code:** https://github.com/hesreallyhim/awesome-claude-code
Use the "Recommend a Resource" issue form. **Not a PR, and you must type it
yourself.** Category: Observability & Monitoring › Session Monitors. The
description is 1–3 sentences, factual, no "you", no emojis. Leave the trap
checkbox unticked (the form tells you which one).

**Glama, awesome-mcp-servers, official MCP Registry, Smithery:** these need
small changes to the repo first (a `glama.json` file, and an `mcpName` field
in package.json in the next npm release). I'll do these; you don't need to
post anything for them.

---

## 10. Product Hunt (1–2 weeks after HN)

**Link:** https://www.producthunt.com/posts/new
**Launch:** 12:01am Pacific (8:01am Lagos). Needs at least 2 gallery images
(1270×760); the first one should show it working, not a logo.

- **Name:** trackline
- **Tagline (max 60):** `Know when your AI coding agent stops doing what you asked`
- **Description (max 500):**

```
AI coding agents don't crash when they drift. They edit files you never mentioned, add packages nobody asked for, and ignore your rules, and the build stays green. trackline runs beside Claude Code, Codex and Cursor, checks every action against your request and your project rules, and can stop the agent and tell it why so it fixes itself. Free and open source. Optional phone app to approve blocked actions.
```

- **Maker's first comment:** write it yourself on the day: why you built it,
  who it's for, what's new, and one thing you want feedback on. Ask for
  feedback, never for upvotes.
- Link your X in your maker profile. That's where it belongs on Product Hunt.

---

## Facebook, LinkedIn, X

- **Facebook:** skip.
- **LinkedIn:** fine to keep posting there, but for the job search, not for users.
- **X:** when a Reddit or HN post gets traction, post a link to it on X. People
  join a discussion that's already busy.
