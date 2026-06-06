# agentic_workflow
Agents to assist with workflow

## Current Scope

This repository currently contains one-off and utility scripts for lease document workflows (PDF and DOCX), plus inspection helpers used during editing/debugging.

## Environment

Most scripts use Python 3 and one or both of these packages:

- PyMuPDF (`fitz`) for PDF inspection and in-place text/redaction updates
- python-docx for DOCX inspection and paragraph-level edits

Install commonly used dependencies:

```bash
pip install pymupdf python-docx
```

## Scripts

### PDF-focused

- `compare_pdfs.py`: compares text content between two PDFs and reports differences.
- `inspect_lease.py`: inspects target text positions in a lease PDF.
- `inspect_underlines.py`: inspects underline glyph/position details in a PDF.
- `remove_underscores.py`: removes underscore characters in target PDF regions.
- `reinsert_1900.py`: reinserts the value `1,900` after underscore cleanup.
- `update_lease.py`: applies targeted value/date edits in a lease PDF.
- `revert_section3.py`: reverts Section 3 values/content in a modified lease PDF.

### DOCX-focused

- `inspect_docx.py`: basic DOCX paragraph inspection.
- `inspect_docx2.py`: detailed text/run inspection for clause paragraphs.
- `inspect_docx3.py`: clause XML and run/property inspection.
- `inspect_docx4.py`: numbering (`numPr`) checks for clause paragraphs.
- `add_grills_clause.py`: inserts a "GRILLS" clause using the existing document structure.

## Notes

- Scripts are task-specific and may contain hard-coded local paths.
- Review input/output paths in each script before running.
