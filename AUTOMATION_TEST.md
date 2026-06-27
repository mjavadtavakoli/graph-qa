# AUTOMATION_TEST.md

# Automation Test Plan

## Overview

This document defines the automation testing scope for the Phone Book Client/Server application.

The purpose of automation testing is to verify the application's core functionality, reduce repetitive manual testing, and quickly detect regressions after future changes.

> **Note:**
> Currently, the project does not contain automated test scripts. The following test plan and sample code demonstrate how automation testing can be implemented using **pytest**.

---

# Test Environment

| Item      | Value              |
| --------- | ------------------ |
| Language  | Python             |
| Framework | pytest             |
| Test Type | Functional Testing |
| Execution | Local              |
| Target    | Client & Server    |

---

# Automation Scope

The following modules are recommended for automation testing.

| Module         | Description                         |
| -------------- | ----------------------------------- |
| Authentication | Sign Up, Sign In, Logout            |
| Client         | JSON validation and request sending |
| Server         | Request processing                  |
| Phone Book     | CRUD operations                     |
| Search         | Search by name and phone number     |

---

# Client Automation Tests

| ID     | Test Description        | Expected Result            |
| ------ | ----------------------- | -------------------------- |
| AT-001 | Start client            | Client starts successfully |
| AT-002 | Send valid JSON         | Request is sent            |
| AT-003 | Missing JSON file       | Validation error           |
| AT-004 | Invalid JSON format     | Validation error           |
| AT-005 | Receive server response | Response displayed         |

---

# Server Automation Tests

| ID     | Test Description       | Expected Result           |
| ------ | ---------------------- | ------------------------- |
| AT-006 | Sign Up                | User created successfully |
| AT-007 | Sign In                | Login successful          |
| AT-008 | Logout                 | User logged out           |
| AT-009 | Add Phone User         | User added                |
| AT-010 | Remove Phone User      | User removed              |
| AT-011 | Edit Phone User        | Information updated       |
| AT-012 | Add Phone Number       | Number added              |
| AT-013 | Search by Name         | User returned             |
| AT-014 | Search by Phone Number | User returned             |
| AT-015 | Get All Users          | User list returned        |

---

# Negative Test Scenarios

| ID      | Test Description       | Expected Result     |
| ------- | ---------------------- | ------------------- |
| NAT-001 | Invalid JSON           | Validation error    |
| NAT-002 | Missing JSON file      | File not found      |
| NAT-003 | Unknown command        | Error response      |
| NAT-004 | Invalid password       | Login failed        |
| NAT-005 | Unknown username       | User not found      |
| NAT-006 | Unknown phone number   | No result           |
| NAT-007 | Duplicate username     | Registration failed |
| NAT-008 | Duplicate phone number | Operation failed    |

---

# Regression Test Scope

The following features should be executed after every update:

* User Registration
* User Login
* Logout
* Add Phone User
* Remove Phone User
* Edit Phone User
* Add Phone Number
* Search by Name
* Search by Phone Number
* Get All Users

---

# Sample Automation Scripts

The following examples demonstrate how automated tests can be implemented using **pytest**.

---

## Example 1 - Sign Up Test

```python
from core.auth import sign_up

def test_sign_up():
    command = {
        "username": "test_user",
        "password": "123456",
        "email": "test@test.com"
    }

    result = sign_up(command)

    assert "added successfully" in result
```

---

## Example 2 - Sign In Test

```python
from core.auth import sign_in

def test_sign_in():
    command = {
        "username": "admin",
        "password": "admin"
    }

    result = sign_in(command)

    assert "signed in successfully" in result
```

---

## Example 3 - Add Phone User

```python
from core.phone_book import add_new_user

def test_add_phone_user():
    command = {
        "username": "Ali",
        "phone_number": "09121234567"
    }

    result = add_new_user(command)

    assert "added successfully" in result
```

---

## Example 4 - Search User

```python
from core.phone_book import get_user_by_name

def test_search_user():
    command = {
        "username": "Ali"
    }

    result = get_user_by_name(command)

    assert result["name"] == "Ali"
```

---

## Example 5 - Add Phone Number

```python
from core.phone_book import add_phone_number

def test_add_phone_number():
    command = {
        "username": "Ali",
        "phone_number": "09125556677"
    }

    result = add_phone_number(command)

    assert "successful" in result
```

---

## Example 6 - Invalid JSON File

```python
import pytest

from client import tcp_client

def test_invalid_json():
    with pytest.raises(Exception):
        tcp_client(
            "127.0.0.1",
            9090,
            "invalid.json"
        )
```

---

## Example 7 - Missing Command File

```python
import pytest

from client import tcp_client

def test_missing_file():
    with pytest.raises(Exception):
        tcp_client(
            "127.0.0.1",
            9090,
            "missing.json"
        )
```

---

# Suggested Test Structure

```
tests/
│
├── test_client.py
├── test_server.py
├── test_auth.py
├── test_phone_book.py
└── test_search.py
```

---

# Running Tests

Execute all tests:

```bash
pytest
```

Run tests with detailed output:

```bash
pytest -v
```

Generate coverage report:

```bash
pytest --cov
```

Run a single test file:

```bash
pytest tests/test_auth.py
```

---

# Test Status

| Category             | Status  |
| -------------------- | ------- |
| Client Tests         | Planned |
| Server Tests         | Planned |
| Authentication Tests | Planned |
| Phone Book Tests     | Planned |
| Regression Tests     | Planned |
| Negative Tests       | Planned |

---

# Notes

* This document defines the proposed automation testing strategy for the current implementation.
* Sample scripts are provided as reference examples using **pytest**.
* Automation tests are not currently included in the project and should be implemented separately if automated validation is required.
