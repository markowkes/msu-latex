# MSU LaTeX Thesis and Dissertation Template

This repository provides a LaTeX template for Montana State University (MSU) theses and dissertations. The template is intended to help graduate students create a document that follows MSU formatting requirements while allowing them to focus on writing rather than formatting.

## Why Use LaTeX?

LaTeX is a document preparation system widely used in engineering, mathematics, physics, computer science, and many other technical fields.

Benefits include:

- Excellent handling of equations and mathematical notation
- Automatic numbering of chapters, figures, tables, and equations
- Automatic generation of table of contents, lists of figures, and lists of tables
- Easy bibliography and citation management
- Professional document appearance
- Version control through Git

Even if you have never used LaTeX before, this template provides a structured starting point.

---

## Quick Start

### Option 1: Use Overleaf (Recommended for Beginners)

Overleaf is an online LaTeX editor that requires no software installation.

1. Create an account at https://www.overleaf.com (Note some departments or colleges offer free Overleaf Premium accounts which have faster compile times!)
3. Download this repository as a ZIP file
4. Create a new Blank Overleaf project
5. Upload the ZIP contents
6. Open `main.tex`
7. Click **Recompile**

This is the easiest way to get started.

---

### Option 2: Clone the Repository

If you are familiar with Git:

```bash
git clone https://github.com/markowkes/msu-latex.git
cd msu-latex
```

Compile the document using your preferred LaTeX distribution.

Common choices:

- TeX Live (Linux)
- MacTeX (macOS)
- MiKTeX (Windows)

---

## Start Here

After successfully compiling the template, carefully read the generated PDF document (`main.pdf`).

The PDF is intentionally designed to serve as both a sample thesis/dissertation and a user guide. It demonstrates the structure and formatting of a complete document while providing examples of common LaTeX features used throughout graduate research documents.

The generated PDF contains examples of:

- Chapters and sections
- Equations and mathematical notation
- Figures and tables
- Cross references
- Citations and bibliographies
- Front matter
- Appendices
- Common formatting features

New users are strongly encouraged to:

1. Compile the template.
2. Read through `main.pdf`.
3. Identify examples similar to content they plan to include in their own document.
4. Locate the corresponding source files.
5. Replace the example content with their own material.

Most users learn the template much more quickly by examining the examples in `main.pdf` and comparing them with the source `.tex` files than by trying to learn LaTeX from scratch before beginning to write.

Whenever you are unsure how to create a particular element in your thesis or dissertation, the first place to look should be the generated PDF and the source code used to produce it.

---

## Template Options

Most document formatting options are controlled through the document class declaration near the top of `main.tex`:

```latex
\documentclass[dissertation,appendsingle]{MSUstyle}
```

The default settings produce a document that conforms to current MSU Electronic Thesis/Dissertation (ETD) requirements. Most students will not need to modify these options, but several common customizations are available.

### Thesis or Dissertation

The template defaults to a dissertation:

```latex
\documentclass[dissertation]{MSUstyle}
```

For a master's thesis, use:

```latex
\documentclass[thesis]{MSUstyle}
```

This adjusts the front matter to match MSU requirements for a master's thesis.

### Appendices

If your document contains a single appendix:

```latex
\documentclass[appendsingle]{MSUstyle}
```

If your document contains multiple appendices:

```latex
\documentclass[appendmultiple]{MSUstyle}
```

If your document does not contain any appendices, remove these options and comment out the appendix section near the end of `main.tex`.

### Draft Mode

When editing, you may wish to create shorter drafts that use less paper and compile more quickly.

Examples:

```latex
\documentclass[10pt,singlespaced,draft]{MSUstyle}
```

You may also specify a draft version number:

```latex
\draftver{1.0}
```

The draft option is intended for working documents and should normally be removed before your final submission.

### Numbered Sections

By default, some chapter and section titles may appear without numbering.

To force numbering of chapters and sections:

```latex
\documentclass[numberedsections]{MSUstyle}
```

### Figure and Table Numbering

By default, figure, table, and equation numbers reset within each chapter:

```text
Figure 3.2
Table 4.1
Equation 5.7
```

You can disable chapter-based numbering using:

```latex
\documentclass[nonumreset]{MSUstyle}
```

This is generally not recommended for theses and dissertations.

### Printing Options

The default document layout is:

```latex
\documentclass[oneside,openright]{MSUstyle}
```

This produces 1-inch margins suitable for electronic submission.

Other useful options include:

#### Bound or Printed Copies

```latex
\documentclass[oneside,openright,bigmargin]{MSUstyle}
```

Adds a larger left margin for binding.

#### Double-Sided Printing

```latex
\documentclass[twoside,openright]{MSUstyle}
```

Creates a double-sided document and inserts blank pages when necessary so that chapters begin on right-hand pages.

#### Double-Sided Printing with Binding Margins

```latex
\documentclass[twoside,openright,bigmargin]{MSUstyle}
```

Alternates larger inner margins for binding and produces the highest-quality printed copies.

### Accessibility Features

The template includes support for modern tagged PDF generation and PDF accessibility features.

In rare cases, a package or custom code may cause tagging errors during compilation. If this occurs, tagging can be temporarily disabled around the problematic content using:

```latex
\tagpdfparaOff

% problematic content

\tagpdfparaOn
```

Most users will not need to modify these settings.

### Personal Information and Document Metadata

The following fields near the top of `main.tex` should be updated before writing your document:

```latex
\name{Your Full Name}
\DocTitle{Your Thesis Title}
\degreetitle{Engineering}
\department{Mechanical and Industrial Engineering}
\committeechair{Advisor Name}
\graduationdate{May 2027}
\copyrightyear{2027}
```

These values automatically populate the title page, approval pages, PDF metadata, and other required document elements.

---

## Manuscript Option 

The repository includes an example manuscript-style chapter (manuscript_option.tex) that demonstrates how students wanting to include publication manuscripts in their thesis or dissertation should. Students planning to include published or publication-ready journal articles in their thesis/dissertation should review this example in both the source files and the generated PDF.

---

## Repository Structure

```text
.
├── main.tex                Main document
├── chapters/               Individual chapter files
├── figures/                Images and figures
├── bibliography/           References and BibTeX files
├── frontmatter/            Abstract, acknowledgements, etc.
└── ...
```

The exact file organization may evolve, but in general:

- `main.tex` controls the overall document.
- Chapters are written in separate files.
- Figures are stored separately from text.
- References are managed using BibTeX.

---

## Building the Document

A typical build sequence is:

```bash
pdflatex main
bibtex main
pdflatex main
pdflatex main
```

Many editors automate these steps.

---

## Recommended Workflow

Write each chapter in its own file and include it from `main.tex`.

Example:

```latex
\include{chapters/introduction}
\include{chapters/literature_review}
\include{chapters/methods}
\include{chapters/results}
\include{chapters/conclusions}
```

This keeps large documents organized and easier to edit.

---

## Managing References

References are typically stored in a BibTeX database:

```bibtex
@article{smith2024,
  author  = {Smith, John},
  title   = {Example Article},
  journal = {Journal of Examples},
  year    = {2024}
}
```

Then cite using:

```latex
\cite{smith2024}
```

LaTeX automatically handles numbering and formatting.

---

## Figures

Place figures in the `figures` directory and insert them using:

```latex
\begin{figure}[ht]
    \centering
    \includegraphics[width=0.8\textwidth]{figures/example.png}
    \caption{Example figure.}
    \label{fig:example}
\end{figure}
```

Reference figures using:

```latex
Figure~\ref{fig:example}
```

---

## Getting Help

Useful resources:

- Overleaf Documentation: https://www.overleaf.com/learn
- LaTeX Wikibook: https://en.wikibooks.org/wiki/LaTeX
- TeX Stack Exchange: https://tex.stackexchange.com

If you encounter template-specific issues, please open a GitHub issue.

---

## Contributing

Suggestions and improvements are welcome.

If you discover formatting issues, bugs, or have examples that would help future MSU graduate students, please submit an issue or pull request.

---

## Disclaimer

Students are ultimately responsible for ensuring that their thesis or dissertation meets all current Graduate School requirements. Always verify formatting requirements against the latest MSU Graduate School guidelines.
