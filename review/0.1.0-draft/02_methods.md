# Methods {#sec:methods}

## Ownership and configuration

The Reno repository contains configuration, public source evidence, manuscript sources, acceptance tests, workflows and a small importer. Shared methods are imported from the full commit 0eb390bc804c5a3ae5304839187f914364d0bec3. The deployment identity is reno-nv. Its geographic anchor and rectangular watch extent are engineering parameters around Reno; they are not surveyed city boundaries. Washoe County FIPS 32031 selects county-level drought observations, which must not be described as a city-only measurement. The NWS policy uses public forecast zone NVZ003, whose coverage includes areas beyond Reno.

The enabled roster consists of earthquake, weather, air quality, drought and smoke. Declaring a monitor permits execution; it does not certify its response. The required compatibility policy document also contains fields for disabled adapters. Those fields confer no runtime eligibility. California wildfire, road, utility and fuel adapters are not enabled for Reno. Nevada 511, City road closures, flood management, emergency management and public-health links remain separate source-catalog entries where no corresponding verified local adapter is selected.

## PDF acquisition and replay

The document descriptor binds a stable document ID to an exact configured source ID and URL, a human-readable title, the stated edition and rights information. The captured PDF is limited to 16 MB, the collection to 64 MB, and extraction to 10,000 physical pages per document. Live acquisition uses a bounded public HTTPS transport and preserves HTTP failures. In this deployment the shared HTTP client returned 403 for the City PDF, while a separate bounded, unauthenticated curl capture succeeded. We therefore use an explicit recorded-capture import. Its source ID, URL, original retrieval time, declared transport, status and PDF hash must match the deployment and admitted bytes. The transport declaration is operator-recorded provenance backed by the actual command evidence; the import is not a retrospective live-adapter pass. Poppler pdftotext runs with layout preservation and explicit UTF-8 output. Its terminal form-feed boundary defines physical pages; page numbers are one-based and include the cover and contents.

For every page the receipt retains text, its SHA-256 and the number of nonempty extracted lines. It also retains the PDF hash, byte size, acquisition timestamp and extractor version. A complete collection is promoted transactionally; a failed acquisition preserves the previous accepted collection and leaves diagnostic staging. On replay, the original PDF is rehashed and extracted again. Exact page membership and text must agree. Edited extracted text does not pass merely because its own hash was recomputed.

Line counts are properties of a particular extraction and layout. They do not identify legal provisions. Images, multi-column material, tables, symbols and reading order may not survive text extraction faithfully. Search returns matching physical pages and links to the exact retained PDF page fragment, with the upstream location recorded separately. No section segmentation, OCR, statutory interpretation or completeness test is inferred from this path.

## Evidence transformation and native rendering

![Local evidence and authored prose compose with shared methods and an independently pinned template. Arrows describe architecture rather than measured effects.](../output/figures/architecture.png){#fig:architecture}

The shared renderer derives numerical variables, a full page-level CSV, descriptive statistics and publication figures from captured inputs. It fingerprints the deployment, policy, source bytes, lockfile, prose, cover and renderer implementation. Claim-ledger evidence must name captured public files. Native rendering calls the pinned template's RenderManager for combined PDF and web output, retains its provenance and offline assets, and validates exact member bytes before packaging. Pages consumes the same validated packet. A renderer pass is technical evidence and does not supply independent scientific approval.
