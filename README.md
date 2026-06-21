# FFFFysics

> Chasing **Flow, Flux, Field, and Force** — toward electromagnetic space propulsion.

<p align="center">
  <img src="assets/ffffysics-lockup.png" alt="FFFFysics" width="420">
</p>

A static research and knowledge archive at the intersection of continuum mechanics and plasma physics.

**Live site:** https://ffffysics.github.io/

## Repository structure

```text
FFFFysics.github.io/
├── index.html
├── sample-knowledge.json
├── README.md
└── assets/
    ├── ffffysics-mark.svg
    └── ffffysics-lockup.png
```

`assets` is a **folder inside the `main` branch**, not a separate branch.

## Knowledge archive

- Notes and epistemic relations: `direct`, `analogy`, `hypothesis`, `rejected`
- First visit: loads `sample-knowledge.json`
- Later edits: the browser copy in `localStorage` takes priority
- Backup: use **export**
- Restore: use **import**

Because GitHub Pages is static hosting, browser edits are not committed to the repository automatically. Export the JSON and replace `sample-knowledge.json` when you want to publish an updated public seed.

## Deploy through GitHub web

1. Open the repository and select the `main` branch.
2. Upload `index.html`, `sample-knowledge.json`, and `README.md` to the repository root.
3. Choose **Add file → Create new file** and enter `assets/README.md` once if the folder does not exist.
4. Open the new `assets` folder and upload `ffffysics-mark.svg` and `ffffysics-lockup.png`.
5. Commit all changes directly to `main`.
6. In **Settings → Pages**, publish from `main` and `/ (root)`.

## Public links

- GitHub: https://github.com/FFFFysics/FFFFysics.github.io
- Email: iron7344@gmail.com

## Local preview

Serving through a small local web server allows `sample-knowledge.json` to load exactly as it does on GitHub Pages:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/`.
