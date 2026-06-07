# MoSo Inspiration Developer

MoSo Inspiration Developer is an agent skill for handling fragile, unfinished creative ideas without flattening them into premature summaries.

It helps an AI agent receive a raw spark, preserve the user's exact language, develop an Inspiration Bubble, explore multiple directions, generate visual or writing outputs when requested, and run a critic pass to catch generic AI language, over-inference, and loss of intent.

## What It Does

- Preserves strange phrases, contradictions, emotional texture, and unfinished images.
- Turns messy input into a structured Inspiration Bubble.
- Ferments an idea through literary, philosophical, constructive, and psychological-texture probes.
- Generates restrained visual prompts, fiction fragments, copywriting, and long-form writing directions.
- Runs Critic Diff to prevent over-summary, generic consulting language, diagnostic interpretation, and premature conclusions.
- Supports candidate preference signals without silently changing long-term user profiles.

## Core Philosophy

MoSo treats inspiration as something alive and unfinished.

It does not ask:

```text
How can this be summarized?
```

It asks:

```text
What must be preserved so this idea can keep growing?
```

The skill is designed to let large models use their full interpretive ability inside reliable engineering constraints: clear triggers, short default responses, explicit safety boundaries, structured internal contracts, and testable failure cases.

## Repository Structure

```text
docs/
  moso-skill-kit-spec.md
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

## Compatibility

This skill is written as:

- Codex-first
- OpenClaw-compatible in structure
- Hermes-adaptable with a thin manifest or index layer

The core package uses a `SKILL.md` file with YAML frontmatter and Markdown instructions, plus progressively loaded `references/` files.

The design specification lives in [`docs/moso-skill-kit-spec.md`](docs/moso-skill-kit-spec.md).

## Example

Input:

```text
我梦到一个电梯没有按钮，只有一排会呼吸的小灯。我知道它们在等我说话，但我说不出来。
```

Expected style:

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

## Validation

The skill currently validates with the Codex skill creator validator:

```text
Skill is valid!
```

It also includes forward test prompts and scoring rubrics in:

```text
moso-inspiration-developer/references/evaluation-cases.md
```

## License

No license has been selected yet.
