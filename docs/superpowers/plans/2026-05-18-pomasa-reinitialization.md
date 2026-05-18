# Pomasa Reinitialization Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Clean old multi-agent runtime artifacts while preserving reference evidence, then regenerate a fresh Pomasa MAS in the repository root from `./user_input_template.md`.

**Architecture:** This is a filesystem reinitialization task, not an application change. The implementation first records current state, then removes only approved generated directories, then uses Pomasa's local prompt-driven generator instructions and required pattern documents to create the new MAS files.

**Tech Stack:** Markdown, shell commands, Claude Code file tools, Pomasa local generator at `~/.pomasa/pomasa/skills/pomasa/SKILL.md`, git validation.

---

## File Structure

- Preserve: `user_input_template.md` — authoritative task input for the new MAS.
- Preserve: `references/papers/` — original PDF evidence.
- Preserve: `references/paper-visual/` — extracted visual/page evidence.
- Preserve: `references/web/` — archived web evidence.
- Preserve: `references/methodology/` — existing methodology notes unless Pomasa generation deliberately updates methodology files.
- Preserve: `CLAUDE.md`, `README.md`, `package.json`, `package-lock.json`, `commitlint.config.cjs`, `lefthook.yml`, `.gitignore`.
- Remove before regeneration: `agents/`, `workspace/research/`, `_output/`, `wip/`.
- Read for generation: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/SKILL.md`.
- Read for generation: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/README.md`.
- Read for generation: required Pomasa patterns under `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/`:
  - `COR-01-prompt-defined-agent.md`
  - `COR-02-intelligent-runtime.md`
  - `STR-01-reference-data-configuration.md`
  - `STR-06-methodological-guidance.md`
  - `BHV-02-faithful-agent-instantiation.md`
  - `QUA-03-verifiable-data-lineage.md`
- Create or regenerate: `agents/` — new Agent blueprints.
- Create or regenerate: `workspace/` — new runtime workspace structure.
- Create or regenerate if selected by Pomasa: `_output/` — deliverable placeholder or output directory.
- Create or regenerate if needed: `wip/` — working notes.
- Modify if needed: `README.md` — usage instructions for the regenerated MAS.
- Modify if needed: `references/methodology/*.md` — methodology files derived from `user_input_template.md`.

---

### Task 1: Confirm clean baseline and preservation targets

**Files:**
- Inspect: repository root
- Inspect: `user_input_template.md`
- Inspect: `references/papers/`
- Inspect: `references/paper-visual/`
- Inspect: `references/web/`

- [ ] **Step 1: Confirm git status is clean except planning docs**

Run:

```bash
git status --short --branch
```

Expected: output shows branch status and only planned docs under `docs/` as untracked or modified. If other untracked or modified files appear, stop and ask the user before deleting or overwriting anything.

- [ ] **Step 2: Confirm the user input file exists**

Run:

```bash
test -f "user_input_template.md" && printf 'OK user_input_template.md\n'
```

Expected:

```text
OK user_input_template.md
```

- [ ] **Step 3: Confirm protected reference directories exist**

Run:

```bash
test -d "references/papers" && test -d "references/paper-visual" && test -d "references/web" && printf 'OK protected references\n'
```

Expected:

```text
OK protected references
```

- [ ] **Step 4: Snapshot the cleanup targets**

Run:

```bash
find agents workspace/research _output wip -maxdepth 2 -mindepth 1 -print 2>/dev/null | sort
```

Expected: a list of existing files to be removed, or no output for missing/empty directories. Review output before continuing.

---

### Task 2: Read Pomasa generator and required patterns

**Files:**
- Read: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/SKILL.md`
- Read: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/README.md`
- Read: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/COR-01-prompt-defined-agent.md`
- Read: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/COR-02-intelligent-runtime.md`
- Read: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/STR-01-reference-data-configuration.md`
- Read: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/STR-06-methodological-guidance.md`
- Read: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/BHV-02-faithful-agent-instantiation.md`
- Read: `/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/QUA-03-verifiable-data-lineage.md`

- [ ] **Step 1: Read the Pomasa generator instructions**

Use the Read tool on:

```text
/Users/weili.wang/.pomasa/pomasa/skills/pomasa/SKILL.md
```

Expected: the file describes the generator role, input handling, pattern selection, mandatory pattern reads, output structure, and delivery instructions.

- [ ] **Step 2: Read the Pomasa pattern catalog overview**

Use the Read tool on:

```text
/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/README.md
```

Expected: the file lists required, recommended, and optional Pomasa patterns.

- [ ] **Step 3: Read all required pattern documents**

Use the Read tool on each file:

```text
/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/COR-01-prompt-defined-agent.md
/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/COR-02-intelligent-runtime.md
/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/STR-01-reference-data-configuration.md
/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/STR-06-methodological-guidance.md
/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/BHV-02-faithful-agent-instantiation.md
/Users/weili.wang/.pomasa/pomasa/skills/pomasa/pattern-catalog/QUA-03-verifiable-data-lineage.md
```

Expected: after this step, the worker has the mandatory Pomasa constraints for agent blueprints, runtime assumptions, reference layout, methodology files, faithful subagent invocation, and data lineage.

---

### Task 3: Remove only approved old runtime artifacts

**Files:**
- Delete contents or directories: `agents/`
- Delete contents or directories: `workspace/research/`
- Delete contents or directories: `_output/`
- Delete contents or directories: `wip/`
- Preserve: `workspace/` if it contains non-`research` content not approved for removal

- [ ] **Step 1: Remove approved old artifacts**

Run:

```bash
rm -rf "agents" "workspace/research" "_output" "wip"
```

Expected: command succeeds with no output.

- [ ] **Step 2: Confirm protected directories still exist**

Run:

```bash
test -d "references/papers" && test -d "references/paper-visual" && test -d "references/web" && test -f "user_input_template.md" && printf 'OK protected files remain\n'
```

Expected:

```text
OK protected files remain
```

- [ ] **Step 3: Confirm old cleanup targets are gone**

Run:

```bash
for path in agents workspace/research _output wip; do if test -e "$path"; then printf 'STILL_EXISTS %s\n' "$path"; fi; done
```

Expected: no output. If output appears, inspect the path before continuing.

---

### Task 4: Generate the fresh Pomasa MAS structure

**Files:**
- Read: `user_input_template.md`
- Create: `agents/00.orchestrator.md`
- Create: `agents/01.source_collector.md` or equivalent first-stage agent blueprint
- Create: `agents/02.synthesis_analyst.md` or equivalent analysis agent blueprint
- Create: `agents/03.citation_verifier.md` or equivalent verification agent blueprint
- Create: `agents/04.speech_writer.md` or equivalent final writing agent blueprint
- Create or modify: `references/methodology/research-overview.md`
- Create or modify: `references/methodology/data-sources.md`
- Create or modify: `references/methodology/analysis-methods.md`
- Create or modify: `references/methodology/output-template.md`
- Create: `workspace/` runtime subdirectories needed by the generated pipeline
- Create if Pomasa selects export/output staging: `_output/`
- Create if useful: `wip/notes.md`
- Modify if needed: `README.md`

- [ ] **Step 1: Read the task input**

Use the Read tool on:

```text
/Users/weili.wang/workspace/knowledge-engineering-driven-ai-practice/user_input_template.md
```

Expected: the worker sees the project identifier `ai-work-system-speech-20260518`, Chinese output requirements, strict QA requirements, and final deliverables: one HTML presentation file and one Markdown speech manuscript.

- [ ] **Step 2: Select Pomasa patterns for this project**

Use these pattern choices unless the required pattern documents reveal a direct contradiction:

```text
Required: COR-01, COR-02, STR-01, STR-06, BHV-02, QUA-03
Recommended: STR-02, STR-03, STR-04, STR-05, BHV-01, BHV-04, BHV-05, QUA-01, QUA-02
Optional selected: BHV-03, because independent source extraction and verification tasks may run in parallel later
Optional skipped: STR-08 and STR-09 as DOCX/PDF export is explicitly out of scope; final output is Markdown plus HTML
Optional skipped: BHV-06 unless the user later provides custom search/fetch tools
```

Expected: this selection supports a staged research-writing pipeline with verifiable references and no DOCX/PDF export path.

- [ ] **Step 3: Generate agent blueprints**

Create `agents/` and write focused blueprints in Chinese. The exact agent count can be adjusted to fit Pomasa constraints, but the baseline pipeline should be:

```text
agents/00.orchestrator.md — coordinates the pipeline and invokes workers using BHV-02 faithful invocation wording.
agents/01.source_collector.md — inventories and extracts relevant evidence from preserved local references.
agents/02.synthesis_analyst.md — turns sources and user ideas into a structured argument and chapter plan.
agents/03.citation_verifier.md — checks claims against local references and records source lineage.
agents/04.speech_writer.md — produces the final Markdown speech manuscript and HTML presentation.
```

Required orchestrator invocation wording must follow this form for each worker:

```text
Please read `agents/XX.agent_name.md` and execute strictly according to that Blueprint, parameters: ...
```

Expected: every blueprint has clear role, inputs, outputs, allowed files, forbidden actions, completion criteria, and quality checks.

- [ ] **Step 4: Generate methodology files**

Update or create the methodology files under `references/methodology/` from `user_input_template.md`:

```text
references/methodology/research-overview.md — project topic, core questions, narrative constraints, final deliverables.
references/methodology/data-sources.md — preserved local PDFs, extracted visual notes, web archive, MindFlow and Pomasa GitHub URLs.
references/methodology/analysis-methods.md — concept lineage analysis, case synthesis, engineering pattern abstraction, speech narrative design, citation traceability.
references/methodology/output-template.md — exact final output requirements for Markdown speech manuscript and HTML presentation.
```

Expected: methodology files contain portable references only, with no machine-local MindFlow or Pomasa absolute paths.

- [ ] **Step 5: Generate runtime workspace directories**

Run:

```bash
mkdir -p "workspace/research" "workspace/drafts" "workspace/final" "_output" "wip"
```

Expected: command succeeds with no output.

- [ ] **Step 6: Add a concise new workflow note if needed**

If `README.md` no longer describes the regenerated MAS accurately, update only the relevant usage section. Include these facts:

```text
- Input: user_input_template.md
- Agent blueprints: agents/
- Runtime workspace: workspace/
- Final outputs: Markdown speech manuscript and HTML presentation
- Protected evidence: references/papers/, references/paper-visual/, references/web/
```

Expected: README remains concise and does not mention local absolute paths for MindFlow or Pomasa.

---

### Task 5: Validate regenerated structure and references

**Files:**
- Inspect: `agents/`
- Inspect: `workspace/`
- Inspect: `_output/`
- Inspect: `references/papers/`
- Inspect: `references/paper-visual/`
- Inspect: `references/web/`
- Inspect: changed files from git diff

- [ ] **Step 1: Confirm key generated directories exist**

Run:

```bash
test -d "agents" && test -d "workspace" && test -d "_output" && printf 'OK generated structure\n'
```

Expected:

```text
OK generated structure
```

- [ ] **Step 2: Confirm protected evidence directories still exist**

Run:

```bash
test -d "references/papers" && test -d "references/paper-visual" && test -d "references/web" && printf 'OK evidence preserved\n'
```

Expected:

```text
OK evidence preserved
```

- [ ] **Step 3: Check for forbidden local absolute references in committed content**

Run:

```bash
grep -R "/Users/" agents references/methodology README.md user_input_template.md 2>/dev/null || true
```

Expected: no output, except acceptable examples if already present in ignored or non-committed local-only files. If output appears in generated project files, replace machine-local paths with repository-relative paths or approved GitHub URLs.

- [ ] **Step 4: Run whitespace validation**

Run:

```bash
git diff --check
```

Expected: no output and exit code 0.

- [ ] **Step 5: Review git diff for scope**

Run:

```bash
git status --short --branch && git diff --stat
```

Expected: changes are limited to the spec/plan docs, deleted old runtime artifacts, regenerated MAS files, and any necessary README or methodology updates. Protected reference evidence directories are not deleted.

---

### Task 6: Report completion without committing implementation changes

**Files:**
- Inspect: git status

- [ ] **Step 1: Summarize changed files**

Run:

```bash
git status --short
```

Expected: status shows the changed and generated files. Do not commit unless the user explicitly asks.

- [ ] **Step 2: Report paths and validation evidence**

Report these items to the user:

```text
- New/updated MAS directories and files
- Protected reference directories confirmed preserved
- Validation command: git diff --check
- Any files that still need user review
```

Expected: final response does not claim final speech outputs exist unless the generated MAS has actually produced them.
