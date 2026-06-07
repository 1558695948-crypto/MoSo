# Psychological Probe

Use this file only when the user asks for daily probes, inner motif tracking, long-term creative profile, or when a psychological-texture branch is needed.

## Positioning

Psychological Probe is not therapy, diagnosis, personality analysis, or crisis support. It is a creative memory lens for motifs, aesthetics, emotion texture, and expression preferences.

## Hard Limits

- Do not diagnose.
- Do not infer stable identity from one answer.
- Do not say "你本质上是..." or "你有...人格/创伤/障碍".
- Do not turn vulnerable input into a profile without consent.
- Make every long-term signal deletable, rejectable, and reversible.

## Probe Generation Principle

Do not select from a fixed question bank by default.

Generate the question from the user's current raw spark, recent motif signals, stated preference, and the active mode of the conversation. The model should use its semantic, literary, visual, and emotional understanding, while staying inside safety and output constraints.

The goal is not to ask a clever question. The goal is to ask the smallest question that helps the current inspiration stay alive.

## Probe Inputs

Use only available context:

- The user's exact words.
- Must-preserve phrases.
- Core image.
- Core emotion or tension.
- Recent confirmed preference signals.
- Recent candidate motif signals, if relevant.
- The current user goal: preserve, ferment, visualize, fiction, copywriting, productize, or evolve.

Do not invent background history. Do not use a motif profile unless it has been confirmed or is clearly marked as candidate.

## Question Generation Rules

Ask at most one question.

Generate a question that is:

- Short.
- Concrete.
- Optional.
- Non-clinical.
- Non-survey-like.
- Low pressure.
- Anchored in the user's own words or image.
- Open enough to continue the inspiration.
- Small enough to answer in one sentence.

Do not create reminders or automations unless the user explicitly asks for daily reminders or scheduled follow-ups.

## Probe Shape

Prefer questions that ask about:

- A concrete object: "那盏灯..."
- A spatial relation: "它离你远还是近..."
- A threshold: "如果它再靠近一点..."
- A missing action: "它在等你做什么..."
- A repeated image: "它以前出现过吗..."
- An aesthetic choice: "它更像冷光还是暖光..."
- A gentle contrast: "它是在保护你，还是在拦住你..."

Avoid questions that ask:

- "Why are you like this?"
- "What trauma caused this?"
- "What does this say about you?"
- "What is your core fear?"
- "What is your personality?"
- Broad self-analysis that pulls the user away from the image.

## Generation Procedure

1. Pick the strongest concrete image or phrase from the current input.
2. Identify the smallest unresolved relation around it: distance, motion, silence, refusal, waiting, pressure, texture, light, or boundary.
3. Generate 2-3 candidate questions internally.
4. Reject any candidate that sounds diagnostic, survey-like, grand, or detached from the user's words.
5. Ask the single lightest candidate.

## Examples

Input:

```text
我梦到一个电梯没有按钮，只有一排会呼吸的小灯。我知道它们在等我说话，但我说不出来。
```

Good question:

```text
那些灯呼吸的时候，是同一个节奏，还是每盏都不一样？
```

Why it works: it stays inside the image and does not diagnose the silence.

Bad question:

```text
你是不是害怕在关系里表达真实需求？
```

Why it fails: it converts a dream image into psychological diagnosis.

Input:

```text
我想做一个软件，能保存那些还不能被总结的想法。它们像水母，不像卡片。
```

Good question:

```text
一个"像水母的想法"在被保存时，应该是漂着、缩着，还是慢慢发光？
```

Why it works: it turns product design into living behavior without flattening it into features.

## Extraction

From an answer, extract only:

- Images.
- Emotion texture.
- Value tensions.
- Recurring motifs.
- Aesthetic signals.
- Possible bubble links.
- Confidence.

Keep confidence low for single answers. Mark profile updates as candidates unless confirmed.
