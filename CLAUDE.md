# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains a speech manuscript about knowledge-engineering-driven AI practice, plus the research notes, source inventory, agent prompts, methodology notes, and archived PDF references used to produce it.

## Commands

This is a documentation/research repository. There is no application build or test suite.

Useful commands:

```bash
git status --short --branch
git diff --check
npm run prepare
```

Commit hooks are managed by lefthook and commitlint:

```bash
npx lefthook install --force
./node_modules/.bin/commitlint --edit <commit-message-file>
```

Commit messages must use conventional commits with a lowercase scope and non-empty body, for example:

```text
docs(readme): 更新项目说明

Describe the speech manuscript and reference material layout.
```

## Repository Structure

- `_output/final-speech.md` is the final speech manuscript.
- `agents/` contains role prompts for the research and writing workflow: orchestration, source collection, synthesis, citation verification, and speech writing.
- `workspace/research/` contains intermediate research artifacts such as source inventory, raw notes, synthesis, and citation verification.
- `references/methodology/` contains methodology notes and templates that shape the research workflow.
- `references/papers/` archives the local PDF reference materials used by the project.
- `user_input_template.md` captures the original task framing and source list.

## External Reference Projects

Do not refer to local absolute paths for MindFlow or Pomasa. Use their GitHub repositories instead:

- MindFlow: `https://github.com/neil-wang-global/MindFlow`
- Pomasa: `https://github.com/eXtremeProgramming-cn/pomasa`

For copied PDF materials, use relative paths under `references/papers/`.

## Reference Handling

When updating research notes or the speech manuscript, keep source references portable:

- Use relative paths for files stored in this repository, such as `references/papers/CLI_for_AI_Agents.pdf`.
- Use GitHub URLs for MindFlow and Pomasa documents instead of `/Users/...` paths.
- Avoid adding machine-local absolute paths to committed files.
