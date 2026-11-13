# Reno NV Intel

Composable civic evidence for Reno, Nevada, powered by [region-intel](https://github.com/docxology/region-intel).

<p align="center"><img src="docs/assets/reno-cover.png" alt="Reno, Nevada cover illustration" width="360"></p>

[Public site](https://docxology.github.io/reno-nv-intel/) · [Manuscript HTML](https://docxology.github.io/reno-nv-intel/manuscript/web/index.html) · [Manuscript PDF](https://docxology.github.io/reno-nv-intel/manuscript/manuscript.pdf)

This thin repository owns Reno identity, policy, a curated public source catalog, retained evidence, acceptance tests and authored scholarship. Its importer delegates all acquisition, extraction, search, publication and rendering to one immutable shared dependency. No copied runtime implementation lives here.

## Retained evidence

The official City Title 18 PDF is retained with source URL, stated edition, rights, acquisition clock, original bytes and all-page extraction receipts. Pages offers lexical PDF-page search and links to the source. Counts mean **physical PDF pages and nonempty extracted lines**, including front matter; they are not legal article/section counts. The shared HTTP client also received 403 for the PDF; an explicit recorded import of a bounded, unauthenticated curl capture supplies the retained bytes. This is not a live-adapter pass. Both Municode collections are cataloged independently; access errors do not become empty or fabricated code corpora. See [source policy](docs/sources.md), [architecture](docs/architecture.md), [reproduction](docs/reproducibility.md) and [review packet](review/0.1.0-draft/).

## Run and verify

Use Bun 1.4.2, Poppler pdftotext, and the frozen lockfile.

```sh
bun install --frozen-lockfile
bun run validate
bun run documents:check
bun run pages:export
bun run pages:validate -- .pages
bun run publication:check
bun run gui
```

The enabled monitors are earthquake, weather, air quality, drought and smoke. Nevada roads, public health, meetings, flood management and emergency sources have explicit catalog links and independent availability receipts. Configuration and HTTP reachability do not establish successful semantic collection, currency or calm conditions. California-specific and coastal monitors are disabled.

## Research publication

The ten-section manuscript, bibliography, claim ledger, original conceptual cover, deterministic figures and complete native packet use the actual pinned [docxology/template](https://github.com/docxology/template) RenderManager APIs. Pages includes the PDF and complete offline HTML packet. Native rebuild requires REGION_TEMPLATE_ROOT and REGION_TEMPLATE_PYTHON plus the tools in [reproduction](docs/reproducibility.md). This is a 0.1.0 **review draft**, not a formal release, current-law certification or scientific approval.

## Maintenance

`documents:acquire`, `sources:check`, `gov-meetings`, `alerts` and `observations:seed` deliberately collect or retain new evidence. Refreshes require reviewing source clocks, unavailable states and rights before rerendering. CI replays frozen public evidence; the separate collection workflow uploads new observations without silently committing them. Original contributions follow the repository license; source documents, linked material and third-party marks retain their own terms.
