# Repository guidance

## Project

Hyperfocus is an instruction-only agent skill for helping users start and make progress on studying, development, writing, and other chosen tasks. The deliverable is Markdown instructions and YAML metadata; there is no application, build process, dependency manifest, or automated test suite.

## Files

- `SKILL.md`: authoritative skill definition, including YAML front matter and the interaction workflow.
- `agents/openai.yaml`: display name, short description, and default invocation prompt.
- `README.md`: English installation and usage documentation.
- `README.ja.md`: Japanese documentation with the same scope and meaning as the English README.
- `LICENSE`: MIT license terms and copyright notice.
- `AGENTS.md`: instructions for maintaining this repository, separate from the skill's instructions for focus sessions.

Read the relevant files before making changes. Editing this repository does not itself require running a Hyperfocus session.

## Editing conventions

- Respond to the maintainer in Japanese. Keep `SKILL.md`, `agents/openai.yaml`, and `README.md` in English, and `README.ja.md` in Japanese. The skill itself must respond in its user's preferred language.
- Preserve `name: hyperfocus` and the `$hyperfocus` invocation unless a rename is requested. Keep metadata and examples consistent with the skill definition.
- Update both READMEs when changing installation, usage, scope, or documented behavior. Preserve conditions and limitations across translations.
- Keep the repository instruction-only unless executable tooling is requested. Prefer a focused edit over extra infrastructure or dependencies.
- Keep the full workflow and its rationale self-contained in `SKILL.md`. Do not introduce separate reference files unless explicitly requested.
- Preserve unrelated user changes. Do not create commits, rewrite history, or publish changes unless requested.

## Behavioral constraints

When editing the skill or describing its behavior:

- Help the user do their chosen task through a concrete first step, short attempts, and feedback based on observed results. Routine task execution on their behalf is outside this skill's purpose.
- Preserve a session goal, a way to check progress, and a stopping point. About 10 minutes is only a provisional trial when no time is specified.
- Respect the user's choice to pause, stop, or switch activities. Do not treat missed meals, lost sleep, or difficulty stopping as success.
- Do not equate hyperfocus with flow, infer a diagnosis or brain state, or promise a particular mental state or scientifically validated outcome.
- Do not promise timed notifications without a working mechanism. Do not infer progress from silence or elapsed time.
- Saving personal records and changing notification settings require the user's authorization; invoking the skill alone is insufficient.

## Validation

For documentation changes, review the diff, check relative links, and compare both READMEs for matching instructions and limitations. Check shell examples for correct paths and quoting without changing the user's installed skills.

If YAML is changed, parse both the `SKILL.md` front matter and `agents/openai.yaml` with an available YAML parser. Verify that the skill name and default prompt still agree. There is no repository-specific build or test command; do not claim runtime behavior was tested from a text or syntax check alone.

For changes to the interaction workflow, check representative prompts covering an unclear task, a concrete study or development task, a language preference, and a request to stop. State whether this was a review of instructions or an actual session test.

## Version control

This checkout uses Jujutsu with a colocated Git repository. Use `jj status`, `jj diff`, and a bounded `jj log` to inspect existing work and the final change. No Git staging step is needed for ordinary file edits. If working in a Git-only clone, use its existing Git workflow instead.

