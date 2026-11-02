# Results {#sec:results}

## Retained document edition

The source identifier is reno-title18. The retained PDF's cover states that the code was effective January 8, 2025 and amended June 3, 2026 [@reno2026]. Acquisition was recorded at 2026-11-01T23:40:30.028Z. The receipt identifier is:

```text
f687a3da4cad5ef36df9d242d53dc400570e93f675f907ac3391ff25c20e961a
```

The extraction contains 555 physical PDF pages and 21850 nonempty extracted lines. These replace neither legal article counts nor section counts. The PDF viewer's physical page index includes front matter; the source's printed page labels can therefore differ. The descriptive profile spans every physical page. Its minimum is 5, median 43, maximum 57 nonempty lines, with 0 pages having no nonempty extracted lines. No pages are dropped to improve the distribution.

![Complete distribution of nonempty extracted lines over physical PDF pages, with the twelve largest pages labeled by PDF page number. These layout-dependent counts are not legal section counts or a burden measure.](../output/figures/corpus-profile.png){#fig:corpus-profile}

The complete all-page CSV accompanies this figure. A page with many extracted lines may contain dense text, tabular content or formatting artifacts. A sparse page may contain an image or a chapter boundary. Neither condition identifies substantive importance. The descriptive statistics summarize this single retained edition and extraction procedure; they do not support a population confidence interval or a temporal trend.

## Composition and source availability

The source catalog contains 23 explicitly selected entries. The monitor roster contains 5 enabled adapters. Source reachability receipts, when retained, report each check's original clock and HTTP result. They do not turn a reachable landing page into a parsed operational feed. Initial public probes of the Municode administrative and land-development collections returned access errors. The shared HTTP client also returned 403 for Title 18; its retained bytes came from an explicit import of the separately recorded bounded curl capture. The Title 18 document is therefore published as a separate document collection, with no eCode360 identity and no claim of full municipal-code capture.

The live dashboard, retained observations and native manuscript are distinct artifacts. Rebuilding the static site can reproduce the document search and review packet without a new network acquisition. A separately run collection may discover later observations, including unavailable states; it does not revise this manuscript's retained document clock until a deliberate new evidence build occurs.


### Retained monitor clocks and a metadata defect

The initial batch was assessed at 2026-11-01T23:57:12.738Z. Its original source-health receipts distinguish check/retrieval clocks from AirNow's 2026-11-01T23:00:00.000Z observation, the drought product dated 2026-10-27 and the HMS product dated 2026-11-01. The retained public rows preserve these original fields, provider identity and status; rendering does not turn them into current observations. Missing or stale clock evidence cannot support an available row.

The original weather report records forecastZone NVZ003, but its health receipt URL incorrectly names CAZ101. That historical metadata is retained unchanged and is not requested-zone evidence. The shared runner now uses the collector's per-call URL resolver for future health receipts. This correction does not retroactively repair the old receipt or advance its clock.
