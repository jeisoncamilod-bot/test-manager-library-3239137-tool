# API Interaction Guide

## 1. Purpose

This document defines the expected interaction between the Manager Library demonstration data seeder and the backend API.

The purpose is to ensure that demonstration data is submitted through the API and follows the official project specifications.

## 2. General Principles

The demonstration data seeder should:

- Use the documented API endpoints.
- Follow the official API contract.
- Respect authentication and authorization requirements.
- Submit data using the expected request formats.
- Handle successful responses and errors.
- Respect the backend's validation rules and business constraints.
- Avoid direct database access.

## 3. API Base URL

The seeder should use a configurable API base URL.

The actual URL depends on the execution environment and must be documented once the environment configuration is established.

The base URL should not be duplicated unnecessarily throughout the tool's configuration.

## 4. Authentication

The seeder must follow the authentication requirements defined by the official API contract.

If an endpoint requires authentication, the request must include a valid access token in the required format.

Credentials and access tokens must not be committed to the repository or printed in logs.

The authentication mechanism must be verified against the official API specification before implementation.

## 5. Request Format

Requests must follow the API contract, including:

- Correct endpoint paths.
- Supported HTTP methods.
- Appropriate request headers.
- JSON request bodies where required.
- Valid field names and data types.

The seeder must not assume that an endpoint or field exists without confirming it in the official documentation.

## 6. Data Submission

The seeder may prepare demonstration data for entities supported by the API, such as books, categories, and members, provided the corresponding operations are documented and available.

Data must comply with the required fields, relationships, uniqueness constraints, and business rules.

Operations involving loans must respect the rules for availability, overdue loans, loan limits, and book returns defined in the project specifications.

## 7. Response Handling

The seeder should distinguish between successful responses and failed requests.

It should handle documented HTTP status codes, including:

| Status | Meaning |
|---|---|
| `200` | The request succeeded. |
| `201` | A resource was created successfully. |
| `401` | Authentication is missing or invalid. |
| `403` | The operation is not authorized. |
| `404` | The requested resource was not found. |
| `409` | The request conflicts with an existing state or business rule. |
| `422` | The submitted data failed validation. |

The actual response codes must be checked against the specific endpoint definitions in the official API contract.

## 8. Error Reporting

When a request fails, the tool should record enough information to identify the problem.

Error reporting should include the affected operation, relevant status code, and a safe description of the failure.

Logs must not expose passwords, access tokens, or other sensitive information.

## 9. Data Integrity

The seeder must use the API as the entry point for data submission.

It must not bypass backend validation, modify database records directly, or ignore business constraints.

Repeated requests must be handled carefully to avoid unintended duplicate records or inconsistent demonstration data.

## 10. Implementation Status

This document describes the expected interaction between the demonstration data seeder and the backend API.

The actual endpoints, configuration variables, request examples, and supported operations must be verified against the official API contract and the implemented backend.

This document does not confirm that the seeder or its API interactions have been implemented.

## 11. Related Documentation

- `README.md`: Repository purpose and scope.
- `seeder-overview.md`: Intended responsibilities of the demonstration data seeder.
- `demo-data-guidelines.md`: Guidelines for preparing demonstration data.
- `seeder-usage-guide.md`: Expected usage and troubleshooting.
- `test-manager-library-3239137-docs`: Official specifications and API contract.
