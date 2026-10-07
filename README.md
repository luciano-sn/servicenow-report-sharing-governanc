# ServiceNow – Report Sharing Governance

## Overview

This project presents a ServiceNow solution developed to identify and remove
report sharing records associated with groups that do not have active users.

The solution addresses the platform finding:

> "Report shared with a group which has no users"

## Business Objective

Improve report-sharing governance by removing obsolete sharing configurations
while preserving valid sharing relationships.

## Technical Approach

The solution analyzes the following ServiceNow tables:

- `sys_report_users_groups`
- `sys_user_grmember`
- `sys_user`

The validation follows this rule:

1. Identify report sharing records associated with a group.
2. Check whether the group has at least one active user.
3. Keep the sharing when an active user exists.
4. Remove the sharing when no active user exists.
5. Validate the environment after execution.

## Important Considerations

Direct user sharing records are not affected.

Only records with a populated `group_id` are analyzed.

Users with `active = false` are not considered active members for this
validation.

## Solution

The repository contains:

- Fix Script for the data correction
- Pre-execution validation
- Post-execution validation
- Technical documentation

## Validation

The expected result after execution is:

    Quantidade total de candidatos: 0

This indicates that no report-sharing records remain associated with groups
without active users.

## Technologies

- ServiceNow
- GlideRecord
- JavaScript
- Fix Scripts
- Background Scripts
- ServiceNow Platform Governance

## Disclaimer

This project contains a sanitized and generic implementation.
No confidential company data, credentials, production Sys IDs, or proprietary
information are included.
