# Reno NV Intel documentation

The regional consumer applies the pinned [region-intel engine](https://github.com/docxology/region-intel/tree/51b18faeec1454e80a533795c6e3859eaeb5fc9b)
to Reno's identity, source policy, and retained evidence. The consumer contains
configuration, public inputs, a thin command importer, and deployment-specific
scholarship.

| Guide | What it covers |
|---|---|
| [Operating and verification guide](reproducibility.md) | Frozen dependencies, offline native checks, static exports, and build outputs. |
| [Architecture](architecture.md) | The shared engine, consumer-local policy, and artifact custody. |
| [Source and coverage policy](sources.md) | Jurisdictions, documented source bounds, and unavailable or stale states. |
| [Source validation](source-validation.md) | Recorded source checks and extraction limits. |
| [Manuscript and render guide](manuscript/README.md) | Canonical sections, citations, figures, and pinned PDF/HTML verification. |
| [Maintenance backlog](TODO.md) | Pending deployment work. |

The [deployment](../region.json) declares the source catalog and allowed monitors.
The [civic profile](../configs/reno-civic.json) and [collection policy](../configs/reno-region.json)
set the identity and operating bounds. The [document catalog](../documents.json)
binds the retained City Title 18 edition. The [archived review packet](../review/0.1.0-draft/)
contains the previously built PDF, complete offline HTML, figures, and receipts.
