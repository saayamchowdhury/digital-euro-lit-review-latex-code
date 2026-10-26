# Understanding the Digital Euro: A Literature Review

This repository contains the LaTeX source files for the literature review on the digital euro and is a part of my assignment submission.

## File Structure

```
.
├── !main.tex
├── abstract-body.tex
└── references.bib
```

## Files

### `!main.tex`

The main LaTeX document. It sets up the document structure and formatting, and includes the abstract and body content.

### `abstract-body.tex`

Contains the abstract and main text of the literature review, including the introduction, discussion, critical evaluation, and conclusion.

### `references.bib`

Contains the bibliographic entries used to generate the reference list.

## Compilation

The document is built with **XeLaTeX** and **Biber**. `!main.tex` sets `% !TEX program = xelatex`, and the bibliography uses `biblatex-chicago` (Chicago author-date) with `backend=biber`.

### Requirements

- A TeX distribution with XeLaTeX and Biber (e.g. TeX Live, MiKTeX)
- The `biblatex-chicago` package, plus `csquotes`, `titlesec`, `fancyhdr`, `authblk`, `abstract`, `microtype` and `lmodern`
- `abstract-body.tex` and `references.bib` in the same directory as `!main.tex`

### Build sequence

```bash
xelatex !main
biber !main
xelatex !main
xelatex !main
```

The first run generates the citation data, Biber resolves it against `references.bib`, and the last two runs resolve the citations and cross-references. The output is `!main.pdf`.

### Notes

- `abstract-body.tex` is pulled in by `\input{abstract-body}` inside the custom `\maketitle` in `!main.tex`. It is not compiled on its own.
- If you use an editor like TeXstudio, Overleaf or VS Code (LaTeX Workshop), set the engine to XeLaTeX and the bibliography tool to Biber.
- If citations show as `(?)` or the reference list is empty, Biber did not run or failed. Check `!main.blg` for errors, then rerun the full sequence.
