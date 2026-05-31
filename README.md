# skills
## Dependencies
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



## Skill Installation Locations

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
