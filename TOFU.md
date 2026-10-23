# LOOPY on Tofu

LOOPY, by Nicky Case, is a tool for thinking in systems. Draw variables and the positive or negative relationships between them, then play the model to explore feedback loops. The application runs entirely in the browser and keeps the upstream name, artwork, favicon, author credits, and links to the author's work.

## Run on Tofu

- Framework preset: `static`.
- Site root and output directory: repository root (`.`).
- Entry page: `/index.html`, the upstream introduction with links to the editor.
- Current editor: `/v1.1/`; the older `/v1/` editor remains available.
- Install command: none; no package manager or external runtime dependencies.
- Build command: none; HTML, CSS, JavaScript, and images are already in the repository.
- Environment variables: none.
- Database, API keys, sign-in, and server process: none.

Serve the repository unchanged with any static host. For a local check:

```sh
python3 -I -m http.server 48937 --bind 127.0.0.1 --directory /absolute/path/to/loopy
curl --fail --silent --show-error --output /dev/null --write-out '%{http_code}\n' http://127.0.0.1:48937/
curl --fail --silent --show-error --output /dev/null --write-out '%{http_code}\n' http://127.0.0.1:48937/v1.1/
```

Models can be saved as links that include the entire model in the URL, or exported and imported as `.loopy` files in v1.1. There is no cloud storage, account system, or automatic cross-device saving. Anyone with a model URL can read the model. The editor uses the current site's origin when generating share and embed URLs.

## Adaptations

- Changed the three built-in example links in each of `v1/pages/examples/index.html` and `v1.1/pages/examples/index.html` to relative URLs. Selecting an included example now opens this copy's corresponding editor instead of sending users to `ncase.me`.
- Added this deployment and provenance guide.
- No runtime libraries, analytics, tracking scripts, advertisements, or hosted services were added. Core simulation code and branding are unchanged. Optional community examples and author/support links remain upstream links; those external destinations are not needed to create, play, save, or load models and are not verified by this fork.

## Upstream and license

- Upstream: https://github.com/ncase/loopy
- Upstream default branch: `gh-pages`.
- Base commit: `2d8e13f0a006f4024f27ad1712d7f9c2c1ad7cd9`.
- Fork: https://github.com/tofu-gallery/loopy
- `main` mirrors the upstream commit without adaptation commits. `gh-pages` is retained from the fork.
- Adaptation branch: `tofu`.
- Gallery pin: `pin/2026-10-23`, created only after local verification succeeds.
- License: CC0 1.0 Universal; see the unchanged `LICENSE.txt`. The upstream README's third-party credit list and all existing copyright notices remain intact.
