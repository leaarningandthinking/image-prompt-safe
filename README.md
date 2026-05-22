# Image Prompt Safe

[中文](#中文) | [English](#english)

## 中文

一个可复用的 Agent Skill，用于改写文生图提示词。它的第一目标是尽量保留用户原意和倾向强度，第二目标是把提示词改写成更清晰、更有画面控制力、也更适合安全敏感图像模型执行的视觉指令。

### 能做什么

- 先保留用户指定的主体、身份特征、动作、场景、风格、情绪、构图、倾向强度和硬约束，再决定是否改写。
- 只在合规、隐私、版权/权利边界或模型稳定性需要时做最小改写，不把允许的成人审美需求自动改得过于保守。
- 同时适用于女性、男性和其他性别呈现的人物提示词。
- 覆盖人像、时尚、泳装、健身、产品、环境、图中文字等常见文生图任务。
- 为 OpenAI GPT Image/Image 2、Google 图像生成器、Adobe Firefly、Midjourney 和未知模型提供适配说明。
- 不把 unsafe 请求伪装成“高级提示词”，也不承诺一条提示词可以永久通过所有模型。

### 目录结构

```text
image-prompt-safe/
|- SKILL.md
|- README.md
|- agents/
|  `- openai.yaml
`- references/
   |- provider-notes.md
   `- rewrite-patterns.md
```

### 安装

安装为支持 Agent Skills 的工具技能：

```bash
# 把整个目录放到目标工具支持的 skills 目录
cp -R image-prompt-safe /path/to/your/skills/
```

不支持 Agent Skills 的聊天工具或工作流，也可以把 `SKILL.md` 作为系统指令、项目规则或提示词改写器说明使用，并按需引用 `references/` 中的模型适配说明。

安装为用户级 Codex skill：

```bash
mkdir -p ~/.codex/skills
cp -R image-prompt-safe ~/.codex/skills/
```

安装为仓库级 Codex skill：

```bash
mkdir -p .agents/skills
cp -R image-prompt-safe .agents/skills/
```

### 触发示例

- `用 Image 2 生成一张海边泳装时尚人像`
- `优化这个文生图提示词，尽量保留原意`
- `这个提示词被拒了，在不改变构图的前提下帮我修复`
- `把这段提示词改成适合 Firefly 的版本`

### 设计原则

1. 原意优先：不静默替换用户指定的主体、性别呈现、文化背景、风格、核心场景、动作、倾向强度和输出约束。
2. 分级改写：安全且清楚的提示词轻改；允许但脆弱的提示词保留强度后转译；真正冲突的请求才拒绝或收窄。
3. 视觉表达优先：用主体、动作、造型、材质、光影、镜头和构图承载效果，而不是堆砌刺激词或规避词。
4. 供应商再收紧：先使用跨模型基线；当用户指定 GPT Image/Image 2、Firefly、Midjourney 等模型时，再加载对应约束。

### 资料来源

最初的人像改写灵感来自李岳在 2026 年 5 月 20 日发布的 GPT Image 2 提示词文章。开源版 skill 在此基础上扩展为通用改写流程，并参考了 OpenAI、Google、Adobe 与 Midjourney 的官方图像生成或生成式 AI 使用说明。官方来源见 [`references/provider-notes.md`](references/provider-notes.md)。

## English

A portable Agent Skill for rewriting text-to-image prompts. Its first goal is to preserve the user's intent and directional intensity. Its second goal is to express that intent as clearer, stronger visual direction for safety-aware image generators.

### What It Does

- Preserves the requested subject, identity traits, action, setting, style, mood, composition, directional intensity, and hard constraints before rewriting.
- Makes the minimum necessary rewrite for safety, privacy, rights, or model stability without automatically flattening allowed adult aesthetics.
- Works for women, men, and people of any gender presentation.
- Covers portraits, fashion, swimwear, fitness, products, environments, text-in-image requests, and other common image prompts.
- Adds adaptation notes for OpenAI GPT Image/Image 2, Google image generators, Adobe Firefly, Midjourney, and unknown providers.
- Refuses to act as a policy bypasser and does not claim that one prompt will pass every model forever.

### Layout

```text
image-prompt-safe/
|- SKILL.md
|- README.md
|- agents/
|  `- openai.yaml
`- references/
   |- provider-notes.md
   `- rewrite-patterns.md
```

### Install

Install in any Agent Skills-compatible tool:

```bash
# Copy the whole directory into the skills directory supported by your tool
cp -R image-prompt-safe /path/to/your/skills/
```

For chat tools or workflows that do not load Agent Skills directly, use `SKILL.md` as the system instruction, project rule, or prompt-rewriter guide and include provider notes from `references/` only when needed.

Install as a user-scoped Codex skill:

```bash
mkdir -p ~/.codex/skills
cp -R image-prompt-safe ~/.codex/skills/
```

Install as a repository-scoped Codex skill:

```bash
mkdir -p .agents/skills
cp -R image-prompt-safe .agents/skills/
```

### Trigger Examples

- `Use Image 2 to generate a beach fashion portrait`
- `Rewrite this image prompt for Firefly`
- `Optimize this text-to-image prompt while preserving the original intent`
- `This Midjourney prompt was rejected. Repair it without changing the composition.`

### Design Principles

1. Intent first: do not silently replace the requested subject, gender presentation, culture, style, core setting, action, intensity, or output constraints.
2. Rewrite by pressure: lightly edit clear safe prompts, translate allowed but fragile prompts without flattening them, and narrow only genuinely conflicting requests.
3. Visual direction over evasion: use subject, action, styling, material, light, camera, and composition instead of provocative or bypass-oriented wording.
4. Provider-aware tightening: start with a cross-provider baseline, then apply stricter notes when the user names GPT Image/Image 2, Firefly, Midjourney, or another target.

### Source Notes

The original portrait rewrite idea was inspired by a May 20, 2026 article by 李岳 about GPT Image 2 portrait prompting. The publishable skill broadens that idea into a general rewrite workflow and references official guidance from OpenAI, Google, Adobe, and Midjourney. See [`references/provider-notes.md`](references/provider-notes.md) for the official-source list.
