# Traceability Matrix — OpenCart API Testing (Postman) — POS & NEG

## How to use this file
This matrix maps API areas and behaviours to test coverage inside the Postman collection.
Because routes and request names can vary by OpenCart setup, the mapping is written by feature and intent.
Update the “Postman folder / request” column to match the exact names in your collection.

System under test: OpenCart 4.1.0.3 running locally.

---

## Legend
- POS = Positive scenario (valid usage)
- NEG = Negative scenario (invalid usage, missing data, wrong IDs, broken preconditions)

---

## Traceability matrix

| Area | Requirement / behaviour to validate | Test IDs (suggested) | Type | Postman folder / request | Evidence |
|---|---|---:|---|---|---|
| Authentication | Valid API login returns success response and usable token/session data | API-AUTH-01 | POS | Auth / POS - Login | postman_test_run.json |
| Authentication | Invalid credentials fail safely with clear error | API-AUTH-02 | NEG | Auth / NEG - Login invalid creds | postman_test_run.json |
| Authentication | Missing credentials fails safely | API-AUTH-03 | NEG | Auth / NEG - Login missing fields | postman_test_run.json |
| Cart | Add valid product to cart succeeds | API-CART-01 | POS | Cart / POS - Add item | postman_test_run.json |
| Cart | Add invalid product ID fails safely | API-CART-02 | NEG | Cart / NEG - Add invalid product | postman_test_run.json |
| Cart | Add without required preconditions fails safely | API-CART-03 | NEG | Cart / NEG - Add without auth | postman_test_run.json |
| Cart | View cart returns expected items and totals | API-CART-04 | POS | Cart / POS - Get cart | postman_test_run.json |
| Customer | Customer details can be attached to session | API-CUST-01 | POS | Customer / POS - Set customer details | postman_test_run.json |
| Shipping | Shipping method can be set when prerequisites are met | API-SHIP-01 | POS | Shipping / POS - Set shipping method | postman_test_run.json |
| Shipping | Setting shipping with missing preconditions fails safely | API-SHIP-02 | NEG | Shipping / NEG - Missing preconditions | postman_test_run.json |
| Payment | Payment method can be set when prerequisites are met | API-PAY-01 | POS | Payment / POS - Set payment method | postman_test_run.json |
| Payment | Setting payment with missing or invalid data fails safely | API-PAY-02 | NEG | Payment / NEG - Missing/invalid data | postman_test_run.json |
| Order | Order can be created successfully from a valid flow | API-ORD-01 | POS | Orders / POS - Create order | postman_test_run.json |
| Order | Order creation fails safely if prerequisites are not met | API-ORD-02 | NEG | Orders / NEG - Create order missing preconditions | postman_test_run.json |

**Note:**  
A total of **21 Postman tests** were executed.  
Multiple tests may validate a single behaviour (for example, cart and order flows),
so this matrix is intentionally maintained at **feature level** rather than listing
every individual request.

---

## Notes
- This project intentionally includes NEG tests like invalid credentials, missing data, incorrect product IDs, and broken preconditions to confirm safe failure behaviour.
- If you rename folders/requests, keep this file updated so the repo stays easy to audit.
