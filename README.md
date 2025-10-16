 OpenCart API — IEEE 829 POS/NEG 

A complete Postman API test collection designed according to IEEE 829 testing standards, covering both positive and negative flows for OpenCart (v4.1.0.3, local instance).


Overview

This project validates the key OpenCart API endpoints through structured, executable tests.  
It ensures full functional coverage, clear test documentation, and measurable pass/fail criteria.

 Modules Included
| Module | Description |
|--------|--------------|
| Auth | Login session creation, invalid login attempts |
| Cart | Add, list, remove, invalid product operations |
| Customer | Attach customer details to API session |
| Shipping | Set address, fetch methods, set method |
| Payment | Address, methods, negative preconditions |
| Order | Create and confirm order |


Files Included
collections/
└── OpenCart API — IEEE 829 POS-NEG (George).postman_collection.json
environments/
└── OpenCart_Local_IEEE_829_SAMPLE.postman_environment.json
results/
├── OpenCart_API_Test_Summary_-_By_Test.csv
├── OpenCart_API_Test_Results.csv
└── OpenCart API — IEEE 829 POS-NEG (George).postman_test_run.json
.gitignore
README.md


Environment Configuration

A sample environment file is provided:
environments/OpenCart_Local_IEEE_829_SAMPLE.postman_environment.json

Replace the placeholders with your own credentials:
json
{
  "baseUrl": "http://localhost/opencart/upload/index.php?route=api",
  "api_username": "demo",
  "api_key": "YOUR_API_KEY_HERE"
}


How to Execute Tests
Option 1 — Postman GUI

Import the collection and environment into Postman.
Run the collection via the Collection Runner.
Review results in the Postman console.

Option 2 — Newman CLI
Run the collection directly from your terminal:

newman run "collections/OpenCart API — IEEE 829 POS-NEG (George).postman_collection.json" \
  -e "environments/OpenCart_Local_IEEE_829_SAMPLE.postman_environment.json" \
  -r cli,htmlextra \
  --reporter-htmlextra-export "reports/OpenCart_API_Report.html"

Expected output: 57 tests, 0 failures (100 % pass) 


Results Summary
Total Tests: 57
Passed: 57
Failed: 0
Avg Response Time: 50–190 ms (Localhost)

Compliance

IEEE 829 structure: ️yes
POS/NEG coverage: yes
Token chaining and dependencies: ️yes
Modular traceability: yes

License
MIT License — for educational and portfolio use.
© 2025 George Petre

Author

George Petre
Sturry, CT2 0HN, UK
george.petre23@gmail.com
georgempetre.github.io

