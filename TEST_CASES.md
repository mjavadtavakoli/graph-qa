# TEST_CASES.md

# Test Cases

## Overview

This document contains the functional test cases for the Phone Book Client/Server application.

Each test case verifies one specific functionality of the system.

---

# TC-001

### Title

Register a new user with valid information

### Preconditions

* Server is running.
* Username does not already exist.

### Test Steps

1. Open the client.
2. Send a Sign Up request.
3. Enter a valid username.
4. Enter a valid password.
5. Enter a valid email.
6. Submit the request.

### Expected Result

The user is registered successfully.

---

# TC-002

### Title

Register with an existing username

### Preconditions

* Username already exists.

### Test Steps

1. Send a Sign Up request.
2. Enter an existing username.
3. Submit the request.

### Expected Result

The registration request should fail.

---

# TC-003

### Title

Login using valid credentials

### Preconditions

* User is registered.

### Test Steps

1. Send a Sign In request.
2. Enter valid username.
3. Enter valid password.

### Expected Result

The login operation is completed successfully.

---

# TC-004

### Title

Login using incorrect password

### Preconditions

* User exists.

### Test Steps

1. Send a Sign In request.
2. Enter valid username.
3. Enter incorrect password.

### Expected Result

The login request is rejected.

---

# TC-005

### Title

Logout

### Preconditions

* User is logged in.

### Test Steps

1. Send Logout request.

### Expected Result

The user is logged out successfully.

---

# TC-006

### Title

Add new phone book contact

### Preconditions

* Server is running.

### Test Steps

1. Send Add Phone User request.
2. Enter username.
3. Enter phone number.
4. Submit.

### Expected Result

The contact is created successfully.

---

# TC-007

### Title

Add duplicate phone user

### Preconditions

* Contact already exists.

### Test Steps

1. Add an existing contact again.

### Expected Result

The request should fail.

---

# TC-008

### Title

Add second phone number

### Preconditions

* Contact exists.

### Test Steps

1. Send Add Phone Number request.
2. Enter existing username.
3. Enter another phone number.

### Expected Result

The phone number is added successfully.

---

# TC-009

### Title

Add duplicate phone number

### Preconditions

* Phone number already exists.

### Test Steps

1. Add an existing phone number.

### Expected Result

The operation should fail.

---

# TC-010

### Title

Edit username

### Preconditions

* Contact exists.

### Test Steps

1. Send Edit Phone User request.
2. Update username.

### Expected Result

Username is updated successfully.

---

# TC-011

### Title

Edit phone number

### Preconditions

* Contact exists.

### Test Steps

1. Send Edit Phone User request.
2. Update phone number.

### Expected Result

Phone number is updated successfully.

---

# TC-012

### Title

Search by username

### Preconditions

* Contact exists.

### Test Steps

1. Send Get Phone User By Name request.
2. Enter username.

### Expected Result

The requested user information is returned.

---

# TC-013

### Title

Search non-existing username

### Preconditions

* User does not exist.

### Test Steps

1. Search using an unknown username.

### Expected Result

No matching user is found.

---

# TC-014

### Title

Search by phone number

### Preconditions

* Phone number exists.

### Test Steps

1. Send Get Phone User By Number request.
2. Enter phone number.

### Expected Result

The related user information is returned.

---

# TC-015

### Title

Search using an unknown phone number

### Preconditions

* Phone number does not exist.

### Test Steps

1. Search using an unknown phone number.

### Expected Result

No matching result is returned.

---

# TC-016

### Title

Retrieve all contacts

### Preconditions

* One or more contacts exist.

### Test Steps

1. Send Get All Phone Users request.

### Expected Result

The complete contact list is returned.

---

# TC-017

### Title

Retrieve contacts when phone book is empty

### Preconditions

* Phone book contains no records.

### Test Steps

1. Send Get All Phone Users request.

### Expected Result

An empty list is returned.

---

# TC-018

### Title

Remove an existing contact

### Preconditions

* Contact exists.

### Test Steps

1. Send Remove Phone User request.
2. Enter username.

### Expected Result

The contact is removed successfully.

---

# TC-019

### Title

Remove a non-existing contact

### Preconditions

* Contact does not exist.

### Test Steps

1. Remove an unknown contact.

### Expected Result

The application should reject the request or return an appropriate response.

---

# TC-020

### Title

Load a valid JSON command file

### Preconditions

* Valid JSON file exists.

### Test Steps

1. Execute the client.
2. Load the command file.

### Expected Result

The request is accepted and sent to the server.

---

# TC-021

### Title

Load an invalid JSON file

### Preconditions

* Invalid JSON file exists.

### Test Steps

1. Execute the client.
2. Load the invalid JSON file.

### Expected Result

The client reports an invalid JSON format.

---

# TC-022

### Title

Command file not found

### Preconditions

* File does not exist.

### Test Steps

1. Execute the client.
2. Specify a non-existing file.

### Expected Result

The client reports that the command file cannot be found.

---

# TC-023

### Title

Send an unsupported command

### Preconditions

* Server is running.

### Test Steps

1. Modify the command name.
2. Send the request.

### Expected Result

The server rejects the request.

---

# TC-024

### Title

Execute complete workflow

### Preconditions

* Server is running.

### Test Steps

1. Register a user.
2. Login.
3. Add a phone user.
4. Add another phone number.
5. Search by username.
6. Search by phone number.
7. Display all contacts.
8. Edit user information.
9. Remove contact.
10. Logout.

### Expected Result

All operations complete successfully.

---

# Test Case Summary

| Module            | Number of Test Cases |
| ----------------- | -------------------- |
| Authentication    | 5                    |
| Phone Book        | 14                   |
| Client Validation | 3                    |
| Server Validation | 1                    |
| End-to-End        | 1                    |
| **Total**         | **24**               |

---

# Notes

* All test cases are based on the current implementation of the application.
* These test cases can be executed manually or used as input for automation testing.
* Any deviation from the expected result should be reported in the `BUG_REPORT.md` document.
