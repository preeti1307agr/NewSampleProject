# User Authentication Specification (Frontend Only)

## Overview
This feature allows users to:
- Register a new account
- Login using existing credentials

⚠️ Note: This is a frontend-only implementation.
No real backend is used. Data will be stored in browser localStorage.

Frontend: React  

---

## 1. User Registration

### Fields Required
- Name (string, required)
- Email (string, required, valid email format)
- Password (string, required, min 6 characters)

### Behavior
- On submit:
  - Validate all fields
  - Check if email already exists in localStorage
  - If not, store user in localStorage

### Stored Data Format (localStorage key: "users")
[
  {
    "name": "string",
    "email": "string",
    "password": "string"
  }
]

### Success
- Show message: "User registered successfully"
- Redirect to Login page

### Error Cases
- Email already exists → show error
- Invalid inputs → show validation errors

---

## 2. User Login

### Fields Required
- Email (string, required)
- Password (string, required)

### Behavior
- On submit:
  - Validate inputs
  - Check credentials against localStorage

### Success
- Store logged-in user in localStorage (key: "authUser")
{
  "name": "string",
  "email": "string"
}

- Redirect to dashboard/home page

### Error Cases
- Invalid email/password → show error message

---

## 3. Frontend Requirements

### Pages
- Login Page
- Register Page
- Dashboard Page (simple welcome screen)

### UI Behavior
- Form validation before submission
- Show success/error messages
- Redirect after login/register

---

## 4. State Management

- Store users in localStorage
- Store logged-in user in localStorage
- Persist login after page refresh

---
