# Claude Skills

A curated collection of [Claude Code](https://claude.ai/code) skills for technical writing, AI-assisted development, and consulting analysis.

[中文文档](./README.zh.md)

---

## Skills Included

| Skill | Trigger | Description |
|-------|---------|-------------|
| `technical-writing-craft` | Writing technical articles, blog posts, or explanatory docs | Framework-first writing patterns that make complex ideas memorable |
| `vibe-coding` | Building software with AI / no-code prototyping | Guide for non-engineers using AI tools to build functional software |

---

## Installation

### Plugin Method (Recommended)

Run these commands inside Claude Code:

```
/plugin marketplace add webaifei/feynman-skills
/plugin install feynman-skills@feynman-skills
/reload-plugins
```

### Manual Method

For a new project, download directly:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/webaifei/feynman-skills/main/CLAUDE.md
```

For an existing project, append to your current file:

```bash
echo "" >> CLAUDE.md
curl https://raw.githubusercontent.com/webaifei/feynman-skills/main/CLAUDE.md >> CLAUDE.md
```

---

## Usage

Once installed, skills are available automatically. You can also invoke them explicitly:

```
/technical-writing-craft
/vibe-coding
```

Or mention it in your request:

> "Use technical-writing-craft to help me write this article"

---

## Skills Detail

### technical-writing-craft

Use when writing technical articles, blog posts, or explanatory documents — especially when explaining complex engineering concepts, analogies, or industry shifts.

**Core patterns:**
- **Framework-First** — find the unifying framework before listing facts
- **Example pacing** — distant → familiar → present-day, in that order
- **Anchor sentence** — one sentence that can expand or compress the whole piece
- **Empathy before correction** — quote the common misconception before reframing it
- **Identity ending** — close with a role redefinition, not a to-do list

### vibe-coding

Use when someone is using AI to generate code, building prototypes without deep technical skills, or exploring how non-engineers can create functional software through natural language.

**Core principles:**
- Vibe coding is a distinct, learnable skill — not just prompt engineering
- Replace Figma mockups with functional prototypes built in 30 minutes
- Build iteratively: break down complex problems into smaller AI-friendly chunks
- Know the limits: great for MVPs, not for production-critical systems

---

## Adding a New Skill

1. Create `skills/<skill-name>/SKILL.md` with this frontmatter:

```markdown
---
name: skill-name
description: One sentence — when to use this skill.
license: MIT
---

# Skill Title

...skill content...
```

2. Add the path to `.claude-plugin/plugin.json`:

```json
{
  "skills": [
    "./skills/technical-writing-craft",
    "./skills/vibe-coding",
    "./skills/your-new-skill"
  ]
}
```

3. Update `.claude-plugin/marketplace.json` version.

4. Commit and push — the skill is live immediately after users run `/reload-plugins`.

---

## License

MIT
