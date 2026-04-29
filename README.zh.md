# Feynman Skills

> "如果你不能简单地解释一件事，说明你还没真正理解它。" — 理查德·费曼

[Claude Code](https://claude.ai/code) Skills，帮助你创作真正通俗易懂的内容——覆盖**写作风格与组织方式**和**视觉呈现**两个层面。

[English](./README.md)

---

## 解决什么问题

大多数技术内容在两个层面同时失败：

- **内容层** — 罗列了事实，却没有给读者统一的认知框架。读者知道了更多信息，但思维方式没有变化。
- **呈现层** — 内容本身清晰，但视觉输出粗糙，增加了读者的理解成本。

Feynman Skills 同时解决这两个问题。用费曼的方式写，用好产品的方式呈现。

---

## 包含的 Skills

| Skill | 层级 | 适用场景 |
|-------|------|---------|
| `technical-writing-craft` | **内容层** — 文章风格与组织 | 当你想让读者真正*理解*，而不只是*知道* |
| `vibe-coding` | **呈现层** — UI 与视觉 | 当你想把内容做成精美的交互页面 |

---

## 安装方式

### 插件方式（推荐）

在 Claude Code 中运行：

```
/plugin marketplace add webaifei/feynman-skills
/plugin install feynman-skills@feynman-skills
/reload-plugins
```

### 手动方式

追加到项目的 `CLAUDE.md`：

```bash
echo "" >> CLAUDE.md
curl https://raw.githubusercontent.com/webaifei/feynman-skills/main/CLAUDE.md >> CLAUDE.md
```

---

## 使用方法

两个 Skill 按顺序配合使用：

```
/technical-writing-craft   ← 第一步：组织内容结构
/vibe-coding               ← 第二步：做成好看的页面
```

或者在请求中提及：

> "用 technical-writing-craft 帮我写一篇关于零知识证明的文章，然后用 vibe-coding 做成一个干净的 HTML 页面"

---

## Skill 详情

### technical-writing-craft — 内容层

六个写作模式，区分"传递信息的写作"和"改变思维方式的写作"：

| 模式 | 作用 |
|------|------|
| **框架先行** | 找到一个框架，让所有事实都显得必然，而不是偶然堆砌 |
| **例子节奏** | 遥远 → 熟悉 → 当下。先训练直觉，再提出主张 |
| **锚点句** | 一句话能展开成整篇，也能把整篇压缩回来 |
| **先共情再纠正** | 先引用常见误判，读者感到被理解后才会打开接受通道 |
| **身份结尾** | 结尾告诉读者"你现在是谁"，而不是"你接下来要做什么" |
| **生成-验证不对称** | 帮读者看清自身价值在于判断，而不是生产 |

### vibe-coding — 呈现层

引导你用 AI 把内容变成可运行的精美 UI——不需要深厚的工程背景：

| 原则 | 含义 |
|------|------|
| **原型替代 Mockup** | 用 30 分钟做出可运行的页面，而不是 Figma 静态稿 |
| **迭代式构建** | 把复杂 UI 拆成小块交给 AI，通过追问逐步完善 |
| **了解边界** | 适合文章、落地页、文档；生产级系统仍需工程评审 |

---

## 添加新 Skill

1. 创建 `skills/<skill-name>/SKILL.md`：

```markdown
---
name: skill-name
description: 一句话——什么场景下调用这个 skill。
license: MIT
---

# Skill 标题

...内容...
```

2. 添加到 `.claude-plugin/plugin.json`：

```json
{
  "skills": [
    "./skills/technical-writing-craft",
    "./skills/your-new-skill"
  ]
}
```

3. 更新 `marketplace.json` 版本号，提交推送。

---

## License

MIT
