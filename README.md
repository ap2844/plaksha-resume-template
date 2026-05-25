# Plaksha Resume Template Fork

This is my fork of [`jalan-subham/plaksha-resume-template`](https://github.com/jalan-subham/plaksha-resume-template), adapted into a simpler single-source LaTeX resume setup.

The editable resume now lives in:

```text
src/resume.tex
```

The old split section files were consolidated into this one file, so resume content, custom commands, and layout definitions are all in one place.

## What Was Done

1. Cloned the original resume template repository locally.
2. Combined the original split LaTeX files into one self-contained resume source.
3. Moved the final source file to `src/resume.tex`.
4. Updated image and font paths so the source can still find:
   - `../images/plaksha.png`
   - `../fonts/Calibri-*.ttf`
5. Forked the original repository to `ap2844/plaksha-resume-template`.
6. Set the local Git remotes as:

```bash
origin   git@github.com:ap2844/plaksha-resume-template.git
upstream git@github.com:jalan-subham/plaksha-resume-template.git
```

7. Switched the remotes to SSH so future pushes from WSL2 use the local SSH key.
8. Pushed the consolidated version to the fork.
9. Starred the original upstream repository.
10. Updated GitHub CLI in WSL2 from Ubuntu's older package to GitHub's official apt package.

## Repository Structure

```text
.
├── README.md
├── fonts/
│   ├── Calibri-Bold.ttf
│   ├── Calibri-BoldItalic.ttf
│   ├── Calibri-Italic.ttf
│   └── Calibri-Regular.ttf
├── images/
│   └── plaksha.png
└── src/
    └── resume.tex
```

## Editing The Resume

Open `src/resume.tex` and replace the placeholder content in these sections:

- heading and contact links
- education
- work experience
- projects
- positions of responsibility
- skills
- achievements

The template currently includes the Plaksha logo through this block:

```tex
\begin{tikzpicture}[remember picture, overlay]
    \node[anchor=north east, xshift=-1cm, yshift=-1cm] at (current page.north east) {
        \includegraphics[width=5cm]{plaksha}
    };
\end{tikzpicture}
```

Remove that block from `src/resume.tex` if you do not want the logo.

## Using On Overleaf

1. Open Overleaf.
2. Create a new project.
3. Choose either:
   - **Import from GitHub** and select `ap2844/plaksha-resume-template`, or
   - upload a ZIP of this repository.
4. Open the Overleaf project menu.
5. Set **Compiler** to **XeLaTeX**.
6. Set **Main document** to:

```text
src/resume.tex
```

7. Recompile.

Keep the `fonts/`, `images/`, and `src/` folders in the same relative locations. The LaTeX file expects the fonts and logo to be one directory above `src/`.

Overleaf recommends keeping the main document at the top level for maximum compatibility, but this fork intentionally keeps the source in `src/resume.tex`. If Overleaf has trouble detecting it automatically, manually set the main document as described above.

## Compiling Locally

This project needs XeLaTeX because it uses `fontspec` and local Calibri font files.

From the repository root:

```bash
cd src
xelatex resume.tex
```

If `xelatex` is not installed, use Overleaf or install a TeX distribution such as TeX Live.

## Git Workflow

Normal work happens against your fork:

```bash
git status
git add src/resume.tex README.md
git commit -m "Customize resume"
git push
```

The original template remains available as `upstream`:

```bash
git fetch upstream
```

## Notes

- The repository is a fork, so attribution to the original author is preserved through GitHub.
- No license was added here because the upstream repository does not currently include one.
