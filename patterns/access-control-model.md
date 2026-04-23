# Access Control Model for Governed Data Platforms

## Overview

This pattern defines how access should be structured across governed data platforms in regulated environments.

The objective is not simply to restrict access. It is to ensure that access is aligned to data sensitivity, layer purpose, user role, and approved usage context.

A strong access control model enables platforms to scale safely while reducing ambiguity in who can access what, at what level, and for what purpose.

## Why This Pattern Matters

Many data platforms apply access control inconsistently:
- broad access to raw and curated layers
- weak separation between engineering and consumption paths
- unclear handling of sensitive or regulated data
- manual exceptions that do not scale

This leads to:
- unnecessary exposure of sensitive data
- inconsistent user experiences across domains
- audit and compliance risk
- weak confidence in downstream AI and analytics use

## Pattern Objective

The goal of this pattern is to establish a reusable access model that:

- follows least-privilege principles
- aligns access with layer responsibilities
- supports controlled consumption paths
- reduces unnecessary exposure to sensitive data
- scales across teams and domains

## Core Access Principles

### 1. Least Privilege
Users and systems should only receive the minimum level of access needed for their approved purpose.

### 2. Layer-Aware Access
Access should differ across Bronze, Silver, and Gold based on the role of each layer.

### 3. Domain-Aware Control
Access should be aligned to business domain ownership and approved usage boundaries.

### 4. Sensitive Data Handling
Sensitive, regulated, or restricted data should require stronger controls than general-purpose data.

### 5. Controlled Consumption
Most users should consume curated and approved outputs rather than accessing lower-level layers directly.

## Layer-Specific Access Model

## Bronze Layer — Source-Aligned Ingestion

### Access Intent
Highly restricted.

### Typical Access Model
- platform ingestion processes
- limited engineering and operations roles
- tightly controlled troubleshooting access

### Why
Bronze contains raw or near-raw source-aligned data and often includes the highest sensitivity exposure.

### Control Expectations
- restricted raw-zone access
- explicit operational need for access
- source traceability retained
- minimal broad user access

---

## Silver Layer — Standardization and Validation

### Access Intent
Restricted but broader than Bronze.

### Typical Access Model
- data engineering and platform teams
- governance and data quality functions
- limited domain-aligned technical users

### Why
Silver contains validated and standardized data but may still include sensitive fields or partially transformed content requiring controlled handling.

### Control Expectations
- role-based access by technical function
- policy-aligned access to sensitive data elements
- controlled transformation and validation access
- fewer broad consumption paths

---

## Gold Layer — Curated Consumption

### Access Intent
Broadest approved access, but still governed.

### Typical Access Model
- analysts
- reporting users
- approved downstream applications
- governed AI and retrieval workloads

### Why
Gold should provide stable, business-ready, and governed access paths that reduce the need for broad lower-layer access.

### Control Expectations
- curated and role-appropriate access
- business-aligned datasets and interfaces
- governed downstream use
- AI and retrieval access restricted to approved outputs

## Access Control Dimensions

A reusable access model should evaluate access across multiple dimensions:

- user role
- business function
- domain ownership
- data sensitivity
- layer location
- approved usage context
- platform or workload type

This helps prevent simplistic models where access is granted too broadly based on only one factor.

## Preferred Consumption Model

The platform should guide users toward approved access paths:

- analytics and reporting should consume curated datasets
- domain consumers should use approved business-ready structures
- AI workloads should use access-scoped and governed retrieval paths
- raw-layer access should remain limited and exception-based

## Benefits

- reduces unnecessary exposure to sensitive data
- improves consistency across teams and domains
- supports clearer audit and review processes
- strengthens downstream trust in analytics and AI use
- scales more effectively than manual exceptions

## What Not to Do

Avoid these weak patterns:
- granting broad raw-layer access by default
- using the same access model across all layers
- relying on manual exceptions as the normal access path
- exposing AI systems to unrestricted lower-layer content
- treating curated access as optional rather than preferred

---

This pattern supports governed platform growth by ensuring that access control is designed as a reusable architecture capability rather than a series of one-off permission decisions.
