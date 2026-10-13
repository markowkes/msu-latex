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
