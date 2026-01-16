# OpenCart API Testing Project (POS and NEG)

This repository contains an API testing project for OpenCart built using Postman. I created this collection to validate how the OpenCart APIs behave when used correctly and when used incorrectly, focusing on both positive and negative scenarios.

The goal of this project was to understand the API flows end to end, not just send requests. Each test checks responses, status codes, dependencies between calls, and how the system behaves when something goes wrong. Everything was tested against a local OpenCart instance running version 4.1.0.3.

The collection covers the main API areas used during a typical shopping flow. This includes authentication, cart operations, customer data handling, shipping and payment setup, and order creation. Requests are chained using tokens and session data so the flow behaves like a real client interacting with the API.

I deliberately included negative cases such as invalid credentials, missing data, incorrect product IDs, and broken preconditions. These tests help confirm that the API fails safely and returns meaningful error responses instead of silently succeeding.

All tests are organised in a single Postman collection, with a sample environment file included. The environment file contains placeholders for base URL, API username, and API key, which can be replaced to run the tests locally. This keeps the collection reusable and easy to set up.

The collection can be executed either through the Postman interface or from the command line using Newman. When executed, all tests pass successfully on the local setup, with response times remaining low due to the localhost environment.

Test results are exported into xlsx and JSON formats to provide a clear summary of execution, individual test outcomes, and response data. This makes it easy to review results outside Postman and keeps the project transparent.

This project reflects how I approach API testing in practice: understand the workflow, test both success and failure paths, validate dependencies between calls, and document results clearly. It is intended as a learning and portfolio project rather than a production API benchmark.

Author: George Petre
GitHub: [https://github.com/GeorgeMPetre](https://github.com/GeorgeMPetre)
Portfolio: [https://georgempetre.github.io](https://georgempetre.github.io)
