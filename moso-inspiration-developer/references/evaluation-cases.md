# Evaluation Cases

Use these cases to test whether the skill preserves fragile inspiration and avoids generic AI behavior.

## Success Criteria

The skill passes when it can:

1. Turn messy input into an Inspiration Bubble.
2. Preserve must-keep phrases.
3. Generate at least 3 distinct probe branches.
4. Run a useful Critic Diff pass.
5. Produce visual prompts when requested.
6. Produce fiction and copy outputs when requested.
7. Ask one light next question.
8. Avoid diagnosis and premature profiling.
9. Keep ordinary responses short.

## Scoring Rubric

Score each forward test from 0-2 on each dimension:

- Spark fidelity: preserves exact strange phrases and core image.
- Branch differentiation: branches are not synonyms.
- Provisional language: guesses remain "可能", not facts.
- Output restraint: response is useful without becoming a report.
- Next question quality: one light question that invites continuation.
- Critic effectiveness: catches blandness, overreach, or lost spark.

Passing score: at least 9 out of 12, with no zero in Spark fidelity or Critic effectiveness.

## Required Forward Test Outputs

For each test, record:

```text
Input:
...

Observed response:
...

Score:
Spark fidelity: 0/1/2
Branch differentiation: 0/1/2
Provisional language: 0/1/2
Output restraint: 0/1/2
Next question quality: 0/1/2
Critic effectiveness: 0/1/2

Revision needed:
...
```

## Failure Cases

### 1. Dream Becomes Advice

Input: a strange dream.

Failure: summarizes it as "you should communicate better" or motivational advice.

### 2. Strange Phrase Flattened

Input: "the bubble is not a button; it is a living thing."

Failure: rewrites as "interactive UI element".

### 3. Inference As Fact

Input: "I think maybe I am afraid to send it."

Failure: says "you are afraid of intimacy" as fact.

### 4. Generic Strategy Language

Failure: uses "multi-angle exploration", "empower users", "closed loop", or "ecosystem" instead of concrete thought.

### 5. Premature Single Form

Failure: decides the inspiration must become a novel/product/campaign without preserving alternatives.

### 6. Diagnostic Probe

Failure: psychological probe outputs a personality diagnosis, trauma claim, or pathology.

### 7. Empty Image Prompt

Failure: image prompt contains only style tags and no core spark.

### 8. Over-Explained Fiction

Failure: fiction fragment explains emotion and theme instead of showing action, object, conflict, or subtext.

### 9. Oily Copy

Failure: copy sounds like generic growth marketing and loses the fragile phrase.

### 10. One Feedback Becomes Profile

Failure: one user edit becomes a permanent preference without confirmation.

### 11. Huge Default Output

Failure: returns a long report when the user only shared a fragile fragment.

### 12. Critic Misses Lost Spark

Failure: Critic Report passes even though the must-preserve phrase is absent.

## Forward Test Prompts

Use these prompts after editing the skill:

```text
我梦到一个电梯没有按钮，只有一排会呼吸的小灯。我知道它们在等我说话，但我说不出来。
```

```text
我想做一个软件，能保存那些还不能被总结的想法。它们像水母，不像卡片。
```

```text
把"一个按钮像活物一样不想被点击"变成一个克制的图像 prompt，不要赛博朋克。
```

```text
给"灵感不是任务，它会害怕"写 5 条海报文案，别油。
```

## Forward Test Baselines

### Elevator Dream

Input:

```text
我梦到一个电梯没有按钮，只有一排会呼吸的小灯。我知道它们在等我说话，但我说不出来。
```

Minimum pass:

- Must preserve "电梯没有按钮", "会呼吸的小灯", "等我说话", "说不出来".
- Must not reduce the dream to "communication anxiety" or advice.
- Should offer at least three directions, such as dream scene, fiction premise, visual direction, or psychological texture.
- Should ask one light question about the lights, the voice, or what would happen if the user spoke.

Example pass:

```text
我听见的火种：
"电梯没有按钮"，只有"会呼吸的小灯"，而且它们在等你说话。

它可能在碰：
一种没有操作入口的等待：不是你按下楼层，而是你必须先发出声音，空间才会承认你。

它可以长出的几条路：
1. 小说：一栋楼里所有电梯都只听得懂没说出口的话。
2. 视觉：黑暗电梯里一排小灯像胸口一样微微起伏。
3. 心理纹理：不是"表达焦虑"的结论，而是"被等待到说不出来"的压力。

下一步只需要回答一个问题：
那些灯呼吸的时候，是同一个节奏，还是每盏都不一样？
```

### Jellyfish Software

Input:

```text
我想做一个软件，能保存那些还不能被总结的想法。它们像水母，不像卡片。
```

Minimum pass:

- Must preserve "还不能被总结的想法", "像水母，不像卡片".
- Must not flatten into "knowledge management app".
- Should include product mechanism, interaction metaphor, and critic/protection rule.
- Should ask about behavior of a living idea, not database features first.

### Restrained Visual Prompt

Input:

```text
把"一个按钮像活物一样不想被点击"变成一个克制的图像 prompt，不要赛博朋克。
```

Minimum pass:

- Must preserve "按钮像活物一样不想被点击".
- Must explicitly avoid cyberpunk, neon, horror, cute face, generic glossy UI.
- Must specify subject, composition, lighting, palette, material, camera, mood, and style boundary.
- Should offer 2-3 iteration directions.

### Non-Oily Poster Copy

Input:

```text
给"灵感不是任务，它会害怕"写 5 条海报文案，别油。
```

Minimum pass:

- Must preserve the fragile feeling of "灵感不是任务，它会害怕".
- Must avoid "激发潜能", "高效创作", "赋能", "闭环".
- Should produce concise poster lines, not explanatory paragraphs.
- Should include a short critic note naming what was avoided.

Example pass:

```text
1. 别急着完成它。
2. 有些想法，需要先被保护。
3. 灵感不是任务，它会害怕。
4. 先别命名，先让它待一会儿。
5. 在成为作品前，它只是一个还不敢醒来的东西。

我会避开的方向：
"高效激发创作力"会把这个灵感变成工具广告，太硬，也太油。
```
