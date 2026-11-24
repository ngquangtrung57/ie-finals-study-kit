# IE4476 / IE4483 finals study kit

Unofficial study material for two NTU (Singapore) final exams:

| Course | Title | Kit |
|---|---|---|
| **IE4476** | Image Processing and Computer Vision | [IE4476_study_kit.zip](https://github.com/ngquangtrung57/ie-finals-study-kit/releases/latest/download/IE4476_study_kit.zip) |
| **IE4483** | Artificial Intelligence and Data Mining | [IE4483_study_kit.zip](https://github.com/ngquangtrung57/ie-finals-study-kit/releases/latest/download/IE4483_study_kit.zip) |

Each kit holds, for its course:

- **Study notes** (PDF, about 420-470 pages): every lecture topic, with step-by-step worked examples,
  "playbooks" (exam recipes), common traps, and a priority strip that says how often each topic comes in past papers.
  Every section says which block of the cheatsheet to use.
- **Cheatsheet** (PDF, 2 sides of A4, colour): one sheet for a restricted open-book exam.
  Both courses (v1.4): the concepts with the most past-paper marks each show a typical question solved step by step
  (rule, then the working on the example), with working tables where a step repeats a calculation (for example the
  backprop link, forward, delta and update tables); the other topics keep their formulas, procedure, one example and traps.
  v1.5: a white badge at the right of a coloured bar, for example **Q2 3/4**, means that this block was asked as Q2 in
  3 of the 4 past papers. Blocks with no fixed question number have no badge.
  **IE4476 v1.6: new sheet (v3).** Side 1 = Part A, the exam pattern: cards A1-A10 in paper order, each with what the
  paper asks, a WHICH CASE? table, plain-word steps that follow the lecture or tutorial method, a worked example with
  named numbers, and a WRITE box. Side 2 = Part B, general knowledge B1-B13. About 3.9 pt font, larger bottom margin.
  The old IE4476 sheet is kept as `IE4476_cheatsheet_v2.pdf`.
- **Exam how-to book** (PDF, IE4476: 213 pages, IE4483: 244 pages; rewritten in v1.2): the practical version of the
  notes, without background theory. For each exam task, one example is solved step by step: each step gives the
  general rule, then the same step on the example, with a picture whenever the step changes something you can draw.
  Every formula has a list that says what each symbol means. Then come the traps, a practice question with its
  step-by-step solution, and a revise box at the end of each part.
  IE4476 also has a short version (v1.5, 116 pages): only the sections asked in the 3 past papers and the sections
  they need, with the same section numbers as the full book.
- **Past-paper worked solutions**:
  - a PDF book (IE4476: 3 papers, 12 questions; IE4483: 4 papers, 16 questions), and
  - **click-to-reveal pages** (HTML): nothing is shown at first. For each part you open the cheatsheet hint,
    the final answer only, the next step, all steps of each method, and the detailed explanation, one by one.
- **Animations** (HTML, IE4476: 20, IE4483: 24): step-by-step motion pictures of the algorithms
  (histogram equalisation, convolution, Hough transform, Otsu, search, alpha-beta, Apriori, k-means, backprop, ...).
- The LaTeX and Python sources of all of the above.

## Download

**In a browser:** open the [latest release](https://github.com/ngquangtrung57/ie-finals-study-kit/releases/latest)
and click the zip for your course (about 65 MB each). Then unzip it.

**From a terminal:**

```bash
# with curl
curl -LO https://github.com/ngquangtrung57/ie-finals-study-kit/releases/latest/download/IE4476_study_kit.zip
curl -LO https://github.com/ngquangtrung57/ie-finals-study-kit/releases/latest/download/IE4483_study_kit.zip
unzip IE4476_study_kit.zip

# or with the GitHub CLI
gh release download --repo ngquangtrung57/ie-finals-study-kit --pattern '*.zip'
```

## Use

After you unzip, the files you need are in `IE44xx-study/study/IE44xx/` (replace `IE44xx` with your course):

| File or folder | What it is | How to open |
|---|---|---|
| `IE44xx_notes.pdf` | Study notes | Any PDF reader. The links (chapter, PYP tags, cheatsheet tags) are clickable. |
| `IE44xx_cheatsheet.pdf` | 2-sided A4 cheatsheet | Print on **one A4 sheet, double-sided, in colour, at 100 % scale** (not "fit to page"). |
| `IE44xx_howto.pdf` | Exam how-to book (step by step: rule, example, picture, practice) | Any PDF reader. Start here if the notes are too long. |
| `IE4476_howto_short.pdf` | Short IE4476 how-to: asked topics only | Any PDF reader. |
| `IE44xx_pyp_solutions.pdf` | Past-paper solutions book | Any PDF reader. Shows everything (no hiding). |
| `pyp_solutions/index.html` | Click-to-reveal past-paper pages | Open in a browser (double-click). Start here to pick a question. |
| `animations/index.html` | Algorithm animations | Open in a browser. Use the play / step buttons. |

Notes:

- The HTML pages are self-contained. They work offline from your disk; no server and no internet needed.
  Keep each page in its folder (the index pages link to their neighbours).
- A reveal page is 1-5 MB, so it can take a few seconds to open. Tested in Chrome/Chromium; Firefox and Safari should work too.
- Suggested way to study a past paper: try the question on paper first. Then open only the **Cheatsheet hint**.
  Then **Final answer** to check. Use **Next step** only where you are stuck, and read the **Explanation** last.
- "Side S, block N" in the notes and solutions means: cheatsheet side S (1 or 2), coloured bar number N.
  For IE4476 these links point to the old sheet `IE4476_cheatsheet_v2.pdf`.

## What is not included

- **The past exam papers themselves.** The scans belong to the university, so this public kit does not include them.
  The worked solutions restate each question so that you can follow them, and the notes still list every past-paper
  question in their appendix index.
- The lecture slides and other original course files.

## Rebuild (optional, advanced)

The sources are LaTeX (`chapters/*.tex`, `howto/*.tex`, `cheatsheet/*.tex`, `pyp/sol/*.tex`) and Python (`common/tools/`, check
scripts in `pyp/sol/check/`). To rebuild you need a TeX Live installation (pdflatex, with TikZ, forest, tcolorbox,
booktabs) and Python 3 with PyMuPDF. The build scripts (`build_book.sh`, `build_chapter.sh`, `build_cheat.sh`, `build_cheat3.sh`, `build_howto.sh`,
`common/tools/pyp_build.py`) contain absolute paths of the author's machine in their `R=` / `B=` variables: change them
first. Some steps (`assemble.py`, `crop_slide.py`) need the original course PDFs, which are not included.
The check scripts run standalone: `python3 IE44xx/pyp/sol/check/<exam>_Q<n>.py` recomputes every number of a solution.

## Disclaimer

This is a student's personal study material. It is **not** official, not endorsed by NTU or the course lecturers,
and the worked solutions are **not** official answers. Every solution was recomputed by a check script and reviewed
independently, but mistakes are still possible. Where a question can be read in two ways, both readings are shown.
If you find a mistake, please open an issue.
