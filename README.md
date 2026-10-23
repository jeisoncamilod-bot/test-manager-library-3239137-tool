# Manager Library — Tools and Demo Data Seeder

## Overview

This repository contains the supporting utilities for the Manager Library project, with a focus on the demonstration data seeder.

The seeder is intended to populate the application with demonstration data through the backend API. This helps prepare sample data for development, testing, and demonstrations.

The repository is intentionally initialized with minimal content. Each learner is responsible for developing their own fork according to the project's official specifications.

## Purpose

The purpose of this repository is to document and organize the utilities that support the Manager Library project.

The main intended responsibility is the demonstration data seeder, which uses the Manager Library API rather than directly managing the application's database.

## Scope

The repository is intended to cover:

- Demonstration data seeding.
- Preparation of sample data for development and demonstrations.
- Interaction with the backend API to submit demonstration data.
- Documentation of the seeder's configuration, prerequisites, and usage.
- Alignment with the official Manager Library specifications.

## Out of Scope

This repository is not responsible for:

- Implementing the backend API.
- Implementing the React frontend.
- Managing the database infrastructure.
- Replacing the official project specifications.
- Bypassing API validation or business rules.
- Storing production credentials or sensitive user data.

## Relationship with the Backend API

The demonstration data seeder is intended to use the Manager Library API to create the data required for demonstrations.

The seeder should follow the API contract, including its endpoint definitions, authentication requirements, request formats, and validation rules.

It should not write directly to the database or bypass the backend's business logic.

## Relationship with Other Repositories

Manager Library is organized into six repositories:

| Repository | Responsibility |
|---|---|
| `test-manager-library-3239137-docs` | Official project specifications in `spec-python/` and `spec-.net/`. |
| `test-manager-library-3239137-api` | Backend implementation using PHP and Laravel. |
| `test-manager-library-3239137-app` | Frontend implementation using React. |
| `test-manager-library-3239137-page` | Public static presentation site. |
| `test-manager-library-3239137-infra` | Containers, networking, volumes, and database engine. |
| `test-manager-library-3239137-tool` | Supporting utilities, including the demonstration data seeder. |

## Development Guidelines

When developing utilities for this repository:

1. Read the official project specifications before defining sample data.
2. Follow the documented API contract.
3. Use the API rather than accessing the database directly.
4. Respect authentication, validation, and business rules.
5. Avoid hardcoding credentials or exposing sensitive information.
6. Keep sample data consistent with the project's data model.
7. Document prerequisites and usage instructions.
8. Verify the implementation before describing a utility as functional.

## Technology Context

The overall challenge specifies React for the frontend and PHP with Laravel for the backend.

The implementation details of the tools repository must be determined according to the project's requirements. This README does not prescribe an unverified programming language or implementation framework for the seeder.

## Current Status

The repository is intended for supporting utilities, particularly the demonstration data seeder.

Its actual implementation status must be verified against the files committed to the repository. This document describes the repository's purpose and intended responsibilities; it does not claim that a working seeder has already been implemented.

## Related Documentation

Consult the `test-manager-library-3239137-docs` repository for the official specifications, API contract, data model, business rules, and acceptance criteria relevant to the demonstration data seeder.
