# Creovine Academy
## AI Software Engineering, Free Course
### Lesson 1: Set Up Your AI Coding Environment

> **Goal of this lesson:** By the end of this video, the learner should have a code editor, a GitHub account, Git/GitHub access, and at least one AI coding agent ready to use inside VS Code.
>
> **Recording style:** Start on camera, then move to your MacBook screen. Use your normal voice throughout. Keep the explanation conversational. You do not need to reinstall tools you already have. Show learners where to get them and what they should see after setup.

---

## 0. Before You Record

Have these open or ready:

- VS Code
- Your browser
- GitHub
- VS Code Extensions panel
- Codex inside VS Code
- Claude Code inside VS Code
- Terminal
- A simple empty folder you can open in VS Code

Do not worry about showing every possible setting.

The purpose of this lesson is simply:

**Get the learner connected and ready to build.**

---

# 1. Introduction

**[ON CAMERA]**

### SAY:

Hi, welcome to the first lesson of AI Software Engineering.

In this course, I am going to show you how I use AI to build software.

And I want to start from the beginning.

So if you have never used an AI coding agent before, or you have used ChatGPT to generate code but you do not really know how to work inside a proper coding environment, this lesson is for you.

By the end of this lesson, I want you to have your computer ready so that we can actually start building.

We are going to set up a code editor, GitHub, and an AI coding agent.

I will also show you two AI coding tools you can use, Codex and Claude Code.

You do not need both.

You can choose one and follow the rest of the course with it.

**[PAUSE]**

One important thing before we start.

AI can write a lot of code for you, but that does not mean you should stop thinking.

The way I build software with AI is that I still decide what I want to build, how I want it to work, and how I want the project to be structured.

The AI helps me do the work faster.

That is the approach I am going to teach you throughout this course.

---

# 2. What You Need

**[SWITCH TO SCREEN RECORDING]**

### SAY:

Let me quickly show you the basic tools we need.

You need:

1. VS Code
2. Git
3. A GitHub account
4. An AI coding agent

And for this course, the two AI coding agents I am going to show you are Codex and Claude Code.

Again, you do not need to pay for or install every AI coding tool you see online.

Choose one good tool, learn how to use it properly, and build with it.

---

# 3. VS Code

**[OPEN BROWSER]**

Search:

`Visual Studio Code`

**[SHOW THE OFFICIAL MICROSOFT VS CODE PAGE]**

### SAY:

The first thing you need is VS Code.

VS Code is where we are going to open our project, see our files, use the terminal, and work with our AI coding agent.

I already have VS Code installed on my computer, so I am not going to download it again.

If you do not have it, search for Visual Studio Code and make sure you are downloading it from the official Microsoft website.

Choose the version for your computer, install it, and open it.

VS Code works on Mac, Windows, and Linux.

**[OPEN VS CODE]**

This is what VS Code looks like.

Do not worry if it looks complicated at first.

Most of the time, we are only going to use a few parts of it.

Over here, you have your files.

This large area is where your code opens.

And down here, we can open the terminal.

Later, you will also see your AI coding agent inside this environment.

That is enough for now.

---

# 4. Git and GitHub

**[OPEN GITHUB IN BROWSER]**

### SAY:

The next thing you need is GitHub.

If you do not already have a GitHub account, go to GitHub and create one.

GitHub is where we can store our code online.

It also gives us a history of the work we have done.

This becomes very important when you are building with AI.

Sometimes an AI agent can change many files at once.

If something goes wrong, Git helps us understand what changed and go back to an earlier version if we need to.

So even though AI is doing a lot of the coding, I still want you to use Git.

---

## Check Whether Git Is Installed

**[OPEN TERMINAL IN VS CODE]**

### SAY:

Let us check if Git is already installed.

Open the terminal inside VS Code.

You can type:

```bash
git --version
```

If you see a Git version here, Git is installed.

If your computer says that Git is not available, install Git from the official Git website and come back.

**[OPTIONAL PERSONAL NOTE]**

You can briefly explain how you personally use Git while building, for example:

> I commit my work as I go because I do not want an AI agent to make a huge change and leave me with no easy way to go back.

---

# 5. GitHub CLI

### SAY:

There is one more GitHub tool I like to use.

It is called GitHub CLI.

CLI simply means command-line interface.

It lets you work with GitHub directly from your terminal.

Later in this course, I will show you why this is useful, especially when we want our AI coding agent to inspect repositories or work with GitHub without us constantly leaving VS Code.

If you do not have GitHub CLI, search for:

`GitHub CLI`

and follow the official GitHub installation instructions for your computer.

I already have it installed.

So I can check it by typing:

```bash
gh --version
```

And if I need to connect this computer to my GitHub account, I can run:

```bash
gh auth login
```

Then GitHub will take me through the login process.

**[DO NOT LOG OUT OF YOUR OWN ACCOUNT JUST FOR THE RECORDING]**

### SAY:

I am already logged in, so I am not going to disconnect my account just to repeat this process.

But when you run `gh auth login`, follow the instructions on your screen and connect your GitHub account.

---

# 6. Choosing an AI Coding Agent

**[BACK TO VS CODE]**

### SAY:

Now we need the AI.

There are many AI coding tools available.

For this course, I want to keep it simple.

I am going to show you two options:

- Codex
- Claude Code

You only need one.

The exact buttons and pricing of these tools can change over time, so always check their official websites for the latest access options.

What matters for this course is the workflow.

The ideas I will teach you, planning, giving the AI context, reviewing its work, debugging, using Git, and building step by step, work across different coding agents.

---

# 7. Option One: Codex

**[OPEN VS CODE EXTENSIONS]**

Search:

`Codex`

**[SHOW THE OFFICIAL OPENAI CODEX EXTENSION]**

### SAY:

The first option is Codex from OpenAI.

If you want to use Codex inside VS Code, open the Extensions section and find the official Codex extension from OpenAI.

Install the extension.

After that, open Codex and follow the sign-in instructions.

I already have mine connected, so this is what it looks like on my computer.

**[SHOW CODEX PANEL]**

The useful thing about a coding agent is that it is not only giving you an answer in a chat box.

It can work with the files in your project.

It can inspect your code.

It can create files.

It can edit files.

It can run commands.

It can help you find errors.

And depending on how you are using it, it can help you plan and review your work as well.

That is very different from simply copying code from a normal chatbot and pasting it into VS Code.

**[SHOW A VERY SIMPLE EXAMPLE, OPTIONAL]**

Open an empty project and type something harmless such as:

> Tell me what files are currently in this project. Do not change anything.

### SAY:

Notice that I can also tell the agent not to make changes.

You should get comfortable telling your AI exactly what you want it to do, and also what you do not want it to do.

We will talk much more about that later.

---

# 8. Option Two: Claude Code

**[OPEN EXTENSIONS / CLAUDE CODE]**

### SAY:

The second option is Claude Code from Anthropic.

Claude Code can also work inside VS Code.

Search for the official Claude Code integration, install it, and follow the sign-in instructions.

I already have mine connected.

**[SHOW CLAUDE CODE IN VS CODE]**

The same basic idea applies here.

Claude can see the project you are working on, inspect files, make changes, run commands, and help you work through a software task.

You might see developers online arguing that one tool is better than another.

Do not let that stop you from starting.

For now, choose one.

If you already pay for or prefer one of these tools, use that one.

The skill I want you to learn is how to work with an AI coding agent properly.

---

# 9. Do You Need Codex and Claude Code Together?

**[OPTIONAL FACE CAM OR KEEP SCREEN]**

### SAY:

A question you might have is:

Do I need Codex and Claude Code together?

No.

You do not.

I personally use different tools for different situations, and as you get better you may also develop your own preferences.

But as a beginner, having five different coding agents can actually make learning harder.

Pick one and get comfortable with it.

Throughout the course, if I show something using one agent, focus on the idea behind what I am doing.

You can usually apply the same workflow with another agent.

---

# 10. Open a Project Folder

**[CREATE OR OPEN A SIMPLE EMPTY FOLDER]**

### SAY:

Now let us make sure we can actually work inside a project.

I am going to create a simple folder.

You can call yours anything.

For example:

`my-first-ai-project`

Then open that folder inside VS Code.

**[SHOW THE EMPTY VS CODE FOLDER]**

This folder is going to become our project.

When we start building, our files will live inside here.

And when we talk to our AI coding agent, the agent will work inside this project.

That sounds simple, but it is an important idea.

You do not want to randomly ask the AI to create files all over your computer.

Work inside a clear project folder.

---

# 11. A Very Simple First Test

**[OPEN YOUR CHOSEN AGENT]**

### SAY:

Before we finish, let us make sure the AI can see the project.

I can ask:

> Look at this project and tell me what you can currently see. Do not create or edit any files.

**[LET IT RESPOND]**

And that is enough.

We are connected.

I am not asking it to build anything yet.

That is intentional.

Because before we start coding, we need to decide what we are actually building.

That is the next part of this course.

---

# 12. Brief Introduction to External Tools and MCP

**[KEEP THIS SECTION SHORT, ABOUT 60 TO 90 SECONDS]**

### SAY:

There is one more thing I want you to know exists, but we are not going to set it up in this lesson.

Your coding agent does not always have to work only with the files on your computer.

You can connect AI coding tools to other tools and services.

One way you may hear people talk about this is MCP, which stands for Model Context Protocol.

Do not worry about memorising that.

The simple idea is that we can give an AI agent access to additional tools and information that are useful for the work we are doing.

For example, depending on your work, you might connect tools that help with:

- design
- browser testing
- documentation
- databases
- project management
- cloud services
- other developer tools

If you are mainly working on frontend software, the tools you care about may be different from someone doing backend work.

A designer who is using AI as part of a development workflow may also connect completely different tools.

But I do not want you connecting twenty things before you have even built your first project.

We will introduce extra tools when there is a reason to use them.

For now, your basic setup is enough.

---

# 13. What We Have Set Up

**[SHOW VS CODE WITH PROJECT OPEN]**

### SAY:

So at this point, you should have:

- VS Code
- Git
- a GitHub account
- GitHub connected to your computer
- and at least one AI coding agent

That is everything we need to get started.

Notice that we still have not written any code.

That is because the next thing I want to teach you is one of the most important parts of building software with AI.

Planning.

Before I ask an AI to build a product for me, I normally spend time thinking through the product first.

What am I building?

Who is it for?

What exactly should it do?

What are the main features?

How should the different parts connect?

If you skip that and simply tell an AI, "build me an app," you can get something that looks impressive very quickly, but becomes difficult to control as the project grows.

So in the next lesson, we are going to plan the product before we touch the code.

---

# 14. End of Lesson

**[ON CAMERA]**

### SAY:

That is it for this lesson.

Make sure your setup is working before you move on.

You do not need to understand every button in VS Code.

You do not need five AI tools.

And you definitely do not need to know everything about software engineering before you start.

You just need the basic environment ready.

In the next lesson, we are going to take an idea and turn it into a proper plan that our AI coding agent can actually work with.

I will see you there.

---

# Optional Recording Notes for Sarah

These are **not part of the spoken script**.

## Keep

- Your real voice.
- Your natural Nigerian accent.
- Clear captions.
- Mostly screen recording.
- Short face-camera introduction and ending.
- Your own examples and personal habits when they naturally fit.

## Avoid

- Explaining every VS Code button.
- Spending several minutes installing software on camera.
- Comparing ten different coding agents.
- Going deep into MCP.
- Teaching advanced Git in this lesson.
- Teaching APIs, databases, architecture, or deployment yet.
- Making beginners feel like they need to pay for every tool before they can start.

## Good places to add your personal experience

Add a short personal comment when you discuss:

1. Why you use Git.
2. Which coding agent you personally prefer and why.
3. Why you do not immediately ask AI to build the entire product.
4. Why you keep projects inside clear folders.
5. How your own setup differs depending on the type of software you are building.

The personal comments should feel like:

> "This is how I normally do it..."

rather than:

> "This is the only correct way to do it."

---

# Suggested Lesson Resource

Do **not** make a PDF for this lesson unless you later discover students are getting stuck on setup.

Under the video, simply provide a small **Tools Used in This Lesson** section with:

- Visual Studio Code
- Git
- GitHub
- GitHub CLI
- Codex
- Claude Code

Students can use the official links from your course page.

That is enough for Lesson 1.
