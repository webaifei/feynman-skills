# Feynman Skills

> "If you can't explain it simply, you don't understand it well enough." — Richard Feynman

[Claude Code](https://claude.ai/code) skills for creating content that is genuinely easy to understand — covering both **how you write** and **how you present**.

[中文文档](./README.zh.md)

---

## The Problem This Solves

Most technical content fails at two layers:

- **Content layer** — facts are listed without a unifying frame. Readers know more but don't think differently.
- **Presentation layer** — ideas are clear but the visual output is rough, making them harder to absorb.

Feynman Skills addresses both. Write the way Feynman taught, present the way great products do.

---

## Skills Included

| Skill | Layer | When to Use |
|-------|-------|------------|
| `technical-writing-craft` | **Content** — structure & style | When you want readers to *understand*, not just *know* |
| `vibe-coding` | **Presentation** — UI & visual | When you want to turn your content into a polished, interactive page |

---

## Installation

### Plugin Method (Recommended)

Run inside Claude Code:

```
/plugin marketplace add webaifei/feynman-skills
/plugin install feynman-skills@feynman-skills
/reload-plugins
```

### Manual Method

Append to your project's `CLAUDE.md`:

```bash
echo "" >> CLAUDE.md
curl https://raw.githubusercontent.com/webaifei/feynman-skills/main/CLAUDE.md >> CLAUDE.md
```

---

## Usage

The two skills work in sequence:

```
/technical-writing-craft   ← step 1: structure the content
/vibe-coding               ← step 2: present it beautifully
```

Or mention them in your request:

> "Use technical-writing-craft to help me write this article about zero-knowledge proofs, then vibe-code it into a clean HTML page"

---

## What Each Skill Does

### technical-writing-craft — Content Layer

Six patterns that separate writing that *informs* from writing that *changes how you think*:

| Pattern | What it does |
|---------|-------------|
| **Framework-First** | Find one frame that makes every fact feel inevitable, not accidental |
| **Example Pacing** | Distant → familiar → present-day. Train the intuition before making the ask |
| **Anchor Sentence** | One sentence that can expand to the whole piece or compress back to itself |
| **Empathy Before Correction** | Quote the common misconception first. Readers open up before they push back |
| **Identity Ending** | Close with who the reader is now, not what they should do next |
| **Generation-Verification Gap** | Help readers see their value isn't in producing — it's in judging |

### vibe-coding — Presentation Layer

Guides you to turn content into functional, polished UI using AI — no deep engineering required:

| Principle | What it means |
|-----------|--------------|
| **Prototype over mockup** | Build a working page in 30 min instead of a Figma static |
| **Iterative by design** | Break complex UI into small AI-friendly chunks, refine through follow-up |
| **Know the limits** | Great for articles, landing pages, and docs; production systems still need engineering review |

---

## Adding More Skills

1. Create `skills/<skill-name>/SKILL.md`:

```markdown
---
name: skill-name
description: One sentence — when to invoke this skill.
license: MIT
---

# Skill Title

...content...
```

2. Add to `.claude-plugin/plugin.json`:

```json
{
  "skills": [
    "./skills/technical-writing-craft",
    "./skills/your-new-skill"
  ]
}
```

3. Bump version in `marketplace.json`, commit, push.

---

## License

MIT
