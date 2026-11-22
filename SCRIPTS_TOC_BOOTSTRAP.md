# Bootstrapping `SCRIPTS_TOC.md` for Your Project

`SCRIPTS_TOC.md` is the backbone of the Brain & Intern workflow. It gives your web browser Architect a complete map of your codebase in a single file—and stops your IDE agent from burning tokens scanning folders.

Use **Part 1** if you already have a project with existing scripts, or **Part 2** if you are starting from scratch.

---

## Part 1: One-Shot Generator Prompt (For Existing Projects)

Copy and paste this prompt into your IDE coding agent **once** to generate your initial `SCRIPTS_TOC.md`:

~~~text
Scan all active scripts in [e.g., Assets/Scripts/] and generate a clean SCRIPTS_TOC.md file in the project root using this exact structure:

1. Start with a header showing total active script count, approximate total lines of code, and a short note instructing AI agents to check this file before searching the project.
2. Add a "Quick Feature & Subsystem Lookup" Markdown table mapping high-level game features to their key scripts and primary entry-point methods.
3. Group all scripts into numbered sections by folder/domain (e.g., Core, Gameplay, AI, Data, UI, Editor).
4. For each script, list ONLY:
   - Relative file path / filename
   - Defined Types (classes, structs, enums)
   - Namespace and exact Lines count
   - A concise 1–3 sentence Summary of what it owns
   - Key Methods (only the important public/internal entry points—skip boilerplate getters)

Keep descriptions dense and factual so the entire file stays easy to scan in a single browser context window. Do not modify any code files; only create SCRIPTS_TOC.md.
~~~

---

## Part 2: Blank Starter Skeleton (For Brand-New Projects)

Create a file named `SCRIPTS_TOC.md` in your project root and paste this starter template. Your IDE agent will append new scripts to it automatically at the end of each phase.

~~~markdown
# [YOUR PROJECT NAME] – Project Scripts Table of Contents (TOC)

> **Purpose for AI Agents & Developers:**
> Use this Table of Contents as an instant index to locate classes, methods, and systems across the codebase. **Always check this document first before running broad file searches**, conserving tokens and isolating changes immediately.

> **Project Metrics:** 0 Active Scripts | ~0 Total Lines of Code

---

## Quick Feature & Subsystem Lookup

| Feature / Domain | Key Scripts | Primary Entry Points & Methods |
| :--- | :--- | :--- |
| **Player Input & Movement** | `Assets/Scripts/Player/PlayerController.cs` | `HandleInput()`, `FixedUpdate()`, `ApplyMovement()` |
| **Game Loop & Rules** | `Assets/Scripts/Core/GameManager.cs` | `StartMatch()`, `TriggerStateChange()`, `ResetRound()` |
| **UI & HUD** | `Assets/Scripts/UI/HudController.cs` | `BindRoot()`, `RefreshHud()`, `TogglePause()` |

---

## 1. Core Systems (`Assets/Scripts/Core/`)

### `GameManager.cs`
- **Types:** `GameManager : MonoBehaviour`, `MatchState` (enum)
- **Namespace:** `Core` | **Lines:** 140
- **Summary:** Central match state coordinator managing round flow, pause states, and scene transitions.
- **Key Methods:**
  - `StartMatch()` / `EndMatch()`: Initializes and concludes active play sessions.
  - `TriggerStateChange(MatchState next)`: Broadcasts match state transitions to subscribed systems.

## 2. Gameplay & AI (`Assets/Scripts/Gameplay/`)

*(IDE agent appends new scripts here automatically at the end of each phase.)*

## 3. UI & Presentation (`Assets/Scripts/UI/`)

*(IDE agent appends new scripts here automatically at the end of each phase.)*

## 4. Editor Tools (`Assets/Scripts/Editor/`)

*(IDE agent appends custom Editor windows, bakers, and postprocessors here.)*
~~~
