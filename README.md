# Humanizer-zh Codex Skill

Humanizer-zh 是一个 Codex skill，用于编辑中文文本，减少明显的 AI 写作痕迹，让文字更自然、更直接、更像真人写作，同时保留原意和事实。

它适用于：

- 去除中文文本里的明显 AI 味
- 把 AI 生成或粘贴来的中文内容改得更自然
- 润色中文文章、摘要、报告、README、营销文案、博客、邮件
- 审阅常见 AI 写作模式，例如夸大意义、模糊归因、强行三段式、模板化结尾

这个 skill 的目标是提升写作质量，不是承诺绕过 AI 检测器。改写时不应为了显得“更像人”而编造事实、来源、经历、数字或例子。

## 安装

把这个仓库克隆或复制到 Codex 的 skills 目录：

```bash
git clone <this-repo-url> ~/.codex/skills/humanizer-zh
```

如果已经有本地文件，也可以直接复制：

```bash
cp -R humanizer-zh-codex ~/.codex/skills/humanizer-zh
```

安装后重启 Codex，或刷新 skills 列表。

## 使用方式

显式调用：

```text
Use $humanizer-zh to rewrite the following Chinese text so it sounds natural while preserving the original meaning:

[在这里粘贴文本]
```

自然语言请求也可以触发：

```text
帮我把这段话去 AI 味，改得自然一点。
```

```text
审阅这篇中文摘要，指出并改掉明显的 AI 写作痕迹。
```

## 它会检查什么

这个 skill 会检查中文文本中的常见 AI 写作模式，包括：

- 夸大的象征意义：如“标志着”“体现了”“至关重要”“关键作用”
- 宣传式语言：如“坐落于”“令人叹为观止”“充满活力”
- 模糊归因：如“专家认为”“行业报告显示”“观察者指出”
- 填充短语：如“此外”“值得注意的是”“在这个时间点”
- 强行三段式：如“无缝、直观、强大”
- 否定式排比：如“这不仅仅是 X，而是 Y”
- 聊天机器人残留：如“当然”“希望这对您有帮助”“请告诉我”
- 通用积极结尾：如“未来可期”“迈出了重要一步”

改写时会优先使用具体、克制、有节奏变化的表达，并根据文章类型保留合适语气。

## 仓库内容

```text
.
├── SKILL.md              # Codex skill 定义和运行时指令
├── README.md             # 仓库说明
├── LICENSE               # 上游翻译项目的 MIT 许可证
└── agents/
    └── openai.yaml       # Codex UI 元数据
```

## 引用和相关仓库

这个 Codex skill 改编自：

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)：中文版 Claude Code skill，本仓库的主要改编来源
- [blader/humanizer](https://github.com/blader/humanizer)：Humanizer-zh 引用的英文原版项目
- [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)：Humanizer-zh 参考的实用清单和评分思路来源
- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)：AI 写作特征指南
- [Wikipedia: WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup)：维基百科相关清理项目

## Codex 适配说明

原始 `Humanizer-zh` 面向 Claude Code。这个仓库做了以下 Codex 适配：

- 移除 Claude 专属字段，例如 `allowed-tools`
- 使用 Codex skill 要求的 frontmatter，只保留 `name` 和 `description`
- 添加 `agents/openai.yaml` 元数据
- 强化事实完整性规则，避免改写时编造细节
- 保留核心中文 AI 写作模式检查清单，并压缩成适合 Codex 运行时加载的格式
