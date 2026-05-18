# Data Sources Guide

## Data Source Types

### 1. User Input

- Priority: Highest
- Credibility: High as project intent and original argument source
- Includes: `user_input_template.md`
- Citation: mark as `USER-xxx` in research notes

### 2. Local PDF Originals

- Priority: High
- Credibility: Medium to high, depending on speaker and material type
- Includes: `references/papers/`
- Citation: repository-relative PDF path, author/title from filename, page number when available

### 3. PDF Visual Extraction Notes

- Priority: Highest for slide-derived content
- Credibility: Medium to high; verify against PDF or page images when precise wording matters
- Includes: `references/paper-visual/extracted/`, `references/paper-visual/INDEX.md`, `references/paper-visual/manifest.json`, `references/paper-visual/images/`
- Citation: repository-relative extracted Markdown path, plus original PDF when needed

### 4. Web Archive

- Priority: High
- Credibility: depends on original source; use archived Markdown as local evidence and original URL as external citation
- Includes: `references/web/`
- Citation: article title, original URL, and repository-relative archived Markdown path

### 5. GitHub Project Materials

- Priority: High for MindFlow and Pomasa design references
- Credibility: High as project self-description
- Approved URLs:
  - MindFlow: `https://github.com/neil-wang-global/MindFlow`
  - Pomasa: `https://github.com/eXtremeProgramming-cn/pomasa`
- Citation: GitHub URL, not machine-local absolute paths

### 6. External Engineering References

- Priority: Medium to high
- Credibility: depends on publisher and author
- Includes: Anthropic, OpenAI, Martin Fowler, LangChain, Inngest, HumanLayer, and other archived references already stored under `references/web/`
- Citation: title, publisher, original URL, archived Markdown path

## Recording Format

Each source record should include:

- ID: `SRC-xxx` or `USER-xxx`
- Title
- Source type
- Source URL or repository-relative path
- Collection or archive location
- Core content summary
- Usable quote or paraphrase
- Credibility assessment
- Notes on how the source can support the speech

## Citation Principles

- Do not use untraceable claims such as “industry consensus” unless the claim is clearly framed as the speaker's judgment.
- Search summaries can locate sources, but cannot serve as final evidence.
- Prefer local archived materials already in this repository.
- Use repository-relative paths for local evidence.
- Use GitHub URLs for MindFlow and Pomasa.
- User original ideas should be marked as user input, not external evidence.
- If evidence is weak, downgrade the claim rather than forcing a citation.
