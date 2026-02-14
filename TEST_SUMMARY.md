# Test Summary — OpenCart API Testing (Postman) — POS & NEG

## 1. What was tested
This repository contains API tests for OpenCart using a Postman collection focused on both positive and negative scenarios, executed against a local OpenCart instance (XAMPP), version 4.1.0.3.

Coverage follows a typical shopping flow:
- authentication
- cart operations
- customer data handling
- shipping and payment setup
- order creation

## 2. Test execution details
- Tool: Postman (manual run) / Newman (optional CLI)
- Collection: `OpenCart API — IEEE 829 POS-NEG (George).postman_collection.json`
- Environment: `OpenCart Local — IEEE 829 (George).postman_environment.json`
- Evidence file: `OpenCart API — IEEE 829 POS-NEG (George).postman_test_run.json`

## 3. Environment
- Host: localhost (local machine)
- Platform: OpenCart 4.1.0.3 
- Notes: This is a controlled local setup, so response times are naturally low compared to a real hosted environment.

## 4. Results (fill in after each run)
> Keep these numbers honest and taken from the latest run export.

- Execution date:
- Total requests executed:
- Total assertions:
- Passed:
- Failed:
- Skipped:

### Key observations
- POS flow behaviour:
  - (Add short notes from the run, e.g. “Auth token reused correctly”, “Cart totals consistent”, etc.)
- NEG flow behaviour:
  - (Add short notes, e.g. “Invalid credentials rejected”, “Missing required fields returned clear error”, etc.)

## 5. Known limitations
- Results are from a local environment (XAMPP). This does not represent:
  - production network latency
  - real server sizing
  - large database / high traffic conditions
- Test data/state can impact repeatability (existing cart/orders, product stock changes).

## 6. Issues / defects found

No defects were identified during this test execution.

All 21 tests passed successfully, and no functional or performance issues
were observed in the tested scope.

## 7. Conclusion
This Postman suite validates end-to-end OpenCart API behaviour for both valid and invalid usage, confirming not only successful flows but also safe failure responses when inputs or preconditions are wrong.

