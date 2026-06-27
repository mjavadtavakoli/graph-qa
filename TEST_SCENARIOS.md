# TEST_SCENARIOS.md

# Test Scenarios

## Overview

This document describes the end-to-end functional test scenarios for the Phone Book Client/Server application.

Each scenario represents a complete user workflow that should be verified during system testing.

---

# TS-001 - Register a New User

### Objective

Verify that a new user can successfully register.

### Preconditions

* Server is running.
* Username does not already exist.

### Test Flow

1. Start the client.
2. Send a **Sign Up** request.
3. Enter a valid username.
4. Enter a valid password.
5. Enter a valid email.

### Expected Result

The user is successfully registered.

---

# TS-002 - Login with Valid Credentials

### Objective

Verify that a registered user can log in.

### Preconditions

* User has already been registered.

### Test Flow

1. Send a **Sign In** request.
2. Enter a valid username.
3. Enter the correct password.

### Expected Result

The login request is completed successfully.

---

# TS-003 - Login with Invalid Password

### Objective

Verify application behavior when an incorrect password is entered.

### Preconditions

* User exists.

### Test Flow

1. Send a **Sign In** request.
2. Enter the correct username.
3. Enter an invalid password.

### Expected Result

The login request is rejected.

---

# TS-004 - Logout

### Objective

Verify that a logged-in user can log out.

### Preconditions

* User is logged in.

### Test Flow

1. Send a **Logout** request.
2. Wait for server response.

### Expected Result

The user is logged out successfully.

---

# TS-005 - Add a Phone Book Contact

### Objective

Verify that a new phone book contact can be created.

### Preconditions

* Server is running.

### Test Flow

1. Send **Add Phone User** request.
2. Enter username.
3. Enter phone number.

### Expected Result

The new contact is added successfully.

---

# TS-006 - Add Another Phone Number

### Objective

Verify that an additional phone number can be assigned to an existing contact.

### Preconditions

* Contact already exists.

### Test Flow

1. Send **Add Phone Number** request.
2. Select existing username.
3. Enter a new phone number.

### Expected Result

The phone number is added successfully.

---

# TS-007 - Edit Contact Information

### Objective

Verify that contact information can be updated.

### Preconditions

* Contact exists.

### Test Flow

1. Send **Edit Phone User** request.
2. Enter existing username.
3. Update username and/or phone number.

### Expected Result

The contact information is updated.

---

# TS-008 - Search Contact by Name

### Objective

Verify search functionality using username.

### Preconditions

* Contact exists.

### Test Flow

1. Send **Get Phone User By Name** request.
2. Enter username.

### Expected Result

The matching contact information is returned.

---

# TS-009 - Search Contact by Phone Number

### Objective

Verify search functionality using phone number.

### Preconditions

* Phone number exists.

### Test Flow

1. Send **Get Phone User By Number** request.
2. Enter phone number.

### Expected Result

The related contact information is returned.

---

# TS-010 - Display All Contacts

### Objective

Verify that all contacts are returned.

### Preconditions

* At least one contact exists.

### Test Flow

1. Send **Get All Phone Users** request.

### Expected Result

The complete contact list is displayed.

---

# TS-011 - Remove Contact

### Objective

Verify that an existing contact can be removed.

### Preconditions

* Contact exists.

### Test Flow

1. Send **Remove Phone User** request.
2. Enter username.

### Expected Result

The contact is removed successfully.

---

# TS-012 - Invalid JSON File

### Objective

Verify client behavior with an invalid JSON file.

### Preconditions

* Invalid JSON file is available.

### Test Flow

1. Execute the client.
2. Load the invalid JSON file.

### Expected Result

The client rejects the file and displays an error message.

---

# TS-013 - Missing JSON File

### Objective

Verify client behavior when the command file is missing.

### Preconditions

* Command file does not exist.

### Test Flow

1. Execute the client.
2. Specify a non-existing file.

### Expected Result

The client reports that the file cannot be found.

---

# TS-014 - Unknown Command

### Objective

Verify server behavior when an unsupported command is received.

### Preconditions

* Server is running.

### Test Flow

1. Create a request containing an unknown command.
2. Send the request.

### Expected Result

The request is rejected and an error response is returned.

---

# TS-015 - Complete End-to-End Workflow

### Objective

Verify the complete application workflow.

### Preconditions

* Server is running.

### Test Flow

1. Register a new user.
2. Log in.
3. Add a phone book contact.
4. Add another phone number.
5. Search by username.
6. Search by phone number.
7. Display all contacts.
8. Edit contact information.
9. Remove the contact.
10. Log out.

### Expected Result

All operations are completed successfully without unexpected errors.

---

# Scenario Summary

| Scenario ID | Description            | Priority |
| ----------- | ---------------------- | -------- |
| TS-001      | Register User          | High     |
| TS-002      | Login                  | High     |
| TS-003      | Invalid Login          | High     |
| TS-004      | Logout                 | Medium   |
| TS-005      | Add Contact            | High     |
| TS-006      | Add Phone Number       | Medium   |
| TS-007      | Edit Contact           | High     |
| TS-008      | Search by Name         | High     |
| TS-009      | Search by Phone Number | High     |
| TS-010      | Get All Contacts       | Medium   |
| TS-011      | Remove Contact         | High     |
| TS-012      | Invalid JSON           | High     |
| TS-013      | Missing JSON File      | Medium   |
| TS-014      | Unknown Command        | Medium   |
| TS-015      | Complete Workflow      | High     |

---

# Notes

* All scenarios are based on the current implementation of the application.
* These scenarios are intended for manual execution and may also be used as a reference for future automation tests.
* Any failed scenario should be documented in the Bug Report using the project's bug reporting template.
