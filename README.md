# FFFFysics

> Chasing **Flow, Flux, Field, and Force** — toward electromagnetic space propulsion.

<p align="center">
  <img src="assets/ffffysics-lockup.png" alt="FFFFysics" width="420">
</p>

A static research and knowledge archive at the intersection of continuum mechanics and plasma physics.

## The hero model

The home page is a two-dimensional flow-and-field model that is solved in closed
form rather than stepped numerically. Lengths are in units of the cylinder radius
`a`, speeds in the free stream `U`, and `μ₀/2π = 1`.

| Layer | Model |
|---|---|
| Flow | Uniform stream + doublet — potential flow past a circular cylinder — plus a free vortex at the pointer carried by its Milne–Thomson circle-theorem images, so `r = a` stays an exact streamline. Streamlines are contours of `ψ`. |
| Flux | Magnetic flux function of two parallel line currents, `ψ_B = −(I₁ Λ(r₁) + I₂ Λ(r₂))`. Field lines are its contours. |
| Field | `B = ∇ψ_B × ẑ`: `I/r` outside a conductor and `I r/r_c²` inside, by Ampère's law with uniform current density — so nothing diverges on an axis. |
| Force | Ampère's force per unit length between the two currents, `F = I₂ |B₁|` with `|B₁| = I₁/d`. |

Contours are traced with marching squares over the exact scalar fields, so the
lines carry no integration drift. Every number in the readout panel is computed by
the same functions that draw the picture. Dragging drives the vortex; clicking
reverses the probe current, and antiparallel currents repel.

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
- Publish: use **publish** (commits `sample-knowledge.json` straight to this repository)

## Publish from the browser

GitHub Pages is static hosting, so the page has no server of its own. The **publish**
button therefore talks to the GitHub Contents API directly from the browser: it reads the
current `sample-knowledge.json`, commits the archive over it, and GitHub Pages redeploys
on its own.

Authentication is a fine-grained personal access token that you supply once:

1. Create one at <https://github.com/settings/personal-access-tokens/new>.
2. **Repository access** → *Only select repositories* → `FFFFysics.github.io`.
3. **Permissions** → *Repository permissions* → **Contents: Read and write**.
4. Paste it into the publish dialog and choose whether to keep it.

The token is held in `localStorage` under `ffp-gh` (or only in the tab, if you pick
*this tab only*) and is sent to `api.github.com` and nowhere else. It is a credential in
a browser, so it is worth keeping short-lived and single-repository, and `forget token`
in the dialog clears it. Do not enter a token on a machine you do not control — anyone
with access to that browser profile can read it.

Export/import still work unchanged for offline backups and for moving an archive between
browsers.

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
