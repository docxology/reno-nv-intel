# Introduction {#sec:introduction}

## A regional system must preserve its evidence boundary

A region is more than a label on a dashboard. Its jurisdiction, source publisher, document editions, forecast zones and public-service providers determine which operations are meaningful. Reusing software from Crescent City or Davis is appropriate; reusing their municipal corpus, coastal alerts or California-specific eligibility as Reno evidence is not. A thin consumer needs enough local ownership to make these differences explicit while leaving acquisition, validation, search, figures and rendering in one shared implementation.

Reno provides a useful engineering case because its publicly linked code system differs from the eCode360 provider used by the earlier consumers. The City Attorney's guidance identifies the Clerk's role in publishing the municipal code [@renoattorney]. This project follows the City's source identity but does not infer that one access mechanism works because another does. Initial access errors for the two Municode collections are recorded as an availability boundary. The official Title 18 PDF supplies an accessible, explicitly bounded document edition [@reno2026]. The study asks whether this edition can be acquired, inspected, searched and published without claiming that it is the whole Reno municipal code.

## Relation to data and reproducibility scholarship

PROV-DM separates data entities, producing activities and responsible agents [@prov2013]. Here, the PDF is an entity, extraction is an activity and local source ownership remains distinct from shared software ownership. The receipts implement those distinctions pragmatically; they are not a complete PROV serialization or a conformance claim.

W3C guidance treats provenance, quality information, versioning and preservation as publication concerns [@dwbp2017]. The design retains both the publisher's stated edition and the acquisition time, so later rendering cannot silently advance the source clock. It also distinguishes HTTP reachability from semantic acceptance: a successful response does not prove complete or current content.

The FAIR principles motivate discoverability, interpretable metadata and reusable identifiers [@fair2016]. The project publishes source identities and machine-readable commitments but does not claim a formal FAIR assessment. Dataset documentation provides another useful discipline: intended use, composition and collection conditions should travel with data [@gebru2021]. Data statements additionally emphasize the limits of transferring language data between contexts [@bender2018]. This municipal administrative text is neither a representative sample of residents nor evidence of their preferences.

The reported contribution has three parts: a provider-independent document plane in region-intel; an independent Reno deployment that composes that plane with national monitors; and a complete template-rendered review packet whose counts and figures derive from retained bytes. No social, causal or model-performance result is asserted.
