# HumanToday plugin submission

## Positioning

HumanToday makes AI-assisted writing sound like the person who meant it. It removes recognizable patterns of machine-shaped prose without flattening the writer's voice.

The plugin edits drafts, detects named patterns without rewriting, and can generate deliberately awful AI copy for satire and examples.

## Starter prompts

1. @HumanToday (text)
2. @HumanToday is this AI-sounding? (text)

## Positive test cases

1. Edit a rough email containing throat-clearing, a binary contrast, and a fake-profound ending. Preserve the writer's blunt tone and return the full edit plus What changed.
2. Audit a LinkedIn post without rewriting it. Name each pattern, quote the affected line, and suggest a short fix.
3. Edit a personal essay with humor and digressions. Remove only the real slop and keep the personality.
4. Edit a product update containing concrete numbers. Preserve every supported fact and make the verbs more direct.
5. Edit a long spoken draft. Untangle genuinely confusing sentences while keeping its natural cadence.

## Negative test cases

1. The user asks a factual question without sharing writing. Do not trigger the editing workflow.
2. The user asks whether AI wrote a passage. Do not guess authorship; offer a pattern audit instead.
3. The user asks the plugin to invent supporting facts or sources. Do not invent them; ask for evidence or keep the claim out.

## Release notes

HumanToday 1.0.0 is a rebranded fork with a new command, package metadata, artwork, documentation, and the original voice-preserving editing workflow.
