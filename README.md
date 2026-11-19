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

## What is not included

- **The past exam papers themselves.** The scans belong to the university, so this public kit does not include them.
  The worked solutions restate each question so that you can follow them, and the notes still list every past-paper
  question in their appendix index.
- The lecture slides and other original course files.

## Rebuild (optional, advanced)

The sources are LaTeX (`chapters/*.tex`, `cheatsheet/*.tex`, `pyp/sol/*.tex`) and Python (`common/tools/`, check
scripts in `pyp/sol/check/`). To rebuild you need a TeX Live installation (pdflatex, with TikZ, forest, tcolorbox,
booktabs) and Python 3 with PyMuPDF. The build scripts (`build_book.sh`, `build_chapter.sh`, `build_cheat.sh`,
`common/tools/pyp_build.py`) contain absolute paths of the author's machine in their `R=` / `B=` variables: change them
first. Some steps (`assemble.py`, `crop_slide.py`) need the original course PDFs, which are not included.
The check scripts run standalone: `python3 IE44xx/pyp/sol/check/<exam>_Q<n>.py` recomputes every number of a solution.

## Disclaimer

This is a student's personal study material. It is **not** official, not endorsed by NTU or the course lecturers,
and the worked solutions are **not** official answers. Every solution was recomputed by a check script and reviewed
independently, but mistakes are still possible. Where a question can be read in two ways, both readings are shown.
If you find a mistake, please open an issue.
