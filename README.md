# prompt-architect

**stop prompting from scratch. start every project with a master prompt.**

![Stars](https://img.shields.io/github/stars/SAFESPACE22/prompt-architect?style=flat&color=e4ff5e)
![Last Commit](https://img.shields.io/github/last-commit/SAFESPACE22/prompt-architect?style=flat)
![License](https://img.shields.io/github/license/SAFESPACE22/prompt-architect?style=flat)

[Install](#install) • [Before/After](#before--after) • [How It Works](#how-it-works) • [Why](#why)

---

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill that transforms a raw project idea into a complete project package — master prompt, per-team-member task lists, and ready-to-use CLAUDE.md files — through guided conversation with a Principal Engineer persona.

No more re-explaining your project to AI tools every session. Generate once. Share across your team. Start every AI coding session with full context.

## Before / After

|  |  |
| --- | --- |
| 🧱 **Without prompt-architect**<br/>You open Claude Code. You type "I want to build a SMS ride-share app." Claude asks one question, you answer vaguely, it generates generic code that doesn't match your actual stack. You spend 30 minutes re-explaining. Next session: you do it all over again. | ✨ **With prompt-architect**<br/>You run the skill. Answer 5-8 targeted multiple-choice questions. Get a 500-word master prompt, role-scoped sub-prompts for each teammate, and a CLAUDE.md file committed to your repo. Every AI session after this starts with full context. |

**Same project. 10x less context-setting. Aligned team from day one.**

## What You Get

Every time you run `prompt-architect`, you walk away with:

| File | What it is |
| --- | --- |
| `MASTER_PROMPT.md` | 400-600 word structured prompt covering scope, risks, architecture, and definition of done. Works in any AI tool. |
| `{member}_package.md` | One per team member. Sub-prompt + prioritized task list + role-scoped CLAUDE.md context. |
| `README_SNIPPET.md` | Project overview ready to paste into your repo's README. |
| `CLAUDE.md` + `.cursor/rules/project-context.mdc` + `.clinerules` + `GEMINI.md` + `AGENTS.md` + `.github/copilot-instructions.md` | Project-level context auto-loaded by Claude Code, Cursor, Cline, Gemini CLI, OpenAI Codex CLI, and GitHub Copilot. Generated once, works everywhere. |

## How It Works

1. **You describe the project** — one paragraph, no structure required
2. **AI asks targeted questions** — multiple choice with free-response escape hatch, tailored to *your* project
3. **Confidence bar climbs** as the AI builds understanding (you see `Clarity: 62% → 78%`)
4. **At 85% clarity, you get a summary** — confirm or correct the AI's understanding
5. **Team setup** — who's on the team, what are their roles
6. **Everything generates at once** — files land in `.prompt-architect/`

No questions are hardcoded. No templates to fill in. The AI figures out what it needs to know based on what you're actually building.

## The Engineering Lens

The skill runs with a **Principal Software Engineer persona** baked in — 20+ years of experience thinking in:

- 📋 **RFCs** — propose an approach before building
- 📐 **ADRs** — document the *why* behind decisions
- 🔪 **Vertical slicing** — shippable slices, not horizontal layers
- ⚠️ **Risk-first planning** — identify the riskiest assumption first
- ✅ **Definition of Done** — explicit criteria, not vague aspirations
- 🎯 **Shape Up** — define appetite before scope

Your generated master prompt reflects all of this automatically. It's what you'd get if a senior engineer wrote the spec for you — without having one on staff.

## Folder Structure

**This repo:**

```
coldstart/
├── prompt-architect/
│   └── SKILL.md          # the skill — everything runs from here
└── README.md
```

**What gets generated in your project when you run the skill:**

```
your-project/
├── .cursor/
│   └── rules/
│       └── project-context.mdc   # Cursor
├── .github/
│   └── copilot-instructions.md   # GitHub Copilot
├── .prompt-architect/
│   ├── MASTER_PROMPT.md          # source of truth
│   ├── README_SNIPPET.md         # paste into your README
│   └── {member}_package.md       # one per team member
├── .clinerules                    # Cline
├── AGENTS.md                      # OpenAI Codex CLI
├── CLAUDE.md                      # Claude Code
└── GEMINI.md                      # Gemini CLI
```

## Install

### Mac / Linux

```bash
mkdir -p ~/.claude/skills/prompt-architect && curl -o ~/.claude/skills/prompt-architect/SKILL.md https://raw.githubusercontent.com/SAFESPACE22/coldstart/main/prompt-architect/SKILL.md
```

### Windows

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills\prompt-architect" | Out-Null; Invoke-WebRequest -Uri "https://raw.githubusercontent.com/SAFESPACE22/coldstart/main/prompt-architect/SKILL.md" -OutFile "$env:USERPROFILE\.claude\skills\prompt-architect\SKILL.md"
```

### Enable it

Go to **Settings → Capabilities → Code execution and file creation** (must be ON).
Then **Customize → Skills** and toggle `prompt-architect` on.

Install once. Use it every time you start a new project.

## Usage

Start a Claude Code session and say anything like:

- "I want to build [X]"
- "Help me plan a new project"
- "Generate a CLAUDE.md for my new app"
- "Set up context for my team"

Or force it explicitly with `/prompt-architect`.

The skill walks you through everything. Takes about 5-10 minutes for a complete package.

## What Prompt Architect Does

| Thing | Prompt Architect Do? |
| --- | --- |
| Generate master prompts | ✅ Yes — that's the whole point |
| Ask sharp clarifying questions | ✅ Tailored to *your* project, not generic |
| Create per-member task lists | ✅ One package per teammate |
| Write CLAUDE.md files | ✅ Role-scoped, ready to commit |
| Apply engineering frameworks | ✅ RFCs, ADRs, vertical slicing, risk-first |
| Work on existing codebases | ❌ No — this is for project *initialization* |
| Write actual application code | ❌ Use Claude Code for that (after running this) |
| Replace planning with a team | ❌ It's a tool, not a tech lead |

## Why

```
┌─────────────────────────────────────────┐
│  CONTEXT SETUP TIME       ██░░░░░░  -90%│
│  TEAM ALIGNMENT           ████████ +100%│
│  PROMPT QUALITY           ████████ +85% │
│  SETUP FRICTION           ░░░░░░░░  ~0  │
└─────────────────────────────────────────┘
```

- **Stop re-explaining** — every AI session starts with full context via CLAUDE.md
- **Stop drifting** — everyone on the team works from the same master prompt
- **Stop winging scope** — questions surface the risks you'd forget to think about
- **Start with senior thinking** — engineering frameworks baked in, no PhD required

## How It's Different

This isn't a prompt library. It's not a template you fill in. It's a conversational skill that builds the master prompt *with you* — asking the right questions, applying real engineering frameworks, and producing output that's specific to your project.

**Prompt libraries** give you a fill-in-the-blanks template. You still have to know what to write.
**Prompt Architect** gives you a principal engineer who interviews you and writes it for you.

## The Ecosystem

prompt-architect is the **planning layer** that sits in front of Claude Code:

```
  [ raw idea ]
       ↓
  [ prompt-architect ]   ← you are here
       ↓
  [ master prompt + CLAUDE.md ]
       ↓
  [ Claude Code builds the thing ]
```

Use them together. Planning before execution beats execution without a plan.

## Star This Repo

If prompt-architect saves you an hour of context-setting on your next project — leave a star. ⭐

## License

MIT — use it, fork it, build on it. Just don't claim you invented it.

## Credits

Inspired by every engineer who ever said "I wish we'd written this down before we started."
