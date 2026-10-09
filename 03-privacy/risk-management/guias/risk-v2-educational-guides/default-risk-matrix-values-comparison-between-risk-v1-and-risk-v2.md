---
title: "Default risk matrix values comparison between Risk V1 and Risk V2"
slug: "default-risk-matrix-values-comparison-between-risk-v1-and-risk-v2"
updated: 2026-04-20T17:44:52Z
published: 2026-04-20T17:44:52Z
canonical: "helpcenter.securiti.ai/default-risk-matrix-values-comparison-between-risk-v1-and-risk-v2"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Default risk matrix values comparison between Risk V1 and Risk V2

## Default risk matrix values in Risk V2

This article explains the default risk configurations applied in Risk V2. These defaults vary based on whether the customer is new or migrated from an existing setup.

## Default types in Risk V2

Risk V2 applies two categories of defaults:

- Net new customers
- Existing migrated customers

## Defaults for net new customers

New customers are assigned a standard set of defaults for both Linear and Matrix risk models.

### Linear defaults

| Risk level | Color | Score |
| --- | --- | --- |
| Very High | Red | 25 |
| High | Orange | 20 |
| Medium | Yellow | 15 |
| Low | Light Green | 10 |
| Very Low | Green | 5 |

### Matrix defaults (5×5)

Matrix scoring is calculated based on likelihood (A to E) and severity (1 to 5).

| Likelihood \ Severity | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- |
| E | 5 | 10 | 15 | 20 | 25 |
| D | 4 | 8 | 12 | 16 | 20 |
| C | 3 | 6 | 9 | 12 | 15 |
| B | 2 | 4 | 6 | 8 | 10 |
| A | 1 | 2 | 3 | 4 | 5 |

## Defaults for existing migrated customers

For migrated customers, defaults depend on the existing configuration. Four scenarios are supported.

### 1. Linear

- Retains a discrete risk scale
- Uses predefined labels, colors, and scores
- Does not use likelihood and severity combinations

### 2. 3×3 matrix

- Likelihood: A to C
- Severity: 1 to 3
- Produces 9 total risk values
- Scores increase progressively across both dimensions

### 3. 4×4 matrix

- Likelihood: A to D
- Severity: 1 to 4
- Produces 16 total risk values
- Enables more granularity than 3×3

### 4. 5×5 matrix

- Likelihood: A to E
- Severity: 1 to 5
- Produces 25 total risk values
- Matches the default configuration for net new customers

## Key differences between Risk V1 and Risk V2

- Risk V2 standardizes default scoring across both Linear and Matrix models.
- Matrix-based scoring is the default selection in Risk V2.
- Migrated customers retain their structural format but align with updated scoring behavior.

## When these defaults apply

- Net new customers receive predefined Linear and 5×5 Matrix defaults.
- Migrated customers retain their structure but are mapped to one of the supported configurations.
