# User Management UI Specification Document

## Overview

This document describes the user interface requirements for the User Management screen. The page allows administrative users to view existing users, add new users, and manage their roles and statuses.

---

## UI Layout

The screen consists of two main sections:

1. **User List Table (Left Panel)**
2. **New User Form (Right Panel)**

---

## Components

### 1. User List Table

- Columns:
  - **ID**: Auto-incremented user ID
  - **Username**: Displayed as text
  - **Email**: User email address
  - **Enabled**: Boolean value (true/false)
- Functionalities:
  - Sortable columns
  - Filter inputs for each column
  - Checkbox to toggle visibility of disabled users (`Hide Disabled User`)
  - Button: `+ New User` → Clears and opens the form on the right

---

### 2. New User Form

Form fields:
- `Username` (Text - required)
- `Display Name` (Text - optional)
- `Phone` (Text - optional)
- `Email` (Text - required, must be valid format)
- `User Roles` (Dropdown - multi-select: Guest, Admin, SuperAdmin)
- `Enabled` (Checkbox - true/false)

Buttons:
- `Save User` → Submits the form and updates the user list

---

## Initial UI State on Page Load

- The user list should be populated with all enabled users.
- Disabled users are hidden by default (can be shown via checkbox).
- Form fields are initially empty.
- Any form submission should validate the inputs and provide inline feedback if validation fails.

---

## Notes for Developers

- All inputs must be sanitized before backend submission.
- Role options should come from a backend configuration endpoint.
- Ensure email uniqueness before saving.

