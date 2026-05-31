# skills
## 1. Dependencies
### Node.js
```
npm install -g npm@11.16.0
```
### Claude Code
```
npm install -g @anthropic-ai/claude-code
```
### Python
### Anthropics official skill-creator
```
npx skills add https://github.com/anthropics/skills --skill skill-creator
```
Additional agents: Claud Code
Installation scope: Global
All the way down: Yes

```

███████╗██╗  ██╗██╗██╗     ██╗     ███████╗
██╔════╝██║ ██╔╝██║██║     ██║     ██╔════╝
███████╗█████╔╝ ██║██║     ██║     ███████╗
╚════██║██╔═██╗ ██║██║     ██║     ╚════██║
███████║██║  ██╗██║███████╗███████╗███████║
╚══════╝╚═╝  ╚═╝╚═╝╚══════╝╚══════╝╚══════╝

┌   skills
│
◇  Source: https://github.com/anthropics/skills.git
│
◇  Repository cloned
│
◇  Found 18 skills
│
●  Selected 1 skill: skill-creator
│
◇  56 agents
◇  Which agents do you want to install to?
│  Amp, Antigravity, Cline, Codex, Cursor, Deep Agents, Dexto, Firebender, Gemini CLI, GitHub Copilot, Kimi Code CLI, OpenCode, Warp, Zed
│
◇  Installation scope
│  Global

│
◇  Installation Summary ────────────────────────────────────╮
│                                                           │
│                                                           │
│  Example Skills                                           │
│                                                           │
│  ~/.agents/skills/skill-creator                           │
│    copy → Amp, Antigravity, Cline, Codex, Cursor +9 more  │
│                                                           │
├───────────────────────────────────────────────────────────╯
│
◇  Security Risk Assessments ───────────────────────────────────╮
│                                                               │
│                 Gen               Socket            Snyk      │
│  skill-creator  Safe              0 alerts          Low Risk  │
│                                                               │
│  Details: https://skills.sh/anthropics/skills                 │
│                                                               │
├───────────────────────────────────────────────────────────────╯
│
◇  Proceed with installation?
│  Yes
│
◇  Installation complete

│
◇  Installed 1 skill ──────────────────╮
│                                      │
│                                      │
│  Example Skills                      │
│  ✓ skill-creator (copied)            │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│    → ~/.agents/skills/skill-creator  │
│                                      │
├──────────────────────────────────────╯

│
└  Done!  Review skills before use; they run with full agent permissions.


│
│  One-time prompt - you won't be asked again if you dismiss.
│
◇  Install the find-skills skill? It helps your agent discover and suggest skills.
│  Yes

│
◇  Installing find-skills skill...

┌   skills
│
◇  Source: https://github.com/vercel-labs/skills.git
│
◇  Found 1 skill
│
●  Selected 1 skill: find-skills

│
◇  Installation Summary ────────────────────────────────────╮
│                                                           │
│  ~/.agents/skills/find-skills                             │
│    copy → Amp, Antigravity, Cline, Codex, Cursor +9 more  │
│                                                           │
├───────────────────────────────────────────────────────────╯
│
◇  Security Risk Assessments ─────────────────────────────────╮
│                                                             │
│               Gen               Socket            Snyk      │
│  find-skills  Safe              0 alerts          Med Risk  │
│                                                             │
│  Details: https://skills.sh/vercel-labs/skills              │
│                                                             │
├─────────────────────────────────────────────────────────────╯
│
◇  Installation complete

│
◇  Installed 1 skill ────────────────╮
│                                    │
│  ✓ find-skills (copied)            │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│    → ~/.agents/skills/find-skills  │
│                                    │
├────────────────────────────────────╯

│
└  Done!  Review skills before use; they run with full agent permissions.
```
If it was installed in ~/.agents/skills/skill-creator, you can move it to the Claude skill folder
```
cp -pr ~/.agents/skills/skill-creator ~/.claude/skills
```


## 2. Skill Installation Locations

Claude Code supports multiple locations for installing Skills. The best choice depends on how you plan to use and share them.

### Project-Level Skills (Recommended for Team Collaboration)

Install Skills inside your project repository when they are intended to be shared across a team. This approach allows Skills to be version-controlled alongside the project, ensuring that all contributors use the same set of capabilities and prompts.

**Location**

```text
<project-root>/.claude/skills/
```

**Best for**

- Team collaboration
- Shared engineering workflows
- Project-specific automation
- Version-controlled Skill management

---

### Global-Level Skills (Recommended for Personal Use)

Install Skills globally when you want them to be available across all Claude Code projects on your machine. This is the preferred option for personal productivity Skills that you use regularly.

**Location**

```text
~/.claude/skills/
```

**Best for**

- Personal workflows
- Frequently used Skills
- Cross-project productivity enhancements
- Individual customization

---

### Temporary Skill Import (Recommended for Testing)

For quick experiments, demonstrations, or validation, Skills can be imported directly into a Claude conversation. No installation is required, but the Skill is only available during the current session.

**Scope**

```text
Current conversation only
```

**Best for**

- Testing new Skills
- Proof-of-concept demonstrations
- One-time usage
- Rapid iteration

---

### Recommendations

| Use Case | Recommended Location |
|-----------|---------------------|
| Team collaboration | `<project-root>/.claude/skills/` |
| Personal daily use | `~/.claude/skills/` |
| Testing and experimentation | Temporary Import |

### Summary

As a general rule:

- Use **Project-Level Skills** when the Skill should be shared with other team members.
- Use **Global-Level Skills** when the Skill is part of your personal toolkit and should work across all projects.
- Use **Temporary Imports** when evaluating or testing a Skill before deciding where to install it permanently.


## 3. What Is a Skill?

A Skill is a reusable capability package that extends an AI agent with specialized knowledge, workflows, scripts, templates, and supporting resources.

Each Skill is organized as a directory with a predefined structure:

```text
skill-name/
├── SKILL.md       # Required: Skill definition and instructions
├── scripts/       # Optional: Executable scripts (Node.js, Python, Shell, etc.)
├── references/    # Optional: Reference documents loaded on demand
└── assets/        # Optional: Static resources and templates
```

---

## SKILL.md

The core definition file of a Skill.

This file typically contains:

- **name**: Skill name
- **description**: Brief description of the Skill
- **body**: Detailed instructions, workflows, and guidance

**Example**

```markdown
name: mysql-risk-analysis

description: Analyze MySQL risk inspection results and generate governance recommendations.

body:
- Parse inspection records
- Identify high-risk items
- Generate remediation suggestions
- Produce executive summaries
```

**Purpose**

- Defines when the Skill should be used
- Provides instructions for the AI agent
- Acts as the entry point of the Skill

---

## scripts/

Contains executable code used by the Skill.

Typical languages include:

- Python
- Node.js / TypeScript
- Shell scripts
- Go binaries

**Example**

```text
scripts/
├── analyze.py
├── generate_report.py
└── notify.sh
```

**Purpose**

- Data processing
- Automation workflows
- External system integration
- Report generation

---

## references/

Contains reference documentation that can be loaded when needed.

**Example**

```text
references/
├── mysql-best-practices.md
├── incident-playbook.md
└── architecture-guide.pdf
```

**Purpose**

- Provide domain knowledge
- Store operating procedures
- Supply implementation examples
- Reduce prompt size by loading content only when required

---

## assets/

Contains static resources used by the Skill.

**Example**

```text
assets/
├── report-template.md
├── incident-template.docx
├── dashboard.json
└── logo.png
```

**Purpose**

- Document templates
- Configuration files
- Static datasets
- Images and other supporting resources

---

## Example Skill Structure

```text
mysql-risk-governance/
├── SKILL.md
├── scripts/
│   ├── baseline_analysis.py
│   ├── trend_analysis.py
│   └── generate_report.py
├── references/
│   ├── mysql-inspection-standard.md
│   ├── governance-process.md
│   └── incident-playbook.md
└── assets/
    ├── daily-report-template.md
    └── weekly-summary-template.md
```

---

## Summary

| Component | Required | Purpose |
|------------|----------|---------|
| SKILL.md | Yes | Defines the Skill and its behavior |
| scripts/ | No | Stores executable code and automation logic |
| references/ | No | Stores reference materials loaded on demand |
| assets/ | No | Stores templates, static files, and resources |

At minimum, a Skill only requires a `SKILL.md` file. The `scripts/`, `references/`, and `assets/` directories are optional and should be added only when needed.
