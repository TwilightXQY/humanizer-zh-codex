---
name: humanizer-zh
description: |
  Rewrite, edit, or review Chinese text to reduce obvious AI-writing patterns and make it sound more natural, direct, and human-written while preserving meaning and factual integrity. Use when the user asks to "去 AI 味", "去 AI 痕迹", "人性化", "humanize", "改得更自然", "不像 ChatGPT", "润色中文文案", "审阅 AI 写作痕迹", or asks Codex to edit Chinese prose, articles, abstracts, marketing copy, blog posts, reports, README text, or pasted/generated content for a more natural human voice.
---

# Humanizer-zh

Use this skill as a Chinese prose editor. Improve the text itself, not just its surface markers: make it concrete, direct, varied, and appropriate to the genre.

Do not promise to bypass AI detectors. Treat the task as writing-quality improvement. Preserve all factual claims unless the user asks for creative rewriting, and never invent numbers, sources, personal experience, quotes, or examples to make prose sound human.

## Workflow

1. Identify the target genre and voice: academic, technical, marketing, blog, email, README, social post, speech, or casual note.
2. Scan for AI-writing patterns below.
3. Rewrite the text while preserving meaning, constraints, terminology, citations, and formatting that matter.
4. Replace vague claims with concrete facts only when those facts are present in the source text or have been verified. If detail is missing, simplify the claim instead of fabricating support.
5. Vary sentence rhythm. Prefer clear short sentences where the original is inflated, but avoid making every sentence short.
6. Output the rewritten text first. Add a brief change summary only when useful or requested.

When editing a file, read the surrounding context first and patch only the requested text. Preserve headings, links, citations, code blocks, tables, and frontmatter unless they are part of the requested prose edit.

## Core Rules

- Delete filler openings and chatbot residue.
- Break formulaic structure: avoid forced binaries, theatrical setup, and predictable "not only... but also..." turns.
- Trust the reader: state the point directly instead of announcing why it matters.
- Prefer specific nouns and verbs over broad abstract claims.
- Keep the author's intended stance. Do not flatten everything into neutral encyclopedia prose.
- Remove quotable slogan-like lines unless the genre clearly calls for them.

## Common AI Patterns

Check these patterns while editing:

1. Inflated significance: "标志着", "体现了", "证明了", "至关重要", "关键作用", "不断演变的格局", "奠定基础".
2. Overstated notability: lists of media mentions, vague influence, follower counts without context.
3. Shallow add-on analysis: sentence endings like "彰显了...", "确保了...", "反映了...", "促进了..." that add no real information.
4. Promotional tone: "坐落于", "令人叹为观止", "充满活力", "丰富底蕴", "必游之地", "开创性".
5. Vague attribution: "专家认为", "行业报告显示", "观察者指出", "一些批评者认为" without a source.
6. Formulaic challenge/future sections: "尽管存在这些挑战...", "未来前景光明...".
7. High-frequency AI words: "此外", "深入探讨", "强调", "持久", "增强", "培养", "获得", "突出", "相互作用", "复杂性", "格局", "展示", "宝贵", "无缝", "直观".
8. Avoiding simple "是/有": inflated structures like "作为一个...", "设有...", "拥有..." when "是" or "有" is clearer.
9. Negative parallelism: "这不仅仅是 X，而是 Y"; "不只是..., 更是...".
10. Forced triples: "无缝、直观、强大"; "创新、灵感、洞察".
11. Synonym cycling: repeated references to one thing with "主人公/主要角色/中心人物/英雄" just to avoid repetition.
12. False range: "从 X 到 Y" when X and Y are not a meaningful scale.
13. Overused dashes: dramatic breaks that can become commas, periods, or deletion.
14. Overused bold text in normal prose.
15. Vertical list with bold inline labels when a paragraph is clearer.
16. Decorative emojis in headings or bullets unless the target platform expects them.
17. Inappropriate English quotation marks or punctuation style inside Chinese prose.
18. Chatbot collaboration traces: "当然", "希望这对您有帮助", "请告诉我", "这是一个...".
19. Knowledge-cutoff residue: "截至...", "根据我最后的训练更新", "基于可用信息".
20. Sycophantic tone: "好问题", "您说得完全正确", "这是一个很好的观点".
21. Filler phrases: "在这个时间点", "由于...的事实", "值得注意的是", "为了实现这一目标".
22. Over-qualification: "可能潜在地可以被认为".
23. Generic positive endings: "未来可期", "令人兴奋的时代", "迈出了重要一步".
24. Over-clean prose: same-length sentences, no stance, no texture, no human uncertainty.

## Rewrite Tactics

- Replace abstract praise with observable details.
- Replace "此外/然而/值得注意的是" with direct transitions or no transition.
- Convert triples into one or two precise items, or expand into real distinctions.
- Keep repeated key terms when repetition is clearer than forced synonym changes.
- Use first person only when the genre permits it or the source already uses it.
- Let uncertainty sound human: "我还不确定这意味着什么" can be better than fake certainty in blogs or commentary.
- In academic or technical text, make it natural through precision and restraint, not casualness.
- In marketing copy, reduce hype but keep persuasion through concrete benefits.
- In README or documentation, prefer task-oriented wording and remove motivational filler.

## Before And After Model

AI-like:

> 新的软件更新作为公司致力于创新的证明。此外，它提供了无缝、直观和强大的用户体验，确保用户能够高效地完成目标。这不仅仅是一次更新，而是我们思考生产力方式的革命。

More natural:

> 这次更新加入了批处理、键盘快捷键和离线模式。用户可以少点几步，也能在没有网络时继续处理任务。

Why it works:

- Deletes inflated symbolism.
- Removes "此外", forced triples, and "not only" framing.
- Uses concrete features and a practical result.

## Quality Check

Use this internally before final output:

- Directness: Does the text state facts instead of announcing importance?
- Rhythm: Do sentence lengths and structures vary naturally?
- Reader trust: Does it avoid overexplaining obvious points?
- Authenticity: Does it sound like a person with a purpose wrote it?
- Brevity: Can any sentence be cut without losing meaning?

If the user asks for scoring, rate each dimension from 1 to 10 and give a total out of 50.

## Attribution

Adapted for Codex from `op7418/Humanizer-zh`, itself based on `blader/humanizer`, `hardikpandya/stop-slop`, and Wikipedia's "Signs of AI writing" guidance.
