# bft-api.lab
bft-api.lab is the package name for the API lab.


# api-lab

bft-api.lab is the repository for Billfold Technology schematics based business particles and nucleus files.
|
| Command | Description |
| --- | --- |
|  Build file name: | 'bft-filename_api' |
|  Repository: | [api-lab](https://github.com/Billfold-Technologies/api-lab/) |
|  Access token: | OAuth |
|  Nucleus class: | api.lab |
|  Deployment name: | `npm install` api-lab |
|  [Order](https://github.com/Billfold-Technologies/Technical-Orders) | nucleus type particle |
|  Node Home: | 'sbm-api-lab/filename' |

The nucleus class establishes and sets the CLI. The motherboard hosts seven class series and their business particles. The classes naming convention follows the build filename. A directory of classes may be found here:
| Nucleus Class | Description
| --- | --- |
|- [schematic-lab](https://github.com/Billfold-Technologies/schematic-lab) |The repository for schematic calibration.
|- [trade-engine-lab](https://github.com/Billfold-Technologies/trade-engine-lab) |The repository for trade data and technical analysis.
|- [api-lab](https://github.com/Billfold-Technologies/api-lab) | The repository for store API developers.
|- [plugin-lab](https://github.com/Billfold-Technologies/plugin-lab) | The repository for executable developers.
|- [library-lab](https://github.com/Billfold-Technologies/library-lab) | The repository for personal business machine script developers.
|- [electroplate-lab](https://github.com/Billfold-Technologies/electroplate-lab) | The repository for smart contract testing and CI-CD automation.
|- [snippet-lab](https://github.com/Billfold-Technologies/snippet-lab) | The repository for Billfold Technology UI content and design.
|     |

| Command | Description |
| --- | --- |
| pbm_api show | List all new or modified files |
| pbm_api execute_new | Plan and create new executable to be staged |
| pbm_api launch | App launcher
| pbm_api package | Toolset for packaging personal business machines |
| pbm_api attribution | Shows all schematic authors and events |
| pbm_api test_pipeline | Set up automation test drive event |
| pbm_api set_platform | Embarcation for platform system |

---

# openapi.json — DealMaker API Outline

> Source: [`openapi.json`](./openapi.json) — OpenAPI Specification 3.0.0

## Overview

| Field | Value |
| --- | --- |
| API Name | DealMaker API |
| Specification | OpenAPI 3.0.0 |
| Base URL | `https://api.dealmaker.tech` |
| Authentication | OAuth 2.0 — Client Credentials flow |
| Token Endpoint | `https://app.dealmaker.tech/oauth/token` |
| Libraries | JavaScript, Ruby |

## Authentication

The API uses **OAuth 2.0 Client Credentials** flow. An OAuth application must first be created in the DealMaker portal to obtain a `client_id` and `client_secret`. These are exchanged for a bearer token, which is then passed as an `Authorization` header on every request.

**OAuth Scopes:**

| Scope | Permission |
| --- | --- |
| `deals.read` | Read deal information |
| `deals.write` | Write information to deals |
| `companies.read` | Read company information |
| `companies.write` | Write information to companies |
| `deals.investors.read` | Read information from investors |
| `deals.investors.write` | Write information to investors |
| `webhooks.read` | Read information from webhooks |
| `webhooks.write` | Write information to webhooks |

## Endpoint Groups

### Deals (`/deals`)

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/deals` | List available deals |
| GET | `/deals/{id}` | Get deal by Deal ID |
| GET | `/deals/{id}/summary` | Get deal summary |
| GET | `/deals/{id}/incentive_plan` | Get incentive plan by deal id |
| PUT | `/deals/{id}/script_tag_environment` | Update script tag environment |
| POST | `/deal_setups` | Create deal setup |

### Investors (`/deals/{id}/investors`)

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/deals/{id}/investors` | List deal investors |
| POST | `/deals/{id}/investors` | Create a deal investor |
| GET | `/deals/{id}/investors/{investor_id}` | Get a deal investor by id |
| PUT | `/deals/{id}/investors/{investor_id}` | Update a deal investor |
| PATCH | `/deals/{id}/investors/{investor_id}` | Patch a deal investor |
| GET | `/deals/{id}/investors/{investor_id}/otp_access_link` | Get OTP access link |
| GET | `/deals/{id}/investors/{investor_id}/incentive_plan` | Get investor incentive plan |
| POST | `/deals/{id}/investors/{investor_id}/add_document` | Add document for investor |
| DELETE | `/deals/{id}/investors/{investor_id}/delete_document/{document_id}` | Delete document |
| POST | `/deals/{id}/investors/{investor_id}/add_506c_document` | Add 506c document |
| POST | `/deals/{id}/investors/bulk_upload` | Bulk upload investors |
| POST | `/deals/{id}/investors/{investor_id}/edit_tags` | Edit investor tags |
| GET | `/deals/{id}/investors/{investor_id}/search_entities` | Get search entities |
| POST | `/deals/{id}/investors/{investor_id}/background_checks/run` | Run background check |
| GET | `/deals/{id}/investors/{investor_id}/background_checks/{search_entity_id}/enforcements` | Get enforcements |

### Investor Profiles (`/investor_profiles`)

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/investor_profiles` | Get list of InvestorProfiles |
| GET | `/investor_profiles/{deal_id}` | Get InvestorProfiles for a deal |
| GET | `/investor_profiles/profile/{id}` | Get an investor profile by id |
| DELETE | `/investor_profiles/{type}/{id}` | Delete investor profile |
| POST | `/investor_profiles/corporations` | Create corporation investor profile |
| PATCH | `/investor_profiles/corporations/{investor_profile_id}` | Patch corporation investor profile |
| POST | `/investor_profiles/joints` | Create joint investor profile |
| PATCH | `/investor_profiles/joints/{investor_profile_id}` | Patch joint investor profile |
| POST | `/investor_profiles/individuals` | Create individual investor profile |
| PATCH | `/investor_profiles/individuals/{investor_profile_id}` | Patch individual investor profile |
| POST | `/investor_profiles/trusts` | Create trust investor profile |
| PATCH | `/investor_profiles/trusts/{investor_profile_id}` | Patch trust investor profile |
| POST | `/investor_profiles/managed` | Create managed investor profile |

### Companies (`/companies`)

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/companies` | Get list of Companies |
| POST | `/companies` | Create new company |
| GET | `/companies/{id}` | Get a Company |
| GET | `/companies/{id}/shareholder_ledger` | Get shareholder ledger |
| GET | `/companies/{id}/shareholders` | Get shareholders list |
| GET | `/companies/{id}/shareholders/tags` | Get shareholders grouped by tags |
| POST | `/companies/{company_id}/shareholders/{shareholder_id}/actions` | Create shareholder action |
| POST | `/companies/{id}/shareholders/{shareholder_id}/send_portal_invite` | Send portal invite |
| GET | `/companies/{company_id}/portal/dividends` | Return dividends |
| GET | `/companies/{id}/documents/bulk_uploads` | Return bulk uploads |
| POST | `/companies/{id}/documents/bulk_uploads` | Create bulk upload record |
| GET | `/companies/{id}/news_releases/email_templates` | Get list of email templates |
| POST | `/companies/{id}/news_releases/email_template` | Create email template |
| GET | `/companies/{id}/members/bulk_uploads` | Get member bulk uploads |
| POST | `/companies/{id}/members/bulk_uploads` | Create member bulk upload |

### Incentive Plans

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/deals/{id}/incentive_plans/time` | Get incentive plans by deal id |
| POST | `/deals/{id}/incentive_plans` | Create incentive plan |
| PATCH | `/deals/{id}/incentive_plans/{incentive_plan_id}` | Update incentive plan |

### Payments & Onboarding

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/deals/{deal_id}/payment_onboarding/questionnaire/initial_questions` | Initial questions |
| GET | `/deals/{deal_id}/payment_onboarding/questionnaire/payout_account_details/data` | Payout account data |
| POST | `/deals/{deal_id}/payment_onboarding/questionnaire/payout_account_details/submit` | Submit payout details |
| GET | `/deals/{deal_id}/payment_onboarding/questionnaire/digital_payments_connection/data` | Digital payments data |
| POST | `/deals/{deal_id}/payment_onboarding/questionnaire/qualification_questionnaire/submit` | Submit qualification |
| POST | `/deals/{deal_id}/payment_onboarding/questionnaire/qualification_questionnaire/response/submit` | Submit qualification response |
| GET | `/deals/{id}/investors/{investor_id}/payments/express_wire/instructions` | Get express wire instructions |
| GET | `/deals/{id}/investors/payments/express_wire/instructions` | Get all express wire instructions |

### Webhooks (`/webhooks`)

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/webhooks` | List webhooks |
| POST | `/webhooks` | Create webhook |
| GET | `/webhooks/{id}` | Get webhook |
| DELETE | `/webhooks/{id}` | Delete webhook |
| GET | `/webhooks/deals/search` | Search webhook deals |
| GET | `/webhooks/deal/{id}` | Get webhook deal |
| GET | `/webhooks/security_token` | Get security token |

### Users (`/users`)

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/users/investments` | Get investments for a user |
| GET | `/users/{id}` | Get user by User ID |
| PUT | `/users/{id}/update_password` | Update user password |
| GET | `/users/accessible_companies` | Get accessible companies |

### Utility

| Method | Path | Summary |
| --- | --- | --- |
| GET | `/country/states` | Returns all valid countries and states |
| POST | `/uploads/generate_url` | Create a presigned S3 URL |
| POST | `/custom_emails/get_access_token` | Generate Beefree editor authorization token |

## Data Models

The API exposes **89 schemas** across the following domains:

| Domain | Key Schemas |
| --- | --- |
| Deal | `V1_Entities_Deal`, `V1_Entities_Deals`, `V1_Entities_DealSetup`, `V1_Entities_DealIssuer`, `V1_Entities_DealFundingMetrics` |
| Investor | `V1_Entities_Investor`, `V1_Entities_Investors`, `V1_Entities_InvestorUser`, `V1_Entities_SubscriptionAgreement` |
| Investor Profile | `V1_Entities_InvestorProfile_Individual`, `V1_Entities_InvestorProfile_Joint`, `V1_Entities_InvestorProfile_Corporation`, `V1_Entities_InvestorProfile_Trust`, `V1_Entities_InvestorProfile_Managed` |
| Company | `V1_Entities_Company`, `V1_Entities_Shareholder`, `V1_Entities_ShareholderLedger`, `V1_Entities_EmailTemplate` |
| Payments | `V1_Entities_ExpressWireInstruction`, `V1_Entities_Payments_SelfServeOnboarding_*`, `V1_Entities_Dividends` |
| Webhooks | `V1_Entities_Webhooks_Deal`, `V1_Entities_Webhooks_Subscription`, `V1_Entities_Webhooks_SecurityToken` |
| Utilities | `V1_Entities_Address`, `V1_Entities_Country`, `V1_Entities_User`, `V1_Entities_BulkUpload` |

---

# Upgrade & Update Suggestions Using Billfold Technologies Business Machines

The following suggestions outline how to evolve the `openapi.json` schema and API integrations using the Billfold Technologies personal business machine (`pbm_api`) toolchain.

## 1. Bump OpenAPI Version to 3.1.0

The current spec uses OpenAPI **3.0.0**. Upgrading to **3.1.0** provides full JSON Schema alignment, `webhooks` as a first-class object, and improved `null`-type support.

**Action:** Use `pbm_api execute_new` to scaffold the upgrade schematic and `pbm_api test_pipeline` to validate the migrated spec against the DealMaker endpoints before publishing.

## 2. Populate Missing `info` Fields

The `info.version` field is currently empty (`""`). Adding a semantic version and contact/license metadata improves developer experience and toolchain compatibility.

**Action:** Use `pbm_api show` to identify modified spec fields, then use `schematic-lab` to calibrate and version the updated `openapi.json`.

## 3. Apply Security at the Operation Level

The spec defines an `oauth` security scheme but does not apply global or per-operation `security` requirements. Adding explicit `security` declarations to each endpoint enforces least-privilege scope controls.

**Action:** Use `pbm_api execute_new` to generate the security-annotation particle, and validate with `electroplate-lab` CI-CD automation.

## 4. Standardize Error Responses

Many endpoints are missing standardized `4xx`/`5xx` error response schemas. Defining a shared `V1_Entities_Error` schema and referencing it across all operations improves client-side error handling.

**Action:** Add the shared error schema via `schematic-lab`, register it in `openapi.json`, and verify coverage with `pbm_api test_pipeline`.

## 5. Integrate Webhook Subscriptions as OpenAPI Webhooks

The current spec includes webhook-related endpoints under `/webhooks` as regular REST paths. OpenAPI 3.1.0 supports a dedicated `webhooks` section that better documents push-based event contracts.

**Action:** Use `electroplate-lab` to author the webhook event schemas and `pbm_api set_platform` to register the webhook delivery platform target.

## 6. Add SDK Generation via `library-lab`

The spec is compatible with OpenAPI code-generation tools (e.g., `openapi-generator`). Generating typed client SDKs in JavaScript and Ruby aligns with the two languages mentioned in the spec.

**Action:** Use `library-lab` personal business machine scripts to automate SDK generation and `pbm_api package` to bundle and distribute the SDKs.

## 7. Extend Investor Profile Schemas for Compliance

The `V1_Entities_InvestorProfile_*` schemas cover individual, joint, corporation, trust, and managed profiles. Adding validation rules (e.g., `minLength`, `pattern`, `enum`) to fields used in KYC/AML workflows ensures compliance data quality at the schema level.

**Action:** Use `schematic-lab` for calibration and `pbm_api test_pipeline` to run compliance validation scenarios.

## 8. Document Payment Onboarding Questionnaire Flow

The payment onboarding endpoints (`/deals/{deal_id}/payment_onboarding/questionnaire/*`) currently lack detailed flow documentation. Adding `x-` extension fields or a dedicated tag group with a description improves developer onboarding.

**Action:** Use `snippet-lab` to author the UI content and flow diagrams, and `pbm_api attribution` to track schematic authorship across questionnaire endpoints.
