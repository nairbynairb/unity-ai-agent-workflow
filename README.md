# The "Brain & Intern" AI Coding Workflow (Starter Templates)

A lightweight, token-saving setup for building large Unity (or any codebase) projects with AI coding agents—without burning through usage limits or letting an IDE agent turn your architecture into spaghetti.

* **Video 1 (The Game Showcase):** `[Coming Soon]`
* **Video 2 (Full Workflow Walkthrough):** `[Coming Soon]`
* **Devlog Timeline:** [Syndicate Hockey 2078 Devlog](https://nairbynairb.github.io/SyndicateHockey2078/timeline.html)

---

## How It Works (In 30 Seconds)

Instead of asking an IDE coding agent to do both high-level architecture *and* file editing (which burns tokens fast on folder scanning and context bloat), this workflow splits the job in two:

1. **The Brain (Web Browser AI — e.g., Gemini Web App):** Has zero access to your hard drive. You hand it `WEB_ARCHITECT_SKILL.md` + `SCRIPTS_TOC.md`, talk through a feature or bug, drop in just the 1–3 exact files it asks for, and have it output a downloadable, phase-by-phase `.md` implementation plan.
2. **The Intern (IDE Agent — e.g., JetBrains Rider, Cursor, VS Code):** Uses `IDE_AGENT_SKILL.md`. It executes **one phase at a time in a fresh chat**, compiles and checks engine logs autonomously, updates `SCRIPTS_TOC.md`, checks off the plan, and runs `git commit` after every clean phase.

---

## Files Included

| File | Where It Goes | Purpose |
| :--- | :--- | :--- |
| **`WEB_ARCHITECT_SKILL.md`** | Upload to your web browser AI chat | Turns the browser model into your Lead Architect that asks for exact files and writes "intern-proof" downloadable `.md` plans. |
| **`IDE_AGENT_SKILL.md`** | Your IDE agent's skill/rules file | Keeps the IDE agent fast, literal, and token-efficient (TOC-first lookup, auto-compile/logs, no autonomous screenshots, auto git commits). |
| **`SCRIPTS_TOC_BOOTSTRAP.md`** | Run once in your IDE | Contains a one-shot prompt to generate `SCRIPTS_TOC.md` on an existing project, plus a blank starter skeleton for new projects. |

---

## Quick Start

1. **Generate `SCRIPTS_TOC.md`:** Open `SCRIPTS_TOC_BOOTSTRAP.md` and run the prompt inside your IDE agent once to create a living Table of Contents in your project root.
2. **Customize the Two Skill Files:** Open `WEB_ARCHITECT_SKILL.md` and `IDE_AGENT_SKILL.md` and replace the bracketed `[PLACEHOLDERS]` with your project name, engine/coordinate conventions, and build/MCP commands.
3. **Start a Browser Session ("The Brain"):** Attach `WEB_ARCHITECT_SKILL.md` and `SCRIPTS_TOC.md`, describe what you want to build or fix, upload the 1–3 files it requests, and download the finished `.md` plan (if using Gemini, it will open cleanly in the side **Document Drawer** for a one-click download).
4. **Execute Phase-by-Phase ("The Intern"):** Drop the `.md` plan into your repo and tell your IDE agent: *"Execute Phase 1 of `MY_PLAN.md`."* Once it compiles, verifies logs, and commits, open a **fresh chat** for Phase 2.

---

## License

Feel free to fork, copy, strip down, and adapt these templates for any personal or commercial project.
