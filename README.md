# Plaksha Resume Template

A single-file XeLaTeX resume template forked from [`jalan-subham/plaksha-resume-template`](https://github.com/jalan-subham/plaksha-resume-template).

The editable resume source is:

```text
src/resume.tex
```

## Structure

```text
.
├── README.md
├── fonts/
├── images/
└── src/
    └── resume.tex
```

## Edit The Resume

Open `src/resume.tex` and replace the placeholder content in:

- heading and contact links
- education
- work experience
- projects
- positions of responsibility
- skills
- achievements

The template includes the Plaksha logo from `images/plaksha.png`. Remove the `tikzpicture` logo block in `src/resume.tex` if you do not want it.

## Use On Overleaf

1. Create a new Overleaf project.
2. Import this repository from GitHub or upload it as a ZIP.
3. Set the compiler to **XeLaTeX**.
4. Set the TeX Live version to **2024**.
5. Set the main document to:

```text
src/resume.tex
```

6. Recompile.

Keep the `fonts/`, `images/`, and `src/` folders in the same relative locations. The LaTeX file expects fonts and images one directory above `src/`.

## Compile Locally

This project needs XeLaTeX because it uses `fontspec` and local font files. Use a 2024 TeX Live/XeLaTeX environment when available.

```bash
cd src
xelatex resume.tex
```
