# Vital (vital-io)

Vital (now operating as Junction, formerly tryVital) is a health-data API platform that gives digital-health, virtual-care, diagnostics, wellness, and EHR/EMR builders a single integration to wearable-device data and nationwide lab testing. Connect 300+ wearables and health devices — Apple HealthKit, Android Health Connect, Oura, Whoop, Garmin, Fitbit, Withings, Dexcom, Freestyle Libre, Withings, Polar, and the rest — through the Vital Link Widget; ingest normalized daily summaries and per-sample timeseries for sleep, activity, body, workouts, heart rate, HRV, glucose, blood pressure, SpO2, ECG, and menstrual cycle; order at-home testkits, at-home phlebotomy, walk-in / Patient Service Center lab collection, and on-site collection across all 50 U.S. states; retrieve structured biomarker results; and run Junction Sense continuous queries to turn raw data into clinically actionable insights. Backed by SOC 2 Type 2, ISO 27001, GDPR-ready, and HIPAA-compliant infrastructure with both US and EU regional deployments.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vital-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vital-io/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Health Data
- Wearables
- Lab Testing
- Digital Health
- Healthtech
- Healthcare
- HIPAA
- HealthKit
- Health Connect
- EHR
- EMR
- Biomarkers
- Diagnostics
- Continuous Glucose Monitoring
- Sleep
- Activity
- Heart Rate
- Webhooks
- Phlebotomy
- Lab Orders

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Vital Users API

Create, list, get, update, and delete end users on the Junction (Vital) platform. Each user represents a person whose wearable, device, and lab data is ingested under your team. Manage user demographics, user insurance details, sign-in tokens for the Junction app, portal URLs, user-resolve by client_user_id, refresh of all connected providers for a user, listing of a user's connections, and soft-delete / undo-delete flows.

- **Human URL:** [https://docs.junction.com/api-details/junction-api](https://docs.junction.com/api-details/junction-api)
- **Base URL:** `https://api.us.junction.com`

#### Tags

- Users
- User Management
- Demographics
- Insurance
- Sign-In Tokens

#### Properties

- [Documentation](https://docs.junction.com/api-details/junction-api)
- [OpenAPI](openapi/vital-users-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vital-users-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-users-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/vital-user-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/vital-create-user-example.json)

### Vital Link API

Connect end users to their wearable and health-data providers. Generate Link tokens that drive the Vital Link Widget, complete OAuth / email / password / demo provider flows, deregister a connection, complete MFA for password providers, run bulk operations (export, import, pause, historical-pull trigger), and retrieve the catalog of 300+ supported providers — Fitbit, Garmin, Oura, Whoop, Withings, Polar, Strava, Dexcom, Freestyle Libre, Apple HealthKit, Android Health Connect, Samsung Health, and the rest.

- **Human URL:** [https://docs.junction.com/wearables/providers/introduction](https://docs.junction.com/wearables/providers/introduction)
- **Base URL:** `https://api.us.junction.com`

#### Tags

- Link
- Provider Connections
- OAuth
- Wearables
- Bulk Operations

#### Properties

- [Documentation](https://docs.junction.com/wearables/providers/introduction)
- [OpenAPI](openapi/vital-link-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vital-link-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-link-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/vital-provider-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/vital-link-token-example.json)

### Vital Wearables Data API

Read normalized wearable-device data across 300+ supported devices. Daily summary endpoints cover sleep, sleep cycles, activity, body composition, workouts, menstrual cycle, ECG, meals, and the user profile. Per-sample timeseries endpoints cover heart rate, heart-rate variability, blood pressure, blood oxygen, glucose (including continuous-glucose monitoring), respiratory rate, body temperature, basal body temperature, distance, steps, floors climbed, active and basal calories, stress level, sleep stream, workout stream, and workout-specific metrics (swimming stroke, distance, duration). All data is normalized to a single schema regardless of source provider.

- **Human URL:** [https://docs.junction.com/api-details/junction-api](https://docs.junction.com/api-details/junction-api)
- **Base URL:** `https://api.us.junction.com`

#### Tags

- Wearables
- Timeseries
- Summary
- Sleep
- Activity
- Body
- Workouts
- Heart Rate
- HRV
- Glucose
- Blood Pressure
- SpO2
- ECG

#### Properties

- [Documentation](https://docs.junction.com/api-details/junction-api)
- [OpenAPI](openapi/vital-wearables-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vital-wearables-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-wearables-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/vital-sleep-summary-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/vital-activity-summary-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/vital-heart-rate-timeseries-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/vital-sleep-summary-example.json)
- [Example](examples/vital-heart-rate-timeseries-example.json)

### Vital Lab Testing API

Order, fulfill, and retrieve lab tests across a nationwide US lab network spanning all 50 states including NY, NJ, and RI. Covers at-home testkits, at-home phlebotomy, walk-in / Patient Service Center collection, and on-site collection. Endpoints handle order creation and lifecycle (create, get, update, cancel, import, register, simulate), appointment management (availability, booking, cancellation, rescheduling for both phlebotomy and PSC), order transactions, results (JSON and PDF), the lab-test compendium (search + convert), payor and insurance/diagnosis search, ABN forms, requisition and label PDFs, collection instructions, and team lab accounts.

- **Human URL:** [https://docs.junction.com/api-details/junction-api](https://docs.junction.com/api-details/junction-api)
- **Base URL:** `https://api.us.junction.com`

#### Tags

- Lab Testing
- Lab Orders
- Biomarkers
- Phlebotomy
- Testkits
- PSC
- Insurance
- Diagnosis
- Compendium

#### Properties

- [Documentation](https://docs.junction.com/api-details/junction-api)
- [OpenAPI](openapi/vital-lab-testing-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vital-lab-testing-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-lab-testing-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/vital-lab-order-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/vital-lab-result-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/vital-create-order-example.json)
- [Example](examples/vital-lab-result-example.json)

### Vital Lab Report Parser API

Submit existing lab-result PDFs to be parsed and normalized into structured biomarker results. Create a lab-report parser job, then poll for status and the parsed result set — useful for back-loading historical patient records or for normalizing results from external labs into the Junction biomarker schema.

- **Human URL:** [https://docs.junction.com/api-details/junction-api](https://docs.junction.com/api-details/junction-api)
- **Base URL:** `https://api.us.junction.com`

#### Tags

- Lab Reports
- PDF Parsing
- Biomarkers
- Document AI

#### Properties

- [Documentation](https://docs.junction.com/api-details/junction-api)
- [OpenAPI](openapi/vital-lab-report-parser-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vital-lab-report-parser-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-lab-report-parser-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vital Sense API

Junction Sense — query and aggregation API for per-user health data. Run on-demand aggregate queries across a user's ingested wearable and lab data, fetch the result table for a defined continuous query, and read continuous-query task-execution history. Sense turns raw ingest into clinically meaningful metrics (sleep debt, HRV trends, glucose variability, etc.) without you owning the aggregation infrastructure.

- **Human URL:** [https://docs.junction.com/api-details/junction-api](https://docs.junction.com/api-details/junction-api)
- **Base URL:** `https://api.us.junction.com`

#### Tags

- Sense
- Continuous Queries
- Aggregation
- Analytics
- Insights

#### Properties

- [Documentation](https://docs.junction.com/api-details/junction-api)
- [OpenAPI](openapi/vital-sense-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vital-sense-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-sense-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vital Team API

Read and administer team-level resources on the Junction (Vital) platform. Get team metadata, search team users by uuid or client_user_id, fetch the Svix webhook portal URL for managing webhook subscriptions, and introspect team-level historical pulls and per-resource availability for your team's users.

- **Human URL:** [https://docs.junction.com/api-details/junction-management-api](https://docs.junction.com/api-details/junction-management-api)
- **Base URL:** `https://api.us.junction.com`

#### Tags

- Team
- Administration
- Webhooks
- Introspection
- Configuration

#### Properties

- [Documentation](https://docs.junction.com/api-details/junction-management-api)
- [OpenAPI](openapi/vital-team-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vital-team-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-team-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vital Management API

Programmatically manage all Junction regional and global resources for your organization. Authenticated with a separate x-vital-management-api-key, this API governs organizations, teams (create, update, delete, list), team and management API keys, team members and invitations, custom OAuth credentials, data-pull preferences, ETL pipeline configuration (Azure Event Hubs, Google Cloud Pub/Sub, RabbitMQ), webhook subscriptions (create, list, rotate secret, update headers, patch, delete), scope requirements, physician assignments, and lab-account team assignments.

- **Human URL:** [https://docs.junction.com/api-details/junction-management-api](https://docs.junction.com/api-details/junction-management-api)
- **Base URL:** `https://api.us.junction.com`

#### Tags

- Management
- Organizations
- Teams
- API Keys
- ETL Pipelines
- Webhooks

#### Properties

- [Documentation](https://docs.junction.com/api-details/junction-management-api)
- [Postman Collection](collections/vital-lab-report-parser-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-lab-report-parser-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vital-lab-testing-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-lab-testing-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vital-link-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-link-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vital-openapi-original.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-openapi-original.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vital-sense-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-sense-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vital-team-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-team-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vital-users-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-users-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vital-wearables-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vital-wearables-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Portal](https://www.junction.com)
- [Documentation](https://docs.junction.com)
- [API Reference](https://docs.junction.com/api-details/junction-api)
- [Quickstart](https://docs.junction.com/home/quickstart)
- [Getting Started](https://docs.junction.com/home/welcome)
- [Console](https://app.junction.com)
- [Sign Up](https://app.junction.com/signup)
- [Sign In](https://app.junction.com/login)
- [Pricing](https://www.tryvital.com/pricing)
- [Status Page](https://status.tryvital.io)
- [Changelog](https://docs.junction.com/home/api/changelog)
- [Rate Limiting](https://docs.junction.com/home/rate-limiting)
- [Documentation](https://docs.junction.com/home/regions)
- [Authentication](https://docs.junction.com/home/authentication)
- [Webhooks](https://docs.junction.com/webhooks/introduction)
- [Documentation](https://docs.junction.com/wearables/providers/introduction)
- [Security](https://docs.junction.com/home/security)
- [GitHub Organization](https://github.com/tryVital)
- [GitHub Repository](https://github.com/tryVital/vital-fern-api)
- [GitHub Repository](https://github.com/tryVital/docs)
- [Sample App](https://github.com/tryVital/quickstart)
- [OpenAPI](https://raw.githubusercontent.com/tryVital/vital-fern-api/main/fern/openapi/openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/vital-openapi-original.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/vital-openapi-original.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [SDK](https://www.npmjs.com/package/@tryvital/vital-node)
- [SDK](https://www.npmjs.com/package/@tryvital/vital-link)
- [SDK](https://www.npmjs.com/package/@tryvital/vital-core-react-native)
- [SDK](https://www.npmjs.com/package/@tryvital/vital-devices-react-native)
- [SDK](https://www.npmjs.com/package/@tryvital/vital-health-react-native)
- [SDK](https://pypi.org/project/vital/)
- [SDK](https://github.com/tryVital/vital-python)
- [SDK](https://github.com/tryVital/vital-node)
- [SDK](https://github.com/tryVital/vital-go)
- [SDK](https://github.com/tryVital/vital-java)
- [SDK](https://github.com/tryVital/vital-ios)
- [SDK](https://github.com/tryVital/vital-android)
- [SDK](https://github.com/tryVital/vital-flutter)
- [SDK](https://github.com/tryVital/vital-react-native)
- [Sample App](https://github.com/tryVital/vital-connect-rn)
- [Spectral Rules](rules/vital-rules.yml)
- [Vocabulary](vocabulary/vital-io-vocabulary.yml)
- [J S O N- L D](json-ld/vital-io-context.jsonld)
- [Plans](plans/vital-io-plans-pricing.yml)
- [Rate Limits](rate-limits/vital-io-rate-limits.yml)
- [Fin Ops](finops/vital-io-finops.yml)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [Solutions](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
