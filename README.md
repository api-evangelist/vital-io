# Vital (Junction)

API Evangelist catalog entry for **Vital** — the health-data API platform now operating as **Junction** (formerly `tryVital`). Junction gives digital-health, virtual-care, diagnostics, wellness, and EHR/EMR builders a single integration to wearable-device data and nationwide US lab testing.

- Site: <https://www.junction.com>
- Docs: <https://docs.junction.com>
- API reference: <https://docs.junction.com/api-details/junction-api>
- Dashboard: <https://app.junction.com>
- Status: <https://status.tryvital.io>
- GitHub org: <https://github.com/tryVital>
- Canonical OpenAPI (Fern): <https://github.com/tryVital/vital-fern-api>
- Pricing: <https://www.tryvital.com/pricing>

## What Vital / Junction does

- **Wearables.** Normalized data from 300+ providers — Apple HealthKit, Android Health Connect, Samsung Health, Oura, Whoop, Garmin, Fitbit, Withings, Polar, Strava, Wahoo, Cronometer, Ultrahuman, Peloton, Zwift, 8Sleep, Hammerhead, Dexcom (cloud + BLE), Freestyle Libre (cloud + BLE), Abbott LibreView, Beurer, Kardia, Accu-Chek, Contour, Omron, and more — exposed as daily summaries and per-sample timeseries through one schema.
- **Labs.** A nationwide US lab network (all 50 states including NY, NJ, RI) covering at-home testkits, at-home phlebotomy, walk-in / Patient Service Center collection, and on-site collection. One API for ordering, scheduling, results (JSON + PDF), and the lab-test compendium.
- **Sense.** Continuous-query and aggregation layer that turns raw ingest into clinically meaningful metrics (sleep debt, HRV trends, glucose variability) without you owning the aggregation infrastructure.
- **Lab Report Parser.** Submit existing PDF lab results and have them normalized into the same biomarker schema as Junction-fulfilled orders.
- **Webhooks + ETL.** Svix-backed webhook delivery plus BYO ETL destinations (Azure Event Hubs, Google Cloud Pub/Sub, RabbitMQ).
- **Regional residency.** US (`api.us.junction.com`) and EU (`api.eu.junction.com`) deployments with regional API-key prefixes (`pk_us_`, `pk_eu_`, `sk_us_`, `sk_eu_`).
- **Compliance.** HIPAA (BAA), SOC 2 Type 2, ISO 27001, GDPR-ready.

## APIs in this catalog entry

| API | Operations | OpenAPI | Capability |
| --- | --- | --- | --- |
| Users | 19 | [`openapi/vital-users-api-openapi.yml`](openapi/vital-users-api-openapi.yml) | [`capabilities/users.yaml`](capabilities/users.yaml) |
| Link | 14 | [`openapi/vital-link-api-openapi.yml`](openapi/vital-link-api-openapi.yml) | [`capabilities/link.yaml`](capabilities/link.yaml) |
| Wearables Data | 95 | [`openapi/vital-wearables-api-openapi.yml`](openapi/vital-wearables-api-openapi.yml) | [`capabilities/wearables.yaml`](capabilities/wearables.yaml) |
| Lab Testing | 56 | [`openapi/vital-lab-testing-api-openapi.yml`](openapi/vital-lab-testing-api-openapi.yml) | [`capabilities/lab-testing.yaml`](capabilities/lab-testing.yaml) |
| Lab Report Parser | 2 | [`openapi/vital-lab-report-parser-api-openapi.yml`](openapi/vital-lab-report-parser-api-openapi.yml) | [`capabilities/lab-report-parser.yaml`](capabilities/lab-report-parser.yaml) |
| Sense | 3 | [`openapi/vital-sense-api-openapi.yml`](openapi/vital-sense-api-openapi.yml) | [`capabilities/sense.yaml`](capabilities/sense.yaml) |
| Team | 8 | [`openapi/vital-team-api-openapi.yml`](openapi/vital-team-api-openapi.yml) | [`capabilities/team.yaml`](capabilities/team.yaml) |
| Management | quote-only | upstream docs only | [`capabilities/management.yaml`](capabilities/management.yaml) |

The mirrored, single-file upstream spec is preserved at [`openapi/vital-openapi-original.json`](openapi/vital-openapi-original.json) (and its YAML twin at [`openapi/vital-openapi-original.yml`](openapi/vital-openapi-original.yml)) — sourced from [`tryVital/vital-fern-api`](https://github.com/tryVital/vital-fern-api).

## Authentication

- Standard requests use a team-level API key in the `X-Vital-API-Key` header. Keys are prefixed by environment + region:
  - Production: `pk_us_*`, `pk_eu_*`
  - Sandbox: `sk_us_*`, `sk_eu_*`
- Management-API requests use `x-vital-management-api-key` (distinct from the team key — not interchangeable).

## SDKs

Server (Fern-generated):
- Python — [`pypi.org/project/vital`](https://pypi.org/project/vital/), [`github.com/tryVital/vital-python`](https://github.com/tryVital/vital-python)
- TypeScript / Node — [`@tryvital/vital-node`](https://www.npmjs.com/package/@tryvital/vital-node), [`github.com/tryVital/vital-node`](https://github.com/tryVital/vital-node)
- Go — [`github.com/tryVital/vital-go`](https://github.com/tryVital/vital-go)
- Java — [`github.com/tryVital/vital-java`](https://github.com/tryVital/vital-java)

Mobile:
- iOS / Swift — [`github.com/tryVital/vital-ios`](https://github.com/tryVital/vital-ios)
- Android / Kotlin — [`github.com/tryVital/vital-android`](https://github.com/tryVital/vital-android)
- Flutter — [`github.com/tryVital/vital-flutter`](https://github.com/tryVital/vital-flutter)
- React Native — [`@tryvital/vital-core-react-native`](https://www.npmjs.com/package/@tryvital/vital-core-react-native), [`@tryvital/vital-devices-react-native`](https://www.npmjs.com/package/@tryvital/vital-devices-react-native), [`@tryvital/vital-health-react-native`](https://www.npmjs.com/package/@tryvital/vital-health-react-native)
- Vital Link Widget (JS) — [`@tryvital/vital-link`](https://www.npmjs.com/package/@tryvital/vital-link)
- Vital Connect (React Native sample app) — [`github.com/tryVital/vital-connect-rn`](https://github.com/tryVital/vital-connect-rn)

## Anthropic Claude alignment

Junction's normalized, schema-stable surface over wearables and labs is a strong tool surface for Anthropic Claude agents. The [`capabilities/`](capabilities/) directory packages each of Junction's business surfaces as Naftiko capabilities that can be exposed to Claude (directly via tool calling or through an MCP server) — letting an agent reason over a patient's sleep, HRV, glucose, lab biomarkers, and even place new lab orders, under appropriate medical oversight, without writing per-source adapters.

## Pricing snapshot

- **Launch** — `$0.50 / user / month`, `$300 / month` minimum, free start, no credit card. 0–1,000 users.
- **Grow** — `< $0.50 / user / month` (negotiated). 1,000+ users.
- **Scale** — custom contract; uptime SLAs, white-label, ETL pipelines, Analytics API.
- **Lab Testing** — quote-based; testkits have a typical 250-kit minimum (flexible by request); no test upcharges.

Captured in [`plans/vital-io-plans-pricing.yml`](plans/vital-io-plans-pricing.yml) (API Commons Plans 0.1) with FOCUS-aligned cost dimensions in [`finops/vital-io-finops.yml`](finops/vital-io-finops.yml) and rate-limit policy in [`rate-limits/vital-io-rate-limits.yml`](rate-limits/vital-io-rate-limits.yml).

## Repository layout

```
vital-io/
├── apis.yml                            # canonical APIs.json profile
├── README.md
├── review.yml                          # tier-1 reviewer notes
├── openapi/                            # canonical + split OpenAPI 3.1 specs
├── capabilities/                       # Naftiko capability per API surface
├── json-schema/                        # User, Provider, Sleep, Activity, HR, Lab Order, Lab Result
├── json-structure/                     # User and Lab Order lifecycle structures
├── json-ld/                            # schema.org / LOINC-aligned context
├── examples/                           # request / response pairs for headline operations
├── vocabulary/                         # normative vocabulary for the platform
├── rules/                              # Spectral ruleset enforcing Junction conventions
├── plans/                              # API Commons plans + pricing
├── rate-limits/                        # API Commons rate limits
└── finops/                             # FOCUS-aligned cost surface
```

## Reviewer

[Kin Lane](https://apievangelist.com), API Evangelist · co-founder, [Naftiko](https://naftiko.com).

Reviewed 2026-05-25.
