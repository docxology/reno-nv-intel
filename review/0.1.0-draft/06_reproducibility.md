# Reproducibility and Artifact Specification {#sec:reproducibility}

## Frozen public inputs

The input commitment is:

```text
2dd4d69f82c38a2a2893164857ccf3d60460535de5f368314b17fb75b1bb6104
```

The shared core pin is 0eb390bc804c5a3ae5304839187f914364d0bec3. The external template pin is c18dae54a07fe6ac3a7b1a1a274251c169a12e7a. The complete packet retains projected prose, bibliography, claim ledger, source commitments, page-level profile, CSV, three analytical figures in PNG/PDF/SVG, native PDF, extracted text and offline HTML assets. Reproducing source-derived counts requires the public retained PDF and the recorded extraction contract. Acquisition is a separate network operation; it should not be silently repeated during an offline acceptance build.

```sh
bun install --frozen-lockfile
bun run validate
bun run documents:check
bun run manuscript:check
bun run manuscript:validate-render -- --bundle
bun run publication:check
bun run pages:export
bun run pages:validate -- .pages
```

To create a new native edition, configure the actual pinned template checkout and its frozen rendering environment, install the documented native tools, then run:

```sh
bun run manuscript:bundle
```

The REGION_TEMPLATE_ROOT and REGION_TEMPLATE_PYTHON environment variables select that external checkout and interpreter. There is no direct-Pandoc substitute when the pinned API is unavailable. A failed render retains staging and preserves the preceding complete packet.

## New observations and version changes

```sh
bun run documents:acquire
bun run sources:check
bun run gov-meetings
bun run alerts
bun run observations:seed
```

Where a public source is unavailable to the shared client, preserve the failed acquisition. A separately recorded public capture can be admitted explicitly:

```sh
bun run documents:import -- --source output/document-capture
```

The import directory and strict capture.json schema are documented in the shared document methods. Never invent successful transport metadata or advance a captured source clock during import.

These commands make new observations and therefore change evidence. They are not equivalent to replaying the retained edition. Check source rights and profile policy before collection; inspect unavailable states afterward. A changed seed, configuration, lockfile, prose or renderer requires new input commitments and a new rendered packet. Exact Git publication checks compare the public working bytes against HEAD or the staged index; they neither stage files nor publish by themselves.

## Validation scope

Meaningful negative controls alter the input that a check is supposed to protect: change original PDF bytes, rehash edited page text, remove a page, change a source URL, exchange a profile, add an unexpected published member or modify a tracked native asset. Such cases must fail. Broad core qualification, consumer acceptance, exact-byte Pages replay, hosted workflow results and visible artifact review remain separately reportable evidence. A failure in one lane is not erased by a pass in another.
