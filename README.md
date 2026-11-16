# Hyperfocus

[日本語](README.ja.md)

Hyperfocus is an agent skill that helps you get started on studying, development, writing, or another task you want to work on. It turns the task into a small first attempt, helps you check the result, and adjusts the next step to what is getting in your way.

The skill responds in your preferred language, or the language of the conversation when you have not specified one.

## What a session looks like

1. Choose a small outcome, a way to check it, and a stopping point.
2. Try one concrete action: solve part of a problem, run a small example, or draft a sentence.
3. Review what happened and get a hint, correction, or next step suited to the result.
4. Explore a related question when it helps the task, or continue independently when you can check your own work.
5. Stop at the agreed point and leave a clear first step for resuming.

If you have not chosen a duration, the skill suggests a trial of about 10 minutes. This is a starting point to adjust, not a required schedule. Timed reminders depend on an actual timer or notification mechanism being set up.

## Install for Codex

This repository contains instructions and metadata; there is no build step or application to run. You need Codex with local skill support to use the installation below.

On macOS or Linux, download or clone this repository, then run the following **from its root directory**. The destination `~/.agents/skills/hyperfocus` must not already exist.

```sh
mkdir -p "$HOME/.agents/skills"
ln -s "$PWD" "$HOME/.agents/skills/hyperfocus"
```

This links the checkout into Codex's user skill directory. Keep the checkout at that location while using the link. Codex supports symlinked skill directories; if the skill does not appear, restart Codex. See the [official skill documentation](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills).

## Usage

Mention `$hyperfocus` in a Codex prompt and describe the work you want to do. Include your available time or current obstacle if you already know them.

**Studying**

```text
$hyperfocus I have 20 minutes to study recursion, but I get lost when tracing
function calls. Help me start with one small example.
```

**Development**

```text
$hyperfocus I want to fix a failing test, but I keep putting it off.
Help me choose the first thing to inspect and check my progress.
```

**Writing**

```text
$hyperfocus I need to write the introduction to an article and cannot start.
Help me put the main point into one sentence. Respond in Japanese.
```

You do not need a complete plan. If the task is unclear, the skill begins by asking what you would like to work on. Feedback follows your answers, output, or drafts; it does not assume that time spent means progress made.

## Scope and limits

The skill supports your own attempts and decisions. It is not intended for routine task execution on your behalf or medical diagnosis. It does not promise hyperfocus or flow, and it does not treat those terms as interchangeable.

Stopping, fatigue, and the ease of switching activities matter alongside task results. The workflow respects requests to stop and does not encourage sacrificing sleep or meals. Invoking it alone does not authorize saving personal records or changing notification settings.

## Repository contents

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Skill definition and interaction instructions. |
| [agents/openai.yaml](agents/openai.yaml) | Display metadata and the default invocation prompt. |
| [AGENTS.md](AGENTS.md) | Repository maintenance guidance for coding agents. |
| [README.md](README.md) / [README.ja.md](README.ja.md) | English and Japanese installation and usage guides. |

The complete workflow and its design rationale are contained in `SKILL.md`; no separate reference files are required. The skill as a whole should not be described as scientifically validated.

## Maintenance

Use `SKILL.md` as the source of truth for behavior, keep `agents/openai.yaml` consistent with it, and update both READMEs when documented behavior changes. Review Markdown links, YAML syntax when edited, and the meaning of both language versions. There is currently no automated test suite or build command. See [AGENTS.md](AGENTS.md) for maintenance and validation guidance.

## License

Licensed under the [MIT License](LICENSE). Copyright (c) 2026 101ta28.
