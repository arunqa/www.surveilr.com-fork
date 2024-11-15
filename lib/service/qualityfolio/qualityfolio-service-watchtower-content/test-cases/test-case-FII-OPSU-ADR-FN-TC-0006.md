---
test_case_id: FII-OPSU-ADR-FN-TC-0006
title: Verify that choosing the "See Details" option of SOC2 TYPE 2 leads to the respective details page.
description: "Verify that choosing the See Details option of SOC2 TYPE 2 leads to the respective details page."
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

# Verify that choosing the "See Details" option of SOC2 TYPE 2 leads to the respective details page.

## Preconditions

- Log in to the Opsfolio application as an admin user.

## Test Steps

1. Login to the Opsfolio Application
2. Redirect to the Opsfolio home page and verify
3. Verify and click on the Audit link from the dashboard header                                          
4. Verify and check the Audit page                
5. Click on the AICPA                                   
6. Verify the Audit-AICPA page                        
7. Click on the 'See details' link on the SOC2 type 2 section

## Expected Result

- System should navigate to SOC2 TYPE2 detail page.

