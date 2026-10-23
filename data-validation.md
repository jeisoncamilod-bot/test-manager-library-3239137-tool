# Demonstration Data Validation

## 1. Purpose

This document defines the validation guidelines for demonstration data prepared by the Manager Library data seeder.

The objective is to ensure that sample data follows the official project specifications and is accepted by the backend API when it satisfies the applicable validation rules.

## 2. General Validation Principles

Demonstration data should:

- Follow the official data model.
- Include all required fields.
- Use the correct data types and formats.
- Respect uniqueness constraints.
- Reference existing related records.
- Comply with the documented business rules.
- Be submitted through the backend API.

The backend remains responsible for enforcing the application's authoritative validation rules.

## 3. Book Data

Book demonstration records should comply with the following documented requirements:

- Titles and authors must contain valid values.
- ISBN values must contain 13 digits.
- Active books must not share the same ISBN.
- The total number of copies must be at least one.
- Available copies must not be negative or exceed the total number of copies.
- Cover images, when supported, must use JPG or PNG format and must not exceed 2 MB.

The exact required fields must be confirmed against the official API contract.

## 4. Category Data

Category references must correspond to categories supported by the official project specifications.

The seeder should not invent additional categories if the project defines a fixed set of categories.

Existing category records should be reused when appropriate.

## 5. Member Data

Member demonstration records must:

- Include the required member information.
- Use valid document numbers.
- Respect the uniqueness requirement for member document numbers.
- Follow the validation rules defined by the backend API.

Demonstration records should use fictional information rather than unnecessary real personal data.

## 6. User Data

User-related data must respect the documented authorization model.

The seeder must not bypass user provisioning rules or create administrator accounts through an unsupported operation.

Authentication credentials must not be stored in demonstration datasets or exposed in logs.

## 7. Loan Data

Loan demonstration data must respect the documented loan rules:

- A loan belongs to one member.
- A loan contains between one and three loan items.
- The same book must not appear more than once in a single loan.
- Each loan item must reference an existing book.
- A member must not exceed the maximum of three unreturned books.
- Members with overdue loans must not receive new loans when prohibited by the business rules.
- The due date is calculated as 14 days after the loan date.
- Book availability must be updated through the backend's loan operations.

The seeder must not create loan records by bypassing the API's validation or stock management logic.

## 8. Invalid Data

The seeder should identify and report invalid data clearly.

When the API rejects a request, the tool should retain enough non-sensitive information to identify the affected record and the validation failure.

Invalid records must not be treated as successfully created.

## 9. Data Consistency

Demonstration data must preserve the relationships between books, categories, members, users, and loans.

The seeder should avoid:

- Duplicate records where uniqueness is required.
- References to nonexistent records.
- Negative inventory values.
- Inconsistent loan and return information.
- Data that violates documented business rules.

## 10. Verification

Validation should be checked against:

1. The official Manager Library specifications.
2. The API contract.
3. The backend's actual validation responses.
4. The resulting data returned by supported API operations.

The implementation must be tested before claiming that all validation requirements are satisfied.

## 11. Implementation Status

This document summarizes validation guidelines derived from the intended Manager Library data model and business rules.

It does not confirm that validation logic has been implemented in the seeder. The backend API remains the authoritative source for enforcing application rules.

## 12. Related Documentation

- `README.md`: Repository purpose and scope.
- `seeder-overview.md`: Overview of the demonstration data seeder.
- `demo-data-guidelines.md`: Demonstration data preparation guidelines.
- `seeder-usage-guide.md`: Expected usage process.
- `api-interaction.md`: Expected interaction with the backend API.
- `test-manager-library-3239137-docs`: Official specifications and API contract.
