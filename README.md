# 🍊 OrangeHRM v5.0 — My Info Module: QA Testing Project

> A structured, end-to-end test suite validating core workflows and role-based access controls across the OrangeHRM 5.0 platform.

---

## 📋 Overview

This repository contains the complete **Test Plan** and executable **Test Cases** for the OrangeHRM Version 5.0 — My Info Module.

The testing strategy is designed to verify that:
- Core business workflows function correctly across all user roles
- Role-based access permissions are strictly enforced
- The employee self-service experience meets all defined requirements

Test cases are extracted from the master test plan (`Test Plan OrangeHRM.docx`) and compiled into a structured Excel workbook (`OrangeHRM_Test Case.xlsx`).

---

## 📁 Repository Structure

```
📦 orangehrm-testing/
├── 📄 Test Plan OrangeHRM.docx      # Master document: objectives, schedules, device matrix, scenarios
└── 📊 OrangeHRM_Test Case.xlsx      # Executable test cases, partitioned by module
```

---

## 🧩 Modules Under Test

| # | Module | Key Test Focus |
|---|--------|----------------|
| 1 | **Login / Logout & Password Management** | Valid/invalid credentials, password changes, multi-role login |
| 2 | **Admin Module** | System configuration, supervisor creation, non-admin access restrictions |
| 3 | **PIM (Personnel Information Management)** | Employee addition workflow, role-restricted record viewing & editing |
| 4 | **Leave Module** | Leave application workflow, self-application limits, manager approval boundaries |
| 5 | **Time Module** | Timesheet configuration, log generation, supervisor approval flows |
| 6 | **Dashboard & Directory** | Widget visibility, data aggregation limits, role-based search behavior |

---

## 🏗️ Testing Strategy

Testing is structured around two primary dimensions:

### 🔄 Workflow Testing
Validates that multi-stage business processes transition correctly between user roles and system states — ensuring logical, end-to-end process integrity.

### 🔐 Role-Based Access Testing
A critical security verification phase that enforces strict access boundaries across three user roles:

| Role | Description |
|------|-------------|
| `Admin` | Full system access including configuration and user management |
| `Supervisor` | Department-level access; can manage and approve direct reports |
| `ESS (Employee Self-Service)` | Personal data access only; cannot view or edit other records |

---

## 🐞 Test Execution & Defect Management

### Tooling
- **Test Tracker**: Microsoft Excel — for distributing, tracking, and recording execution results

### Defect Lifecycle
```
New → Open → In Progress → Fixed → Verified → Closed
```

### Severity Matrix

| Severity | SLA | Examples |
|----------|-----|---------|
| 🔴 **Critical** | < 24 Hours | App crash, data loss, login failure |
| 🟠 **High** | < 48 Hours | Major broken feature, requires significant workaround |
| 🟡 **Medium** | Standard | Feature glitch with simple workaround |
| 🟢 **Low** | Standard | Cosmetic or UI misalignment |

---

## 💻 Environment & Prerequisites

### Browser Support

| Browser | Priority |
|---------|----------|
| Chrome | P0 — Primary |
| Firefox | P1 |
| Safari | P1 |
| Edge | P2 |

### Platform / Viewport

| Platform | Resolution | Scope |
|----------|------------|-------|
| Desktop | 1920 × 1080 | Full suite |
| Mobile | 375 × 812 | Critical ESS features only |

### Required Credentials
To run the full test suite, you need active accounts for all three roles:
- ✅ Admin user
- ✅ Supervisor user
- ✅ ESS (standard employee) user

---

## 🚀 Running the Test Cases

1. **Open** `OrangeHRM_Test Case.xlsx`
2. **Navigate** to the relevant module tab at the bottom of the workbook
3. **Review** the *Pre-requisites* column for your target test case
4. **Execute** the steps listed under *Steps to Reproduce*
5. **Record** your outcome in the *Actual Result* column
6. **Mark** the *Status* column as `Pass` or `Fail`
7. **For failures** — raise a defect ticket with:
   - Environment details (browser, role, build version)
   - Step-by-step reproduction steps
   - Expected vs. actual result
   - Assigned severity level

---

## 📌 Notes

- All test cases are scoped to **functional and role-based testing** only. Performance and security penetration testing are out of scope for this suite.
- Ensure test data is reset between runs to avoid state-dependent failures.
- Coordinate with the dev team before re-running role-based tests after permission changes.


