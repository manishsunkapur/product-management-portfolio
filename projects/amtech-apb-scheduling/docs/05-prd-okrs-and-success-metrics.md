# 05 · Product Requirements Document, OKRs, and Success Metrics

## PRD snapshot

**Feature concept:** Planner review of a downtime-driven schedule recovery proposal.

**Status:** Discovery hypothesis; not approved or committed product scope.

**Problem and users:** See [Problem Statement and JTBD](02-problem-statement-and-jtbd.md). Requirements remain candidate until [discovery and requirements gathering](03-discovery-and-requirements.md) confirms the workflow and current APB behavior.

**Goal:** Help production schedulers recover from downtime faster while maintaining a feasible, trusted, and stable lineup.

**Candidate scope:** Compare current and proposed schedules; identify affected jobs; show delivery, setup, constraint, and input-freshness information; support authorized apply, adjust, or defer; preserve clear state when inputs are stale or no feasible proposal exists.

**Non-goals:** Autonomous publication, predictive maintenance, machine-vision integration, generic ERP redesign, and unvalidated multi-option optimization.

**Dependencies to resolve:** Current APB behavior and configuration; scheduling-engine inputs and performance; production-data freshness; permissions and audit policy; plant schedule communication; metric/event availability.

**Open product decisions:** What event qualifies as verified downtime? Which constraints are hard? What does “at risk” mean per customer? Who can apply? When should a proposal be invalidated? What is the accepted recovery-time baseline?

The detailed candidate requirements are in [Discovery and Requirements](03-discovery-and-requirements.md), the first backlog stories are in [User Stories and Acceptance Criteria](07-user-stories-and-acceptance.md), and the prototype is in [`../prototype/index.html`](../prototype/index.html).

## Product objective

**Help production schedulers recover from downtime faster while maintaining a feasible, trusted, and stable lineup.**

The objective is a candidate for a limited customer pilot, not an Amtech company commitment.

## Proposed pilot key results

Set the final targets with participating customers after establishing a baseline. The figures below are example targets for the work sample and must be validated before launch.

1. **Recovery speed:** Reduce median time from a verified downtime event to an applied feasible schedule by **20% versus the participating plant’s baseline** during the pilot.
2. **Decision quality:** At least **90% of applied proposals** in the pilot have inputs within the customer-agreed freshness threshold and no violated hard constraints.
3. **Usability:** At least **4 of 5 representative schedulers** in moderated prototype sessions complete the core review-and-decision tasks without facilitator help and correctly explain the main trade-off. Adjust the sample size and threshold to the research plan; this is a usability signal, not statistical proof.

## Guardrails

- On-time delivery for affected jobs does not fall below a customer-agreed tolerance versus baseline.
- Post-application schedule churn does not increase beyond a customer-agreed tolerance.
- No proposal with a known violated hard constraint is applied.
- Stale or conflicting inputs are surfaced, not silently accepted.
- Planner override, defer, and failure reasons remain visible for product learning.

## Metric definitions

| Metric | Definition | Why it matters |
|---|---|---|
| Downtime-to-applied-feasible schedule | Time from verified event to successful application of a feasible schedule | Primary recovery outcome |
| Proposal freshness compliance | Proposals with inputs within agreed freshness threshold ÷ proposals applied | Trust in input data |
| Hard-constraint violation rate | Applied proposals with a known hard-constraint violation ÷ applied proposals | Safety and feasibility guardrail; target zero |
| Proposal adjustment/defer rate | Edited or deferred proposals ÷ reviewed proposals | Reveals preference mismatch or missing information; not inherently bad |
| Post-application schedule churn | Additional changes after application within a customer-defined observation window | Stability guardrail |
| Affected-order on-time delivery | Affected orders delivered by the customer-defined commitment ÷ affected orders | Customer outcome guardrail |
| Unassisted prototype task completion | Participants who complete the defined task without facilitator intervention ÷ participants tested | Prototype usability signal |

## Baseline and target-setting

Before the pilot, agree with each customer on the event start/end definitions, affected-order logic, observation window, schedule version, due-date source, and acceptable tolerance. Segment results by plant, resource type, event type, and workflow only where sample sizes and data quality support it. Do not set external targets from synthetic prototype data.

## Decision rule

Expand only if the primary recovery measure improves against baseline and delivery, feasibility, data freshness, and schedule-stability guardrails remain within agreed limits. Revise if users value the concept but the workflow or explanations are weak. Stop or redirect if the problem is uncommon, data cannot be trusted, or operational risk rises.

