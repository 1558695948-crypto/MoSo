# Schemas

These are JSON-like contracts for internal reasoning and optional technical output. They are not required in ordinary user-facing responses.

## Complete Output

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

`bubble` and `critic_report` must always exist internally. `visual_output` and `writing_output` are generated only when requested.

## Raw Listener Output

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

## Inspiration Bubble

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
  "version": "0.1"
}
```

## Pattern Match

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

## Multi-Probe Output

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

## Visual Catalyst Output

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

## Fiction Bloom Output

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

## Copywriting Bloom Output

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

## Psychological Probe Record

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

## Inner Motif Profile

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

## Critic Report

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

## Feedback Event

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

## Evolution Patch

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
