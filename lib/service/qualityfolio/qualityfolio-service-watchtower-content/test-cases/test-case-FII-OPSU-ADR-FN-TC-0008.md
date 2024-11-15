---
test_case_id: FII-OPSU-ADR-FN-TC-0008
title: Ensure that the session name field within the "Create new audit session" popup adheres to a uniform character limit.
description: "Verify that the session name field within the Create new audit session popup adheres to a uniform character limit."
priority: High
status: Active
preconditions: 
  - "Log in to the Opsfolio application as an admin user."
created_by: "QA Engineer"
created_date: "2023-11-13"
suite_id: FII-OPSU-FN-TS-0001
tags:
  - login
  - functional
---

# Ensure that the session name field within the "Create new audit session" popup adheres to a uniform character limit.

## Preconditions

- Log in to the Opsfolio application as an admin user.

## Test Steps

1. Login to the Opsfolio Application                   
2. Redirect to the Opsfolio home page and verify
3. Click on the Audit link from the dashboard header                                                                       
4. Click on the AICPA
5. Click on the SOC2 type-1 link                          
6. Verify and press the Create New Audit session button

## Expected Result

- The session name field should adhere to a uniform character limit as specified in the system's requirements, ensuring consistency and preventing issues related to excessively long session names.

