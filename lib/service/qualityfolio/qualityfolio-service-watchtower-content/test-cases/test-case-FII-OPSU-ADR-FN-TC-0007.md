---
test_case_id: FII-OPSU-ADR-FN-TC-0007
title: Check whether the SOC2 TYPE 1 link is redirected to the corresponding page or not.
description: "Verify that the SOC2 TYPE 1 link is redirected to the corresponding page or not."
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

# Check whether the SOC2 TYPE 1 link is redirected to the corresponding page or not.

## Preconditions

- Log in to the Opsfolio application as an admin user.

## Test Steps

1. Login to the Opsfolio Application
2. Redirect to the Opsfolio home page and verify
3. Verify and click on the Audit link from the dashboard header                                         
4. Verify and check the Audit page                
5. Verify and click on the AICPA                    
6. Verify the Audit-AICPA page                        
7. Verify and click on the SOC2 type-1 link [next page arrow button]

## Expected Result

- System should navigate to SOC2 TYPE1 detail page..

