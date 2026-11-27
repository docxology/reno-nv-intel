# Operations and offline verification

The consumer pins Bun 1.4.2 and the shared engine through its frozen lockfile.
The [deployment](../region.json) selects the regional configuration, civic
profile, and monitor allowlist. The [source policy](sources.md) explains their
limits. The native commands run against retained public inputs and their
archived receipts.

## Local checks

Install Bun 1.4.2 and the exact Poppler extractor below. From the repository root:

```sh
bun install --frozen-lockfile
bun run publication:check
bun run validate
bun run documents:check
bun run manuscript:validate-render -- --bundle
bun run pages:export
bun run pages:validate -- .pages
```

`documents:check` rehashes the retained City Title 18 PDF and reruns
`pdftotext -layout` with UTF-8. It reports physical pages and nonempty lines.
`publication:check` compares actual HEAD or explicitly selected `--staged`
blobs with the local public inputs and native packet. Static export materializes
the site in `.pages/`; validation inspects that local export. Live collection
commands and Pages deployment are separate workflows.

## Manuscript outputs

The [canonical manuscript guide](manuscript/README.md) builds an offline PDF
and HTML using the pinned Template Stages 03 and 04 with aggregate variables and
the archived figures. The manuscript describes the preserved edition, source
clocks, and coverage boundaries. The reader build produces a draft, so its
output carries no legal currency or scientific approval.

The [archived native packet](../review/0.1.0-draft/) has its own renderer pin,
`c18dae54a07fe6ac3a7b1a1a274251c169a12e7a`. The
[native review workflow](../.github/workflows/manuscript.yml) specifies that
toolchain, including its lockfiles, native dependency hashes, and
`REGION_TEMPLATE_ROOT` and `REGION_TEMPLATE_PYTHON` paths. A new native review
build is a separate operation. Its packet includes draft PDF/HTML, extracted
text, citations, evidence and review receipts, a page-count profile and CSV,
and the figure sources. Source rights and original observations apply to
both builds.

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
