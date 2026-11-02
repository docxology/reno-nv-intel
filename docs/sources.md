# Reno source and coverage policy

The complete catalog is region.json; document acquisition is documents.json. The City's Title 18 PDF cover states effective January 8, 2025 and amended June 3, 2026. This is a stated edition, not continuing current law. The original PDF is preserved; every physical page is extracted and replayed. Tables, images, printed labels and reading order require the original. Neither Municode administrative nor land-development collections are represented as successfully scraped: initial ordinary public probes returned access errors. No API ID or eCode identity is invented, and no access control is bypassed.

National adapters: USGS earthquake feed (magnitude 4 within 200 km of the configured Reno anchor), NWS NVZ003, public air-quality stations within 50 km, US Drought Monitor Washoe FIPS 32031, and the shared smoke watch box. Provider success and source freshness are separate acceptance. These areas are engineering extents, not city survey boundaries. County drought is not a city measurement. NWS zone coverage extends beyond Reno.

The v1 shared policy schema requires compatibility parameters for all adapters. Disabled marine, California road, wildfire, utility, fuel and other fields remain unselected compatibility configuration and grant no coverage. Only enabledMonitors permits execution. Do not enable them merely by renaming a county. Nevada 511 has its own developer contract; no authenticated API availability is inferred from a public landing page. City road closures, NNPH air quality, TRFMA flood information, Washoe emergency management, permits and meeting portals need separately reviewed adapters before semantic live-feed claims.

Source checks record HTTP reachability with original clocks and status. A 200 landing page is not a parsed archive, and a static agenda-link count is not a complete meeting archive or validated meeting schedule. Unavailable and empty are distinct. No news feed is configured in this initial deployment; cataloged official services are not fabricated news observations.

Source attribution, document titles and third-party rights travel with retained evidence. The project license does not relicense source illustrations, marks or linked sites. No private records or resident-level profiles are collected. See the manuscript's data statement and claim ledger for intended uses and limits.

## Transport-specific observation

The shared HTTP fetcher returned 403 for the City PDF in the initial deployment. A separately recorded, bounded, unauthenticated curl download succeeded. `documents:import -- --source output/document-capture` admits its profile, exact source ID/URL, original clock, transport, HTTP status and PDF hash before replay. These are operator-recorded provenance backed by the actual command evidence, not a retrospective pass for the failed shared fetch. The public source checks retain the 403 result. Pages serves the exact retained PDF so its search cannot silently point into a later upstream edition.


### Retained monitor clocks and a metadata defect

The initial batch was assessed at 2026-11-01T23:57:12.738Z. Its original source-health receipts distinguish check/retrieval clocks from AirNow's 2026-11-01T23:00:00.000Z observation, the drought product dated 2026-10-27 and the HMS product dated 2026-11-01. The retained public rows preserve these original fields, provider identity and status; rendering does not turn them into current observations. Missing or stale clock evidence cannot support an available row.

The original weather report records forecastZone NVZ003, but its health receipt URL incorrectly names CAZ101. That historical metadata is retained unchanged and is not requested-zone evidence. The shared runner now uses the collector's per-call URL resolver for future health receipts. This correction does not retroactively repair the old receipt or advance its clock.
