
# MANUAL_TEST.md

# Manual Test Checklist

## Overview

This document contains the manual testing checklist for the Phone Book Client/Server application.

The purpose of this checklist is to verify that the main functionalities of the application work correctly before a release.

---

# Test Environment

| Item             | Value                     |
| ---------------- | ------------------------- |
| Application      | Phone Book Client/Server  |
| Operating System | Windows / Linux           |
| Database         | SQLite (sab.db)           |
| Communication    | ZeroMQ                    |
| Test Type        | Manual Functional Testing |

---

# Authentication Tests

| ID     | Test Description                    | Status        | Notes |
| ------ | ----------------------------------- | ------------- | ----- |
| MT-001 | Register a new user                 | ☐ Pass ☐ Fail |       |
| MT-002 | Register using an existing username | ☐ Pass ☐ Fail |       |
| MT-003 | Login with valid credentials        | ☐ Pass ☐ Fail |       |
| MT-004 | Login with invalid password         | ☐ Pass ☐ Fail |       |
| MT-005 | Logout                              | ☐ Pass ☐ Fail |       |

---

# Phone Book Tests

| ID     | Test Description         | Status        | Notes |
| ------ | ------------------------ | ------------- | ----- |
| MT-006 | Add a new phone user     | ☐ Pass ☐ Fail |       |
| MT-007 | Add another phone number | ☐ Pass ☐ Fail |       |
| MT-008 | Edit username            | ☐ Pass ☐ Fail |       |
| MT-009 | Edit phone number        | ☐ Pass ☐ Fail |       |
| MT-010 | Remove phone user        | ☐ Pass ☐ Fail |       |

---

# Search Tests

| ID     | Test Description                       | Status        | Notes |
| ------ | -------------------------------------- | ------------- | ----- |
| MT-011 | Search by username                     | ☐ Pass ☐ Fail |       |
| MT-012 | Search by phone number                 | ☐ Pass ☐ Fail |       |
| MT-013 | Display all contacts                   | ☐ Pass ☐ Fail |       |
| MT-014 | Search for a non-existing username     | ☐ Pass ☐ Fail |       |
| MT-015 | Search for a non-existing phone number | ☐ Pass ☐ Fail |       |

---

# Client Validation Tests

| ID     | Test Description               | Status        | Notes |
| ------ | ------------------------------ | ------------- | ----- |
| MT-016 | Load a valid JSON file         | ☐ Pass ☐ Fail |       |
| MT-017 | Load an invalid JSON file      | ☐ Pass ☐ Fail |       |
| MT-018 | Execute with missing JSON file | ☐ Pass ☐ Fail |       |

---

# Server Validation Tests

| ID     | Test Description                        | Status        | Notes |
| ------ | --------------------------------------- | ------------- | ----- |
| MT-019 | Process valid request                   | ☐ Pass ☐ Fail |       |
| MT-020 | Process unsupported command             | ☐ Pass ☐ Fail |       |
| MT-021 | Handle multiple commands in one request | ☐ Pass ☐ Fail |       |

---

# End-to-End Test

| ID     | Test Description                                                 | Status        | Notes |
| ------ | ---------------------------------------------------------------- | ------------- | ----- |
| MT-022 | Register → Login → Add Contact → Search → Edit → Delete → Logout | ☐ Pass ☐ Fail |       |

---

# Test Execution Summary

| Item             | Result |
| ---------------- | ------ |
| Total Test Cases | 22     |
| Passed           |        |
| Failed           |        |
| Blocked          |        |
| Not Executed     |        |

---

# Defect Tracking

| Bug ID | Description | Severity | Status |
| ------ | ----------- | -------- | ------ |
|        |             |          |        |
|        |             |          |        |
|        |             |          |        |
|        |             |          |        |

---

# Test Execution Information

| Item                | Value       |
| ------------------- | ----------- |
| Tester              |             |
| Test Date           |             |
| Application Version |             |
| Environment         |             |
| Result              | Pass / Fail |

---

# Notes

* Execute all test cases using the current application build.
* Record any unexpected behavior in `BUG_REPORT.md`.
* If a test fails, include detailed reproduction steps and supporting information.
* Ensure the server is running before executing client-side tests.
* Verify the database is accessible before starting the test session.

---

# Approval

| Role     | Name | Signature | Date |
| -------- | ---- | --------- | ---- |
| Tester   |      |           |      |
| Reviewer |      |           |      |
