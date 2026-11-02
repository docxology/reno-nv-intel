# Reproduction and native rendering

Install Bun 1.4.2 and Poppler. Run the README's frozen acceptance sequence. `documents:check` rehashes the retained original PDF and reruns pdftotext -layout with UTF-8. Tool drift that changes page text is a visible failure; never silently rebaseline. `publication:check` verifies actual HEAD or `--staged` blobs against working public inputs and the complete native packet.

Native rendering uses docxology/template commit c18dae54a07fe6ac3a7b1a1a274251c169a12e7a. Prepare its frozen Python 3.14 rendering environment and documented npm lockfile assets. Its own toolchain controls that external project. Install XeLaTeX, TeX Gyre and Latin Modern OpenType fonts, qpdf, Poppler, Pandoc 3.12.1 and pandoc-crossref v0.3.26. Set REGION_TEMPLATE_ROOT and REGION_TEMPLATE_PYTHON; use external caches and TMPDIR when working in GitVault. Then run `bun run manuscript:bundle` and `bun run manuscript:validate-render -- --bundle`. The workflow records exact release hashes for native binaries and retains failure output.

The review packet contains manuscript.pdf, manuscript.txt, complete web/index.html plus offline assets, evidence.json, review-receipt.json, template-render.json, bibliography, ledger, projected sources, all-page CSV/profile, cover and three figures in PNG/PDF/SVG. It is a review draft. PDF/UA, legal currency, scientific approval and civic impact are separate acceptance.


## Exact PDF extraction toolchain

The accepted Title 18 text was extracted with Poppler 26.10.0. Ubuntu 24.04's
default Poppler 24.02.0 does not replay those exact page bytes. The initial
hosted failures are retained; the source PDF, extracted text, page counts and
original capture clocks were not replaced to obtain a passing build.

The Linux workflows use `configs/pdf-tools-linux-64.lock`: 72 exact conda-forge
artifact URLs with SHA-256 checksums, including Poppler 26.10.0 build h7813f90_0
and its complete resolved native dependency closure. Micromamba 2.10.0-0 and
the setup action are pinned; shell initialization is disabled. This lock targets
linux-64 Ubuntu 24.04/glibc 2.39 and is not a macOS installation file. Existing
macOS Poppler 26.10.0 remains the recorded extraction environment. Any other
toolchain must pass the same exact byte replay; a version label alone is not
proof of equivalent text. No text normalization or replay relaxation is used.
