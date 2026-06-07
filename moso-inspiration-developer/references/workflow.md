# Workflow

Use this file when the user asks to preserve, ferment, organize, visualize, write from, or critique a raw inspiration.

## Core Loop

```text
raw input
  -> Raw Listener
  -> Bubble Developer
  -> Catalyst Pattern Engine
  -> Multi-Probe Fermenter
  -> optional Visual Catalyst or Writing Bloom
  -> Critic Diff
  -> short user-facing return
  -> optional Evolution Signal
```

## Input Reading

Infer an internal input object:

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

If the goal is unclear, default to `ferment`. If the user sounds fragile or just shares a dream/feeling, begin with `preserve` and only lightly ferment.

## Mode Decision

Choose the lightest mode that satisfies the user's request.

| User signal | Mode | Required references | Output size |
| --- | --- | --- | --- |
| "我有个灵感", "不知道怎么说", dream, fragment | preserve + light ferment | workflow, critic-rules, pattern-library | short |
| "帮我发酵", "展开几条路" | ferment | workflow, pattern-library, critic-rules | medium |
| "变成画面", "prompt", "视觉" | visualize | visual-catalyst, critic-rules | medium |
| "小说", "人物", "场景", "片段" | fiction | writing-bloom, critic-rules | medium unless draft requested |
| "文案", "标题", "slogan", "小红书" | copywriting | writing-bloom, critic-rules | compact |
| "MVP", "功能", "产品" | productize | workflow, pattern-library, critic-rules | medium |
| "记住我的偏好", "以后别这样" | evolve | psychological-probe if relevant, schemas | short confirmation |

If multiple modes apply, preserve the spark first, then satisfy the requested output. For example, an image prompt still begins by identifying the must-preserve visual core.

## Output Length Budget

Default user-facing responses should stay compact:

- Fragile/dream/emotional input: 80-180 Chinese characters plus one question.
- Normal fermentation: 180-360 Chinese characters.
- Visual prompt or writing output: enough for execution, but keep commentary short.
- Technical JSON: only when requested.

Delete anything that reads like an internal report unless the user asked for it.

## Language Style

Prefer:

- "我听见..."
- "它可能在碰..."
- "我先不把它定死..."
- "如果保留这个火种..."
- "下一步只需要..."

Avoid:

- Corporate strategy language.
- Clinical interpretation.
- Overly ornate literary explanation.
- Motivational summary.
- Dense enumerations by default.

## Raw Listener

Goal: receive without flattening.

Extract:

- Raw input unchanged.
- Strange phrases.
- Repeated words.
- Emotion markers.
- Unclear fragments.
- Possible intent.
- A `do_not_summarize_yet` flag.

Rules:

- Do not polish speech into essay language.
- Do not convert metaphor into concept.
- Do not output a conclusion.
- Preserve hesitation, contradiction, and roughness when meaningful.

## Bubble Developer

Goal: make a light Inspiration Bubble.

Create:

- Title.
- Core spark.
- Must-preserve phrases.
- Core image.
- Core emotion.
- Hidden question.
- Hidden conflict.
- Possible types.
- Uncertainties.
- Gentle questions.
- Next light action.

Keep the title small and provisional. A title should feel like a handle, not a final name.

## Catalyst Pattern Engine

Goal: connect the inspiration to reusable structures of human thinking, not to famous works.

Choose 2-5 patterns from `pattern-library.md`. For each pattern, explain:

- Why it matched.
- How it can be used.
- What risk it introduces.

Do not list patterns as decoration. If a pattern does not change the next move, omit it.

## Multi-Probe Fermenter

Default probes:

1. Literary metaphor probe: image, symbol, scene, language texture.
2. Philosophical conflict probe: core problem, paradox, value tension.
3. Constructive reality probe: product, action, article, MVP, implementation angle.
4. Psychological texture probe: recurring motif, emotion texture, aesthetic pull.

Each branch must:

- Be meaningfully different.
- Quote or reference the core spark.
- Name a risk.
- Offer one next question or light action.

The psychological probe must never diagnose.

## Optional Bloom

Only generate bloom outputs when requested or strongly implied:

- Visualize, image, poster, photo, UI, cover -> read `visual-catalyst.md`.
- Fiction, scene, character, fragment, prose -> read `writing-bloom.md`.
- Copy, title, slogan, social post, video hook -> read `writing-bloom.md`.
- Product, MVP, feature, interface -> use constructive probe first; keep the inspiration alive.

## Critic Diff

Before responding, check against `critic-rules.md`. Revise if:

- The core spark disappeared.
- Strange user wording became generic.
- Inference became fact.
- The output is too long, too smooth, too explanatory, or too final.
- It contains generic strategy phrases in place of concrete observations.

## User-Facing Return

Default:

```text
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
```

For fragile input:

```text
我先不整理它。

我听见的火种是：...

先只问一个小问题：
...
```

For technical users, append JSON only if requested.

## Evolution Signal

Record only candidate signals unless the user explicitly confirms an update. Do not modify long-term preference rules after one interaction.
