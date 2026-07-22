<img width="2172" height="724" alt="RC_Banner" src="https://github.com/user-attachments/assets/9e5de699-6750-4778-82ef-6a901a5f44b6" />

**A structured way for non-coders to build software with AI coding agents.**

This repository accompanies my RailCoding instructional video and provides a lightweight starter template for your own AI-assisted software project.

## What Is RailCoding?

RailCoding is a development process that puts clear rails around AI-generated code.

Instead of opening a coding agent and vaguely asking it to “make an app,” you first use a **GPT Project** to define:

* What the application should do
* What it should never do
* Who it is being built for
* Which features belong in the current build
* How you will know when the work is successful

The coding agent still handles most of the technical implementation, but it works from a clearer plan and within defined boundaries.

## The Two-Agent Workflow

RailCoding separates planning from implementation.

### Your GPT Project: The Planning Room

Create a dedicated GPT Project for your application and keep using the same project throughout development.

Use it to:

* Explore and refine your original idea
* Define features, limitations, and user workflows
* Create and revise `Vision.md`
* Produce focused `BuildSpec.md` files
* Review plans proposed by your coding agent
* Discuss bugs, screenshots, test results, and future features
* Translate technical agent responses into plain language

The GPT Project maintains the broader context of what you are building and why.

### Your Coding Agent: The Builder

Use Codex or another repository-aware coding agent to work directly with the project files.

The coding agent should:

* Read the project documents before coding
* Inspect the existing implementation
* Propose a plan for substantial changes
* Build within the approved scope
* Run relevant tests and checks
* Explain what changed
* Provide manual testing instructions
* Update the project logs

A simple way to think about it:

> **Your GPT Project helps design and supervise the application. Your coding agent builds it.**

## The RailCoding Loop

1. Discuss the idea inside your GPT Project.
2. Define the lasting product philosophy in `dev/Vision.md`.
3. Create a focused `dev/BuildSpec.md` for the current major build.
4. Give the BuildSpec to your coding agent.
5. Have the agent inspect the repository and propose a plan.
6. Bring that plan back to your GPT Project for review.
7. Approve or revise the plan.
8. Have the coding agent implement one manageable phase.
9. Run the automated and manual tests.
10. Record the work and commit a known working version.
11. Continue the same loop as the application develops.

Small adjustments can usually be handled with a direct prompt.

Large features, major refactors, or changes to stored data should receive a new BuildSpec.

## What This Template Contains

```text
RailCoding/
├── agents.md
├── ChangeLog.md
├── latest.json
├── .gitignore
└── dev/
    ├── Vision.md
    ├── BuildSpec.md
    └── ProjectLog.md
```

### `agents.md`

Permanent instructions for the coding agent.

These rules tell the agent to remain within scope, protect sensitive information, perform relevant testing, report failures honestly, and maintain the project logs.

### `dev/Vision.md`

The stable foundation of the application.

Use it to describe:

* The purpose of the application
* Intended users and use cases
* Core product principles
* What the application should do
* What the application should never do

Keep this file focused. It should not contain every possible future feature.

### `dev/BuildSpec.md`

The specification for the current major build.

Create this through your GPT Project after discussing and refining the feature set.

For the initial application, try to limit the BuildSpec to approximately three major phases:

1. Build the core application, data structure, and interface shell.
2. Complete the main user workflows.
3. Add validation, testing, documentation, and deployment support.

You may already have more ideas planned, but they do not all need to be handed to the coding agent at once.

### `dev/ProjectLog.md`

The internal development history.

The coding agent updates this with meaningful technical changes, bug resolutions, planning decisions, testing results, and remaining work.

This gives both you and your agents a useful reference outside the chat history.

### `ChangeLog.md`

A cleaner list of user-visible changes.

Use it for:

* New features
* Changed behavior
* Bug fixes
* Deployment changes
* Compatibility changes

You can later copy relevant entries into your release notes.

### `latest.json`

An optional starting point for an application update checker.

An application can compare its installed version against this small public file and notify the user when an update is available.

It is not required for every project.

## Getting Started

### 1. Copy the template

Use this repository as a template, clone it, or copy the files into a new project.

### 2. Prepare the private development folder

The `dev/` directory contains your internal planning documents.

After copying the template, replace the instructions inside `.gitignore` with:

```gitignore
dev/
```

This allows the folder to remain available locally without publishing your internal plans to GitHub.

Do not store passwords, API keys, private keys, personal information, or other secrets in these documents.

### 3. Create a GPT Project

Create a new GPT Project named after your application.

Begin with something similar to:

```text
I want to develop this application using the RailCoding method.

Help me define the intended users, core purpose, major features,
non-goals, security boundaries, deployment environment, and what
the application should never do.

Challenge unclear or conflicting ideas. Do not write code yet.
Once the foundation is clear, help me create Vision.md and a
focused three-phase BuildSpec.md.
```

Copy the completed documents into the corresponding files under `dev/`.

### 4. Start the coding agent

Open the repository with your coding agent and begin with:

```text
Read agents.md, dev/Vision.md, and dev/BuildSpec.md.

Inspect the repository before changing anything. Propose a practical
implementation plan for the first phase, identify unclear requirements,
and explain important technical decisions in novice-friendly language.

Do not begin implementation until the plan is approved.
```

Take the resulting plan back to your GPT Project for review before proceeding.

## RailCoding Is Not Autopilot

RailCoding does not guarantee that AI-generated code is correct, secure, or maintainable.

You still need:

* Git version control
* Known working commits
* Automated testing
* Manual testing
* Backups
* Careful review of destructive or security-sensitive changes
* Human judgment about whether the application behaves correctly

You do not need to understand every line of code.

You do need to understand what is being changed, why it is being changed, how it was tested, and how to recover if it fails.

## The Core Principle

> **Plan with context. Build within boundaries. Test every meaningful change. Keep a recoverable history.**
