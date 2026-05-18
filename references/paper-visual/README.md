# PDF Visual Semantic Archive

This directory stores visual preprocessing outputs for PDF references used by the speech manuscript and research workflow.

## Layout

- `images/<pdf-slug>/page-001.jpg` stores rendered page images from each source PDF.
- `extracted/<pdf-slug>.md` stores page-by-page visual information extraction from the rendered pages.
- `legacy-semantic-summary/<pdf-slug>.md` stores the earlier summary-style notes and is not the target extraction artifact.
- `manifest.json` maps each source PDF to its rendered image directory and extracted Markdown file.

## Processing rule

Extracted Markdown should be based on visual reading of the rendered pages. For every page, transcribe the visible information into Markdown: titles, headings, paragraphs, bullet lists, tables, diagrams, labels, numbers, examples, conclusions, and visible speaker notes. Do not turn the PDF into a short summary; preserve page-level information as completely as practical. Direct text extraction may be used only as a secondary aid, not as the source of record.
