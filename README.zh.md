# Claude Skills

一套精选的 [Claude Code](https://claude.ai/code) Skills，涵盖技术写作、AI 辅助开发和咨询分析场景。

[English](./README.md)

---

## 包含的 Skills

| Skill | 触发场景 | 描述 |
|-------|---------|------|
| `technical-writing-craft` | 撰写技术文章、博客、解释性文档 | 框架先行的写作模式，让复杂概念变得深刻且易记 |
| `vibe-coding` | 用 AI 构建软件 / 无代码原型开发 | 指导非工程师用 AI 工具构建可运行软件 |

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

新项目直接下载：

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/webaifei/feynman-skills/main/CLAUDE.md
```

已有项目追加内容：

```bash
echo "" >> CLAUDE.md
curl https://raw.githubusercontent.com/webaifei/feynman-skills/main/CLAUDE.md >> CLAUDE.md
```

---

## 使用方法

安装后 Skills 自动生效，也可以手动调用：

```
/technical-writing-craft
/vibe-coding
```

或者在请求中提及：

> "用 technical-writing-craft 帮我写这篇文章"

---

## Skills 详情

### technical-writing-craft

适用场景：撰写技术文章、博客或解释性文档，尤其是需要解释复杂工程概念、类比推理或行业变迁时——输出需要有说服力且令人难忘，而不只是传递信息。

**核心写作模式：**
- **框架先行** — 先找到统一框架，再挂事实，不堆砌信息
- **例子节奏** — 由远及近：遥远具象 → 专业领域 → 当下现实
- **锚点句** — 一句话能展开整篇，也能压缩整篇
- **先共情误判再纠正** — 先引用读者常说的话，再温和给出正确框架
- **身份结尾** — 结尾给读者一个身份重定位，不给 to-do list

### vibe-coding

适用场景：用 AI 工具生成代码、在没有深厚技术背景的情况下构建原型，或探索非工程师如何通过自然语言创建可运行软件。

**核心原则：**
- Vibe coding 是一种独立技能，不只是提示词工程
- 用 30 分钟构建可运行原型，替代 Figma 静态稿
- 迭代构建：把复杂问题拆成 AI 友好的小块逐步实现
- 了解边界：适合 MVP 验证，生产级系统仍需工程评审

---

## 如何添加新 Skill

1. 创建 `skills/<skill-name>/SKILL.md`，包含以下 frontmatter：

```markdown
---
name: skill-name
description: 一句话说明——什么场景下使用这个 skill。
license: MIT
---

# Skill 标题

...skill 内容...
```

2. 将路径添加到 `.claude-plugin/plugin.json`：

```json
{
  "skills": [
    "./skills/technical-writing-craft",
    "./skills/vibe-coding",
    "./skills/your-new-skill"
  ]
}
```

3. 更新 `.claude-plugin/marketplace.json` 的版本号。

4. 提交并推送——用户运行 `/reload-plugins` 后即可使用新 skill。

---

## License

MIT
