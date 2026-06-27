# BUG_REPORT.md

# Bug Report

This document contains the issues identified during manual testing of the application.

---

## BUG-001

### Title

Application cannot process unsupported commands.

**Severity:** High

**Environment:** Python Application (Client/Server)

### Preconditions

* Server is running.
* Client is connected.

### Steps to Reproduce

1. Open `commands.json`.
2. Replace a valid command name with an undefined command.
3. Run the client.
4. Wait for the server response.

### Actual Result

The request is not processed successfully and the application returns an unexpected error.

### Expected Result

The application should reject unsupported commands and return a meaningful error message without interrupting request processing.

### Additional Notes

Observed while testing invalid command scenarios.

**Status:** Open

---

## BUG-002

### Title

Invalid login credentials return an unhandled application error.

**Severity:** Medium

**Environment:** Python Application

### Preconditions

* A registered user exists.

### Steps to Reproduce

1. Start the server.
2. Send a Sign In request.
3. Enter an incorrect password.

### Actual Result

The login request fails with a generic error response.

### Expected Result

The application should return a clear authentication failure message.

### Additional Notes

Observed during authentication testing.

**Status:** Open

---

## BUG-003

### Title

Application accepts duplicate phone numbers test scenario without clear validation feedback.

**Severity:** Medium

### Preconditions

* A phone number already exists.

### Steps to Reproduce

1. Add a phone user.
2. Try to register the same phone number again.

### Actual Result

The operation fails with a database-related error.

### Expected Result

The application should notify the user that the phone number already exists.

### Additional Notes

Observed while testing duplicate data.

**Status:** Open

---

## BUG-004

### Title

Searching for a non-existing phone user returns an unexpected error.

**Severity:** Medium

### Preconditions

Database contains no user with the requested name.

### Steps to Reproduce

1. Run the server.
2. Send a Get Phone User By Name request.
3. Enter a username that does not exist.

### Actual Result

The application returns an unexpected error.

### Expected Result

The application should indicate that no matching user was found.

### Additional Notes

Observed during negative testing.

**Status:** Open

---

## BUG-005

### Title

Client fails when command file is not available.

**Severity:** Low

### Steps to Reproduce

1. Rename or remove `commands.json`.
2. Run the client.

### Actual Result

The client terminates and displays an error.

### Expected Result

The application should clearly notify the user that the command file cannot be found.

### Additional Notes

Observed during file validation testing.

**Status:** Open

---

## BUG-006

### Title

Server crashes when processing an unsupported command.

**Severity:** Medium

**Priority:** Medium

**Environment:**

* Python 3.13
* SQLite
* ZeroMQ

### Preconditions

* Server is running.
* Client is connected.
* A command file contains an unsupported command.

### Steps to Reproduce

1. Create a JSON file containing an undefined command (e.g., `"hello"`).
2. Start the server.
3. Execute:

```bash
python3 client.py --file samples/unknown_command.json
```

4. Observe the server and client outputs.

### Actual Result

* The server terminates with a `KeyError` exception.
* The client receives the raw error value:

```
'hello'
```

### Expected Result

The server should detect that the command is unsupported, return a meaningful error message to the client, and continue running without terminating.

### Additional Notes

The application does not gracefully handle unsupported commands and exposes the raw exception to the client.

**Status:** Open
