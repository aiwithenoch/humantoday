# HumanToday

> Make AI-assisted writing sound like a person again.

AI can give you a clean draft in seconds. It can also give you the same draft it gives everyone else: polished, padded, and strangely confident.

HumanToday is a writing skill and plugin that cuts the machine-shaped habits while keeping the parts readers remember: your point of view, your vocabulary, your jokes, your uncertainty, and your fingerprints.

**Give it the draft. Get back your voice.**

## The goal loop

Every edit has a finish line:

1. Define what the reader should get from the draft and what makes the writer sound like themselves.
2. Make the smallest useful revision.
3. Check the result against [`eval.md`](skills/humantoday/eval.md).
4. Fix failed checks and run the evaluation again.
5. Return the finished draft only when the applicable checks pass, with a short `What changed` note.

HumanToday runs up to three refinement passes when needed. If a safe edit still cannot satisfy a check, it says so instead of quietly shipping a worse draft.

## What HumanToday does

HumanToday has three useful modes:

- **Edit:** sharpen a draft with the minimum effective edit. You get the full revision and a short `What changed` note.
- **Detect:** find named AI-writing patterns without rewriting the draft or pretending to know who wrote it.
- **Generate:** create intentionally terrible AI copy when you need a before-and-after example or a little satire.

It does not turn every sentence into the same glossy, lifeless “professional” voice. A blunt sentence can stay blunt. A weird aside can stay weird. A real detail beats a perfect transition every time.

## Install

Paste this into ChatGPT, Codex, Claude Code, or another compatible coding agent:

```text
Install the /humantoday skill globally from https://github.com/aiwithenoch/humantoday. For every edit, run the HumanToday goal loop: define the goal, revise, check eval.md, fix failures, and repeat until the applicable checks pass. Then return the full draft and What changed.
```

Or install it with the skills CLI:

```sh
npx skills add aiwithenoch/humantoday --skill humantoday --global --yes
```

## Use it

### Edit a draft

```text
/humantoday

I built the thing and it works but the update sounds like a robot wrote it...
```

HumanToday returns the complete edited draft and explains the meaningful changes. It keeps your claims, tone, and useful rough edges intact.

### Detect the pattern, keep the draft

```text
/humantoday is this AI-sounding?

Your draft goes here.
```

HumanToday names the patterns it finds, quotes the relevant lines, and suggests a short fix. It does not rewrite, score, or claim to detect AI authorship.

### Make the worst version on purpose

```text
Draft the most AI-sounding product launch post possible about a calendar app.
```

Useful for satire, training examples, and seeing exactly what you never want to publish.

## The fingerprints it removes

HumanToday looks for more than 20 common habits, including:

- “It’s not X. It’s Y.” contrasts that announce the point instead of making it.
- “Here’s the thing” and “Let me be clear” throat-clearing.
- “What nobody tells you” fake-insight setups.
- Colon reveals such as “The best part: it learns.”
- Vague importance claims, padded verbs, and unnamed “experts.”
- Synonym cycling: agent, assistant, tool, platform, solution, repeat.
- Dramatic fragments, robotic rhythm, and mic-drop endings.
- Decorative formatting that tries to sound energetic instead of being clear.

The skill also checks the basics: active verbs, concrete details, readable sentences, and a structure that serves the point.

## The voice it protects

- Specific facts, names, numbers, and mechanisms.
- Humor, profanity, uncertainty, and personal asides when they belong.
- Distinctive vocabulary and cadence.
- Strong sentences that do not need “improving.”
- The writer's actual meaning, without invented evidence or opinions.

## What's inside

- [`skills/humantoday/SKILL.md`](skills/humantoday/SKILL.md) contains the editing and detection workflow.
- [`skills/humantoday/eval.md`](skills/humantoday/eval.md) contains the self-checks used after an edit.
- [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json) contains the plugin metadata.
- [`scripts/build_plugin.py`](scripts/build_plugin.py) builds and validates the distributable archive.

Build the plugin locally:

```sh
python scripts/build_plugin.py --check
```

## Origin

HumanToday is an independent, rebranded fork of [Peter Yang's No AI Slop](https://github.com/petergyang/no-ai-slop), released under the original MIT license. The editing principles remain credited to the original project; the package name, command, metadata, docs, and artwork in this repository are maintained for HumanToday.

## License

MIT. See [`LICENSE`](LICENSE).
