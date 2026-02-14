# Test Plan — OpenCart API Testing (Postman) — POS & NEG

## 1. Purpose
This test plan explains how the OpenCart API is tested using a Postman collection that covers both positive and negative scenarios. The main goal is to validate end-to-end API flows, not just isolated requests.

## 2. Project overview
- Type: API testing project
- Tooling: Postman collection + Postman environment
- System under test: OpenCart running locally (XAMPP), version 4.1.0.3
- Focus: workflow-based API testing (dependencies between calls, tokens/session data, safe failure on invalid usage)

## 3. Objectives
- Confirm core shopping-flow API behaviour works in a realistic sequence (auth → cart → customer/shipping/payment → order).
- Validate response basics consistently:
  - status code
  - response structure/content (key fields)
  - dependency handling (tokens, sessions, IDs)
- Prove negative scenarios fail safely (missing/invalid input, broken preconditions, wrong IDs, invalid credentials).

## 4. Scope

### In scope
Functional API validation for the main areas used in a typical shopping flow:
- Authentication
- Cart operations
- Customer data handling
- Shipping setup
- Payment setup
- Order creation

### Out of scope
- UI validation
- Performance/load testing (covered in a separate project)
- Security pentesting (beyond basic NEG cases like invalid auth, missing fields, wrong IDs)
- Third-party integrations (payments/shipping providers) unless mocked by the local setup

## 5. Test approach
- Single Postman collection, organised by feature area.
- Requests are chained to behave like a real client (token/session/IDs carried forward).
- Each request includes assertions for:
  - expected status code
  - expected schema/fields
  - expected error messages for negative flows (when applicable)
- Negative testing is deliberate and documented, not accidental.

## 6. Test items (high level)
- Postman collection JSON: `OpenCart API — IEEE 829 POS-NEG (George).postman_collection.json`
- Postman environment JSON: `OpenCart Local — IEEE 829 (George).postman_environment.json`
- Example run output: `OpenCart API — IEEE 829 POS-NEG (George).postman_test_run.json`

## 7. Test environment
- Local OpenCart instance (XAMPP on Windows)
- OpenCart version: 4.1.0.3
- Postman (GUI) or Newman (CLI)
- Environment variables (placeholders in repo) include:
  - base URL
  - API username
  - API key

## 8. Entry criteria
- OpenCart is running locally and reachable via the configured base URL
- API credentials are available and added to the Postman environment
- Test data baseline is prepared (at least one valid product, stock available, etc.)
- Collection imports successfully and variables resolve correctly

## 9. Exit criteria
- All POS scenarios pass for the supported flow in the local environment
- NEG scenarios behave as expected (fail safely and consistently)
- A test run export exists (JSON) and summary is updated in `TEST_SUMMARY.md`

## 10. Deliverables
- This test plan (`TEST_PLAN.md`)
- Roadmap (`TEST_ROADMAP.md`)
- Traceability (`TRACEABILITY.md`)
- Test summary (`TEST_SUMMARY.md`)
- Postman collection + environment + run export already in the repo

## 11. Roles and responsibilities
- Author / Tester: George Petre
  - Design and maintain collection
  - Execute test runs (Postman/Newman)
  - Review results and update summary/traceability
  - Raise defects as findings (documented as expected behaviour for NEG scenarios)

## 12. Risks and limitations
- Localhost results are not production-like (network latency, server sizing, caching, DB size).
- Data/state can affect outcomes (existing carts/orders, product stock changes).
- API route differences can exist between OpenCart setups; variables and routes must match the local configuration.

## 13. Reporting
- Primary evidence: exported Postman run JSON already included in the repo.
- Optional: Newman CLI output / HTML report (if added later).
- Summary results are captured in `TEST_SUMMARY.md`.
