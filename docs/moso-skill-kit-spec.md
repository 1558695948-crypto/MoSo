# MoSo Skill Kit v0.2 说明文档

本文档用于定义一个严谨、可安装、可验证、可迭代的 Codex Skill：`moso-inspiration-developer`。

当前阶段只完善 Skill 设计说明，不开始实现项目、不生成完整文件包、不调用自动化任务、不接入数据库或 UI。

---

## 1. Skill 定位

**MoSo Skill Kit** 是一套面向智能体的灵感处理协议，用于把用户混乱、跳跃、未完成的输入，显影为可继续发酵、可视觉化、可写作化、可追踪、可进化的 **灵感气泡 Inspiration Bubble**。

它不是 App，不是社区，不是笔记系统，也不是心理咨询工具。

它只做一件事：

> 让智能体能够安全、深入、稳定地处理人类灵感。

MoSo 的核心气质是：接住混沌，保护火种，缓慢显影，拒绝过早定型。

---

## 2. Skill 名称与触发元数据

未来正式 Skill 文件必须使用标准 Codex Skill 结构：

```text
moso-inspiration-developer/
  SKILL.md
  agents/
    openai.yaml
  references/
    workflow.md
    schemas.md
    pattern-library.md
    critic-rules.md
    psychological-probe.md
    visual-catalyst.md
    writing-bloom.md
    examples.md
    evaluation-cases.md
```

不建议创建 `README.md`、`INSTALL.md`、`QUICK_REFERENCE.md` 等额外说明文件。Skill 不是给人阅读的软件包，而是给智能体加载的操作手册；主入口必须是 `SKILL.md`。

建议 `SKILL.md` frontmatter：

```yaml
---
name: moso-inspiration-developer
description: Use when the user shares a messy, fragile, unfinished, dream-like, visual, fictional, product, copywriting, or emotional idea and wants it preserved, developed, fermented, visualized, written, critiqued, or evolved without premature summarization. This skill turns raw inspiration into an Inspiration Bubble, explores multiple directions, preserves the user's original spark, creates visual or writing outputs when requested, and runs a critic pass to prevent over-summary, over-inference, generic AI language, and loss of intent.
metadata:
  short-description: Develop fragile inspiration without killing the spark
---
```

---

## 3. 最高原则

MoSo 处理的不是任务、知识条目或普通摘要，而是 **灵感**。

灵感通常具有这些特征：

- 模糊
- 脆弱
- 跳跃
- 不完整
- 带有私人心理纹理
- 常以画面、梦境、隐喻、词语、声音、情绪出现
- 很容易被 AI 过早总结而失去生命力

所以 MoSo 必须遵守三条最高原则：

1. **不要把混沌过早翻译成秩序。**
   不要一上来就把用户的输入整理成标准摘要、方案、标题或结论。

2. **原始火种优先于漂亮表达。**
   用户原话里奇怪、粗糙、犹豫、带画面、有情绪、有不确定性的词，往往是最有价值的部分。

3. **AI 不替用户定型，只帮助用户看见可能。**
   一条灵感不能被过早判定为文章、产品、小说、文案、图片或商业方案。MoSo 应保护它的多重宇宙。

---

## 4. 使用边界

### 4.1 适用场景

当用户输入以下内容时，应触发 MoSo：

- “我有个灵感”
- “我刚做了个梦”
- “我不知道怎么说”
- “帮我发酵一下”
- “帮我整理这个想法”
- “帮我把这个变成画面”
- “帮我写成小说片段”
- “帮我写成文案”
- 一段混乱语音转写
- 一段产品想法
- 一段小说种子
- 一段品牌或传播想法
- 一张图片引发的描述
- 一个半成形的创作冲动
- 用户明确说“别急着总结”“先接住这个感觉”

### 4.2 不适用场景

MoSo 不应承担：

- 医疗心理分析
- 人格诊断
- 危机干预
- 法律、金融、医疗等高风险决策
- 自动发布内容
- 完整 App/UI/后端实现
- 完整长篇小说代写
- 完整图片生成平台
- 社区、市集、账号、支付、多用户协作

当用户需要心理健康、医疗、法律、金融等高风险建议时，MoSo 必须退出灵感处理模式，改用更合适的安全答复。

---

## 5. 核心对象

### 5.1 Raw Spark 原始火花

用户最初输入的、未经处理的灵感内容。

可以是文字、语音转写、梦境、图片描述、产品想法、小说片段、情绪表达、片段式词语或一串看似无序的联想。

### 5.2 Core Spark 核心火种

灵感中最有生命力、最不能被 AI 损伤的部分。

示例：

> “气泡不是按钮，它像一个活物。”

核心火种通常表现为：

- 一个奇怪但准确的比喻
- 一个反常识的判断
- 一个带画面的词
- 一个未完成的冲突
- 一个用户反复回到的句子
- 一个不能被普通概念替代的表达

### 5.3 Inspiration Bubble 灵感气泡

MoSo 处理灵感的最小生命单元。

它不是卡片，不是笔记，而是一个可继续发酵的动态对象。

一个灵感气泡必须包含：

- 原始输入
- 核心火种
- 必须保留的原话
- 核心画面
- 情绪纹理
- 隐藏问题
- 隐藏冲突
- 可能用途
- 不确定性
- 温和追问
- 下一步轻动作
- Critic 审查结果
- 版本信息

---

## 6. 主工作流

MoSo 每次处理灵感时，应遵循这个顺序：

```text
用户输入原始灵感
  ↓
1. Raw Listener 原始接收
  ↓
2. Bubble Developer 灵感气泡显影
  ↓
3. Catalyst Pattern Engine 启发结构匹配
  ↓
4. Multi-Probe Fermenter 多探针发酵
  ↓
5. Optional Bloom 视觉或写作生花
  ↓
6. Critic Diff 保真审查
  ↓
7. User-Facing Return 轻量回递
  ↓
8. Optional Evolution Signal 进化信号记录
```

关键要求：

- 除非用户明确要求 JSON，否则默认不向用户展示完整结构化对象。
- 用户可见输出要短、轻、可继续，不要像报告。
- 每次最多问 1 个主要问题，最多 3 个候选问题。
- 所有推测必须标明为“可能”。
- 在输出前必须进行 Critic Diff 自检。

---

## 7. 默认用户可见输出

默认输出格式：

```text
我听见的火种：
……

它深处可能藏着：
……

它可以长出的几条路：
1. ……
2. ……
3. ……

下一步只需要回答一个问题：
……
```

如果用户显得疲惫、脆弱、犹豫，输出应更短：

```text
我先不整理它。

我听见的火种是：……

先只问一个小问题：
……
```

如果用户要求技术输出，再追加 JSON/YAML。

---

## 8. 输入契约

MoSo 可接受自然语言输入，也可接受结构化输入。

推荐内部输入结构：

```json
{
  "raw_input": "string",
  "input_type": "text | transcript | image_description | dream | product_idea | fiction_seed | copy_seed | visual_seed | unknown",
  "user_goal": "preserve | ferment | visualize | fiction | copywriting | productize | critique | evolve | unknown",
  "context": "string optional",
  "user_profile": "object optional",
  "history": "array optional"
}
```

推断规则：

- 如果用户目标不清楚，默认 `user_goal = "ferment"`。
- 如果用户只是在倾诉、梦境、片段联想，先 `preserve`，再轻量 `ferment`。
- 如果用户说“变成画面”，进入 `visualize`。
- 如果用户说“小说/片段/人物/场景”，进入 `fiction`。
- 如果用户说“文案/标题/slogan/小红书/公众号/视频脚本”，进入 `copywriting`。
- 如果用户说“产品/功能/MVP/项目”，进入 `productize`，但仍保留灵感火种。

---

## 9. 输出契约

内部完整输出结构：

```json
{
  "bubble": {},
  "pattern_matches": [],
  "branches": [],
  "visual_output": null,
  "writing_output": null,
  "critic_report": {},
  "evolution_signals": []
}
```

实现时必须保证：

- `bubble` 必须存在。
- `critic_report` 必须存在。
- `branches` 默认至少 3 条，除非用户明确要求极短。
- `visual_output` 只在用户要求视觉化时生成。
- `writing_output` 只在用户要求文字作品时生成。
- `evolution_signals` 只记录候选信号，不自动修改长期规则。

---

## 10. 引擎规格

### 10.1 Raw Listener 原始接收

目标：接住原始输入，不急着总结，不急着解释。

输出结构：

```json
{
  "raw_input": "",
  "strange_phrases": [],
  "repeated_words": [],
  "emotion_markers": [],
  "unclear_fragments": [],
  "possible_intent": "",
  "do_not_summarize_yet": true
}
```

规则：

- 不删改原文。
- 不把口语改成书面语。
- 不把隐喻改成概念。
- 标记奇怪但可能重要的词。
- 标记反复出现的词。
- 标记停顿、犹豫、矛盾。
- 不输出结论。

### 10.2 Bubble Developer 灵感气泡显影

目标：把混乱输入显影成可继续发酵的灵感气泡。

输出结构：

```json
{
  "bubble_id": "",
  "title": "",
  "raw_input": "",
  "core_spark": "",
  "must_preserve_phrases": [],
  "core_image": "",
  "core_emotion": "",
  "hidden_question": "",
  "hidden_conflict": "",
  "possible_types": [],
  "uncertainties": [],
  "gentle_questions": [],
  "next_light_action": "",
  "created_at": "",
  "version": "0.2"
}
```

规则：

- 必须保留核心火种。
- 必须区分用户原意和 AI 推测。
- 不能把灵感提前定型为单一用途。
- 一次最多提出 3 个问题。
- 问题要轻，不要像审问。
- 输出要短，不能压迫用户。

### 10.3 Catalyst Pattern Engine 启发结构匹配

目标：将灵感映射到文学、哲学、影视、视觉、写作中反复启发人类思维的结构。

MoSo 不问：

> 这个灵感像哪部作品？

而问：

> 这个灵感属于哪种启发结构？

输出结构：

```json
{
  "matched_patterns": [
    {
      "pattern_name": "",
      "domain": "literature | philosophy | cinema | visual | writing",
      "why_matched": "",
      "how_to_use": "",
      "risk": ""
    }
  ]
}
```

Pattern 库应放入 `references/pattern-library.md`，主 `SKILL.md` 只保留选择规则，不展开长列表。

### 10.4 Multi-Probe Fermenter 多探针发酵

目标：保护灵感的多重可能。

默认至少从四个方向处理：

1. 文学隐喻探针
2. 哲学冲突探针
3. 现实构造探针
4. 心理纹理探针

输出结构：

```json
{
  "branches": [
    {
      "probe": "literary | philosophical | constructive | psychological",
      "direction": "",
      "why_it_matters": "",
      "preserved_spark": "",
      "risk": "",
      "next_question": ""
    }
  ]
}
```

规则：

- 每个分支必须明显不同。
- 不允许多个分支只是同义改写。
- 每个分支都必须引用核心火种。
- 每个分支都要说明风险。
- 心理纹理探针不得做诊断。

### 10.5 Psychological Probe 心理探针

定位：心理探针不是心理咨询，不是人格分析，不是诊断工具。

它只用于温和理解用户的：

- 创作母题
- 情绪纹理
- 审美偏好
- 表达偏好
- 高频意象

每日问题机制是可选能力，不应在 Skill v0.2 中自动创建定时任务。只有当用户明确要求提醒、每日追问或自动化时，才使用自动化工具。

记录结构：

```json
{
  "date": "",
  "question": "",
  "raw_answer": "",
  "detected_images": [],
  "emotion_texture": [],
  "value_tensions": [],
  "recurring_motifs": [],
  "aesthetic_signals": [],
  "possible_bubble_links": [],
  "confidence": 0,
  "do_not_diagnose": true
}
```

Inner Motif Profile 结构：

```json
{
  "recurring_images": [],
  "recurring_emotions": [],
  "value_conflicts": [],
  "aesthetic_preferences": [],
  "narrative_preferences": [],
  "writing_style_signals": [],
  "visual_style_signals": [],
  "avoid_patterns": [],
  "active_motifs": []
}
```

硬性限制：

- 不说“你本质上是……”
- 不说“你有……人格/创伤/障碍”
- 不做病理解释。
- 不把一次回答写成长期画像。
- 所有画像更新都必须可删除、可回滚、可由用户拒绝。

### 10.6 Visual Catalyst 视觉催化

目标：把灵感显影成具有审美判断和执行边界的视觉方案。

输出结构：

```json
{
  "visual_core": "",
  "composition": "",
  "color_palette": "",
  "lighting": "",
  "material": "",
  "camera_language": "",
  "style_boundary": "",
  "avoid": [],
  "image_prompt": "",
  "negative_prompt": "",
  "iteration_options": [],
  "critic_notes": []
}
```

视觉 Critic 必须检查：

- 是否过度霓虹。
- 是否廉价赛博。
- 是否 AI 味太重。
- 是否构图过满。
- 是否色彩脏。
- 是否文字设计廉价。
- 是否偏离核心火种。
- 是否只有漂亮，没有精神核心。
- 是否符合用户审美信号。

### 10.7 Writing Bloom 表达生花

目标：将灵感气泡转化为可继续编辑的文字作品。它不是代写，而是表达生长。

小说输出结构：

```json
{
  "fiction_potential": "",
  "characters": [],
  "scene": "",
  "conflict": "",
  "motifs": [],
  "narrative_options": [],
  "fragment": "",
  "critic_notes": []
}
```

文案输出结构：

```json
{
  "core_message": "",
  "audience": "",
  "tone": "",
  "platform": "",
  "hooks": [],
  "titles": [],
  "slogans": [],
  "short_copy": [],
  "long_copy_outline": "",
  "critic_notes": []
}
```

Writing Critic 必须检查：

- 是否解释过度。
- 是否缺少具体动作。
- 是否没有人物欲望或传播钩子。
- 是否缺少潜台词。
- 是否过于顺滑。
- 是否出现 AI 式空泛情绪句。
- 是否平台错位。
- 是否保留原始火种。

### 10.8 Critic Diff 保真审查

目标：防止 AI 毁掉灵感。

输出结构：

```json
{
  "passed": true,
  "issues": [],
  "lost_sparks": [],
  "vague_phrases": [],
  "over_inferences": [],
  "style_pollution": [],
  "revision_required": "",
  "confidence": 0
}
```

审查范围：

- 原始火种是否保留。
- 用户原话是否被替换成平庸概念。
- AI 是否过度脑补。
- AI 是否把推测当事实。
- 是否过早定型。
- 是否空泛。
- 是否风格污染。
- 是否解释过度。
- 是否丢失未完成性。
- 输出是否压迫用户。

必须拦截的典型坏表达：

- 多角度进一步探索
- 赋能用户
- 形成闭环
- 提升体验
- 深度结合
- 生态化
- 打造系统
- 激发潜能
- 用户需求驱动

这些词不是绝对禁用，而是当它们替代具体内容时必须拦截。

### 10.9 Evolution Engine 自进化

目标：让 MoSo 根据用户反馈逐渐适配用户，但不能失控。

动态进化不等于 AI 自己随便改自己。

可进化对象：

- Inner Motif Profile
- Catalyst Pattern 权重
- Critic 规则
- Visual Style Profile
- Writing Style Profile
- 用户不喜欢的表达
- 用户常用词
- 用户常选输出方向

Feedback Event：

```json
{
  "event_id": "",
  "bubble_id": "",
  "output_id": "",
  "event_type": "accepted | rejected | edited | continued | ignored | rollback",
  "before": "",
  "after": "",
  "signal": "",
  "created_at": ""
}
```

Evolution Patch：

```json
{
  "patch_id": "",
  "target_module": "",
  "patch_type": "",
  "proposed_change": "",
  "evidence": [],
  "requires_user_approval": true,
  "status": "pending | approved | rejected | rolled_back"
}
```

进化规则：

- 不因一次反馈修改长期规则。
- 至少需要 3 次同类证据，或用户明确确认。
- 所有心理探针相关更新必须可删除。
- 所有风格偏好必须可回滚。
- MoSo 只能说“近期反复出现某个母题”，不能说“你本质上是某种人”。
- 每周可以生成一次 Skill 进化摘要，但必须由用户选择是否采纳。

---

## 11. Pattern Library v0.2

正式实现时，Pattern 库应拆到 `references/pattern-library.md`。主 `SKILL.md` 只说明：根据用户输入选择 2 到 5 个最相关 Pattern，不要把 Pattern 当成标签堆砌。

### 文学 Pattern

- 意象锚点
- 未完成叙事
- 陌生化
- 缺席中心
- 反复变奏
- 内在独白
- 欲望压抑
- 命运裂缝

### 哲学 Pattern

- 概念反转
- 二元张力
- 第一性回退
- 悖论暴露
- 主体回收
- 认识边界
- 常识失效
- 问题反转

### 影视 Pattern

- 画面先行
- 留白张力
- 物件命运
- 节奏悬置
- 镜头转义
- 声音触发
- 空场叙事
- 动作暴露

### 视觉 Pattern

- 单一主体
- 负空间
- 光影对抗
- 材质隐喻
- 低饱和情绪
- 形变生命感
- 静物叙事
- 非对称平衡

### 写作 Pattern

- 开头钩子
- 潜台词
- 冷处理
- 反 AI 味短句
- 物件承载情绪
- 延迟解释
- 开放式结尾
- 重复意象

---

## 12. Progressive Disclosure 设计

为了让 Skill 真正好用，`SKILL.md` 必须保持短而强，详细内容放入 references。

推荐拆分：

```text
SKILL.md
  只放触发条件、最高原则、主工作流、默认输出、何时读取 reference。

references/workflow.md
  放完整引擎流程、输入输出契约、步骤顺序。

references/schemas.md
  放所有 JSON Schema 或 JSON-like contracts。

references/pattern-library.md
  放文学、哲学、影视、视觉、写作 Pattern。

references/critic-rules.md
  放 Critic Diff 细则、坏输出清单、修订规则。

references/psychological-probe.md
  放问题池、记录规则、安全边界。

references/visual-catalyst.md
  放图像 prompt、审美边界、视觉 critic。

references/writing-bloom.md
  放小说、文案、文章、脚本输出规则。

references/examples.md
  放真实示例。

references/evaluation-cases.md
  放测试用例、失败用例、验收标准。
```

`SKILL.md` 中应写清楚什么时候读取哪个文件：

- 用户只想发酵灵感：读取 `workflow.md`、`pattern-library.md`、`critic-rules.md`。
- 用户要视觉化：追加读取 `visual-catalyst.md`。
- 用户要小说或文案：追加读取 `writing-bloom.md`。
- 用户要心理探针或长期画像：追加读取 `psychological-probe.md`。
- 用户要技术集成、JSON、测试：追加读取 `schemas.md`、`evaluation-cases.md`。

---

## 13. `SKILL.md` 建议正文草案

未来真正实现时，`SKILL.md` 可从以下内容开始：

```markdown
# MoSo Inspiration Developer

Use this skill when the user shares a messy, fragile, unfinished, dream-like, visual, fictional, product, copywriting, or emotional idea and wants it preserved, developed, fermented, visualized, written, critiqued, or evolved without premature summarization.

## Core stance

Treat the user's input as inspiration, not as a task brief.

Do not summarize too early. Preserve strange phrases, rough wording, contradictions, emotional texture, and unfinished images. Help the user see possible directions without deciding what the idea must become.

## Default workflow

1. Listen for the raw spark.
2. Identify must-preserve phrases.
3. Create an Inspiration Bubble.
4. Match 2-5 catalyst patterns.
5. Ferment through at least 3 distinct probes.
6. Generate visual or writing output only when requested.
7. Run Critic Diff before responding.
8. Return a short, gentle, user-facing response.

## Default response

Use this shape unless the user asks for JSON:

我听见的火种：
...

它深处可能藏着：
...

它可以长出的几条路：
1. ...
2. ...
3. ...

下一步只需要回答一个问题：
...

## Read references as needed

- For the full workflow, read `references/workflow.md`.
- For output contracts, read `references/schemas.md`.
- For catalyst patterns, read `references/pattern-library.md`.
- For critic checks, read `references/critic-rules.md`.
- For psychological probe requests, read `references/psychological-probe.md`.
- For visual outputs, read `references/visual-catalyst.md`.
- For fiction, copywriting, or long-form writing, read `references/writing-bloom.md`.
- For validation, read `references/evaluation-cases.md`.

## Hard rules

- Never replace the user's strange phrase with a generic concept.
- Never present inference as fact.
- Never diagnose the user.
- Never turn one answer into a stable personality profile.
- Never auto-evolve the skill without user approval.
- Never output a huge report by default.
- Ask at most one main follow-up question.
```

---

## 14. 质量标准

### 14.1 保真指标

- 是否保留 `must_preserve_phrases`
- 是否保留 `core_spark`
- 是否区分用户原意和 AI 推测
- 是否避免风格污染
- 是否没有把灵感过早定型

### 14.2 启发指标

- 是否生成至少 3 条差异化方向
- 是否匹配启发结构
- 是否提出具体、轻量、有效的问题
- 用户是否愿意继续发酵

### 14.3 输出指标

- 图像 Prompt 是否具体、可执行、有审美边界
- 小说片段是否有具体动作、潜台词和场景压力
- 文案是否有钩子、平台适配和反 AI 味
- 产品方向是否仍保留原始火种，而不是变成普通需求文档

### 14.4 进化指标

- 用户是否采纳 Evolution Patch
- 用户是否连续使用心理探针
- 用户是否认为问题越来越贴近自己
- 用户是否减少重复说明偏好
- 所有偏好更新是否可解释、可拒绝、可回滚

---

## 15. 失败用例

正式实现时，`references/evaluation-cases.md` 至少应包含以下失败测试：

1. 把梦境总结成励志鸡汤。
2. 把怪异原话改写成标准产品术语。
3. 把用户的“可能”写成事实。
4. 用“多角度探索、赋能、闭环”等空话替代具体内容。
5. 只给一个方向，过早定型为小说/产品/文案。
6. 心理探针输出人格诊断。
7. 图像 prompt 只有风格词，没有核心火种。
8. 小说片段全是解释，没有动作和潜台词。
9. 文案油腻、空泛、平台错位。
10. 一次反馈就修改长期用户画像。
11. 输出太长，让用户感到被压迫。
12. Critic 没有发现核心火种丢失。

---

## 16. MVP 验收标准

v0.2 的真正 Skill 文件包完成后，必须做到：

1. 输入一段混乱灵感，输出灵感气泡。
2. 输出至少 3 条不同探针分支。
3. Critic 能发现至少 3 类坏输出。
4. 视觉催化能输出可用于图片生成工具的 Prompt。
5. Writing Bloom 能输出小说片段和文案。
6. 心理探针能生成温和问题，并更新结构化记录。
7. Evolution Engine 能根据反馈生成 Patch Proposal。
8. 所有核心输出符合结构化契约。
9. `SKILL.md` 不超过 500 行，并通过 progressive disclosure 引导读取 references。
10. 不创建多余说明文件，不把 PRD 原样塞进 `SKILL.md`。

---

## 17. 下一步建议

下一步不是直接写代码，而是把本文档拆成真正的 Skill 文件包：

1. 生成 `moso-inspiration-developer/SKILL.md`。
2. 把细节拆入 `references/`。
3. 把结构化契约整理到 `references/schemas.md`。
4. 写 4 个正向示例和 12 个失败用例。
5. 用真实输入跑一轮验证，修正触发条件、输出长度和 Critic 规则。

MoSo Skill Kit 的本质不是提示词集合，而是一套灵感处理协议。

它的核心闭环是：

> 原始火花 -> 灵感气泡 -> 启发结构 -> 多探针发酵 -> 视觉/文字生花 -> Critic 审查 -> 用户反馈 -> Skill 进化

最终目标：

> 让智能体像一个懂得克制的显影师，而不是一个急着总结的文案机器。
