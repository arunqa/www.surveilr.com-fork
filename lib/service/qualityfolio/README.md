
# Qualityfolio Service Specification

The Qualityfolio Service Specification provides a comprehensive test management system designed within the **surveilr** platform. This open-source, compliance-oriented system leverages structured Markdown files, SQL querying, and a web-based UI, making it a robust alternative for quality and compliance-focused test management.

## Overview

### Purpose
The Qualityfolio Service aims to:
- Offer a secure, compliant, and customizable test management solution.
- Store test data in Markdown for traceable and easily integrable documentation.
- Use SQL for advanced querying, analytics, and reporting in a web UI.

### Key Components
- **Markdown-Based Test Storage**: Stores test narratives in Markdown for direct access and version control.
- **Foreign Integration Identifier (FII) System**: Unique codes enabling comprehensive traceability.
- **surveilr Ingestion Pipeline**: Automates Markdown and other test data ingestion into surveilr.
- **RSDD-Based SQLite Query Interface**: Facilitates real-time analytics for test management and tracking.
- **Web UI for Test Management**: Provides a user-friendly test management functionalities within surveilr.

## Structure

### Directory Structure
The test-related data is stored within `/qualityfolio-service-content`, organized the structure:

```
/qualityfolio-service-content
   ├── test-plans
   │   └── {test-plan-FII-code}.md
   ├── test-suites
   │   └── {test-suite-FII-code}.md
   ├── test-cases
   │   └── {test-case-FII-code}.md
   ├── test-runs
   │   └── {test-run-FII-code}.md
   └── test-results
       └── {test-result-FII-code}.md
```

### Example Format
---

## 1. **Test Suites**

A test suite groups related test cases. Here’s how a sample test suite might look in Markdown.

**File: `{test-suite-FII-code}.md`**

```markdown
---
suite_id: TS-001
title: User Login Suite
description: "This suite contains tests for verifying the user login functionality."
created_by: "QA Engineer"
created_date: "2023-11-13"
tags:
  - login
  - authentication
---

# User Login Test Suite

This suite tests the core functionality of the user login feature, including error handling and valid login scenarios.

## Test Cases

- [TC-001: Login with Valid Credentials](./test_cases/TC-001_login_valid.md)
- [TC-002: Login with Invalid Password](./test_cases/TC-002_login_invalid.md)
- [TC-003: Login with Empty Fields](./test_cases/TC-003_login_empty_fields.md)
```

---

### 2. **Test Cases**

Each test case file details the specific steps, expected results, and any necessary prerequisites.

**File: `{test-case-FII-code}.md`**

```markdown
---
test_case_id: TC-001
title: Login with Valid Credentials
description: "Verify that a user can log in with valid username and password."
priority: High
status: Active
preconditions: 
  - "User is registered in the system."
created_by: "QA Engineer"
created_date: "2023-11-13"
suite_id: TS-001
tags:
  - login
  - functional
---

# Login with Valid Credentials

## Preconditions

- User is registered in the system.

## Test Steps

1. Navigate to the login page.
2. Enter a valid username and password.
3. Click on the "Login" button.

## Expected Result

- The user is successfully logged in and redirected to the dashboard.
```

---

### 3. **Test Plans**

A test plan may encompass multiple suites or configurations and is designed to document the test strategy.

**File: `{test-plan-FII-code}.md`**

```markdown
---
test_plan_id: TP-001
title: Test Plan for Release v1.0
description: "This plan outlines the testing strategy and cases for Release v1.0."
created_by: "QA Lead"
created_date: "2023-11-13"
status: In Progress
suites:
  - TS-001
  - TS-002
tags:
  - release_v1.0
  - full_regression
---

# Test Plan for Release v1.0

## Overview

This test plan defines the scope, approach, resources, and schedule for testing the Release v1.0.

## Included Suites

- **[User Login Suite](../suites/suite_example.md)** (TS-001)
- **[Account Management Suite](../suites/suite_account_mgmt.md)** (TS-002)

## Objectives

- Ensure all primary user workflows function as expected.
- Verify no critical bugs are present.
- Test across multiple configurations: browser and mobile.

## Schedule

| Phase               | Start Date | End Date |
|---------------------|------------|----------|
| Test Preparation    | 2023-10-01 | 2023-10-15 |
| Test Execution      | 2023-10-16 | 2023-10-30 |
| Bug Fix Verification| 2023-11-01 | 2023-11-10 |
| Report              | 2023-11-12 | 2023-11-13 |
```

---

### 4. **Test Results**

Test results can be stored individually for each test case in Markdown, making it easy to record and version control every execution instance.

**File: `{test-result-FII-code}.md`**

```markdown
---
result_id: TR-001
test_case_id: TC-001
test_plan_id: TP-001
execution_date: "2023-11-13"
executed_by: "QA Engineer"
status: Passed
environment: "Chrome 95, Windows 10"
notes: "All steps executed as expected. No issues found."
attachments:
  - "screenshots/login_successful.png"
---

# Test Result for TC-001: Login with Valid Credentials

## Execution Details

- **Date:** 2023-11-13
- **Executed By:** QA Engineer
- **Environment:** Chrome 95, Windows 10
- **Status:** Passed

## Observations

- All steps executed as expected. User successfully logged in and redirected to the dashboard.

## Attachments

- [Screenshot of successful login](../attachments/screenshots/login_successful.png)
```

---

### 5. **Test Run (Optional)**

If you want to group results for specific runs (e.g., a specific build or sprint), you can create a test run file to track a specific execution batch.

**File: `test_runs/{test-run-FII-code}.md`**

```markdown
---
test_run_id: TR-005
title: Test Run for Sprint 5
test_plan_id: TP-001
execution_date: "2023-11-13"
executed_by: "QA Team"
status: Completed
results:
  - RES-001
  - RES-002
  - RES-003
tags:
  - sprint_5
  - regression
---

# Test Run for Sprint 5

This test run covers the testing efforts for Sprint 5 as part of Release v1.0.

## Included Results

- **[TC-001: Login with Valid Credentials - Passed](../test_results/TC-001_login_valid_result_2023-11-13.md)**
- **[TC-002: Login with Invalid Password - Failed](../test_results/TC-002_login_invalid_result_2023-11-13.md)**
- **[TC-003: Login with Empty Fields - Passed](../test_results/TC-003_login_empty_fields_result_2023-11-13.md)**
```

---

## Key Features and Workflow

### 1. **Ingestion of Markdown and Automation Artifacts**
   - Automates ingestion of files into the surveilr `uniform_resource` table.
   - Uses FII codes to link files across test plans, cases, and runs.

### 2. **SQL Query Interface**
   - Provides SQL schema for querying test metrics, test statuses, and historical data.
   - Supports advanced queries, including test coverage and defect tracking.

### 3. **surveilr Web UI**
   - The functionality, including dashboards, test case management, and reporting.

### 4. **Integration and Automation**
   - CI/CD integration triggers automated tests for continuous feedback.
   - API endpoints allow integration with automation tools like Playwright and Postman.

## Commands

### Ingest Markdown Content
```bash
surveilr ingest files -r qualityfolio-service-watchtower-content
```
Post-ingestion, `surveilr` is no longer required, the `qualityfolio-service-content` directory can be
ignored, only `sqlite3` is required because all content is in the
`resource-surveillance.sqlite.db` SQLite database which does not require any
other dependencies.

## Start surveilr Web UI
Post-ingestion, `surveilr` is no longer required, the `ingest` directory can be
ignored, only `sqlite3` is required because all content is in the
`resource-surveillance.sqlite.db` SQLite database which does not require any
other dependencies.

```bash
# load the "Console" and other menu/routing utilities plus FHIR Web UI (both are same, just run one)
$ deno run -A ./package.sql.ts | surveilr shell   # option 1 (same as option 2)
$ surveilr shell ./package.sql.ts                 # option 2 (same as option 1)

# start surveilr web-ui in "watch" mode to re-load package.sql.ts automatically
$ ../../std/surveilrctl.ts dev
# browse http://localhost:9000/ to see surveilr web UI
# browse http://localhost:9000/qltyfolio/info-schema.sql to see DMS-specific schema
```

Once you apply `stateless.sql` you can ignore that files and all content will be
accessed through views or `*.cached` tables in
`resource-surveillance.sqlite.db`. At this point you can rename the SQLite
database file, archive it, use in reporting tools, DBeaver, DataGrip, or any
other SQLite data access tools.

## Testing and Automation

### Run Tests
Execute Deno tests to verify Qualityfolio functionality:
```bash
deno test -A
```

This command creates an `assurance` folder with all test-related data and logs.

## Additional Notes

### Integration with Opsfolio
Qualityfolio aligns with Opsfolio for compliance workflows, supporting high traceability and integrity through SQL-based querying and Markdown documentation. Both systems enable evidence-based management and audit readiness, essential for regulated environments.

This documentation outlines Qualityfolio's structure, components, and workflows, enabling teams to leverage it as a robust, open-source solution for software testing and quality assurance.
