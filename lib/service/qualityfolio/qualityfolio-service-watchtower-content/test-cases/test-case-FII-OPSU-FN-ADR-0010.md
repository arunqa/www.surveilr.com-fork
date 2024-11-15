---
test_case_id: FII-OPSU-FN-ADR-0010
title: Check whether the session name, Tenent, Overall progress, Due Date. Actions of various sessions are displayed in tabular format or not.
description: "Verify that the session name, Tenent, Overall progress, Due Date. Actions of various sessions are displayed in tabular format or not."
priority: High
status: Active
preconditions: 
  - "Log in to the Opsfolio application as an admin user."
created_by: "QA Engineer"
created_date: "2023-11-13"
suite_id: TS_0007
tags:
  - login
  - functional
---

# Check whether the session name, Tenent, Overall progress, Due Date. Actions of various sessions are displayed in tabular format or not.

## Preconditions

- Log in to the Opsfolio application as an admin user.

## Test Steps

1. Login to the Opsfolio Application               
2. Redirect to the Opsfolio home page and verify
3. Click on the Audit link from the dashboard header                                                           
4. Verify and check the Audit page                         
5. Click on the AICPA                                        
6. Verify the Audit-AICPA page                         
7. Click on the SOC2 type-1 link                     
8. Verify and check the various sessions present in the SOC2 type 1 page

## Expected Result

- The system should display the session name, Tenant, Overall Progress, Due Date, and Actions of various sessions in a tabular format.

