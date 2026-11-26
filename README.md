# Listening to the Chip: DRDO SAG internship showcase

A static presentation site (plain HTML, CSS and JavaScript, no build step, no internet needed) for walking through the internship:
journey, class notes, every program with its output, a live CPA demo, results, the report and viva Q&A.

## Open it
- **Locally:** double-click `index.html`. Or run `python3 -m http.server` in this folder and open http://localhost:8000.
- **Presenting:** press **P** for presentation mode (fullscreen), **← →** to move between sections, **T** for light/dark, **Esc** closes an enlarged figure.

## Put it on GitHub Pages
1. Create a new repository on GitHub (for example `internship-showcase`).
2. Upload everything in this folder (the files must sit at the top level of the repo, next to `index.html`):
   ```
   git init && git add . && git commit -m "Internship showcase"
   git branch -M main
   git remote add origin https://github.com/<your-username>/internship-showcase.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Build and deployment → Deploy from a branch → main / (root) → Save**.
4. After a minute the site is live at `https://<your-username>.github.io/internship-showcase/`.

## What is real and what is replayed
| Part | Source |
|---|---|
| Code Lab source files | the actual files, unchanged (`code/`) |
| Code Lab terminal output | captured by compiling and running each program (`code/outputs/`); *Run* replays it |
| CPA Live A (real hardware) | values from the recorded run on the supplied ChipWhisperer dataset; the dataset itself (`aes_dataset.h5`) is not included |
| CPA Live B | runs live in the browser on **synthetic** traces (labelled as such) |
| Results figures | your plots and screenshots (`assets/img/`) |
| Report | `assets/report/Internship_Report_Devanshi_Yadav.pdf` |

## Layout
```
index.html          page structure
css/style.css       styling (dark and light themes)
js/app.js           navigation, notes, Code Lab, results, Q&A
js/cpa.js           CPA replay and the in-browser CPA simulator
js/data.js          source code + captured outputs (generated)
code/               the programs and their outputs (also downloadable from the Code Lab)
assets/             figures and the report PDF
```
To change text (journey, class notes, Q&A), edit the arrays at the top of `js/app.js`.
