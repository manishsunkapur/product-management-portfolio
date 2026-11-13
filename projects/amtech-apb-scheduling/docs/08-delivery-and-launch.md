# 08 · Delivery and Launch

## Delivery approach

Treat the validated workflow as a small, measurable increment. Preserve the established schedule path until the new proposal is confirmed and applied. Resolve data, permission, and exception handling before broad rollout.

Use the team’s agreed **Scrum** cadence for planning, refinement, demos, and retrospectives. Scrum organizes delivery; it does not replace product discovery, customer validation, outcome decisions, or cross-functional launch readiness.

## Product manager activities through delivery

1. Confirm the target customer workflow and current APB behavior with Product, Implementation, and Support.
2. Review prototype findings and resolve open product decisions with users and stakeholders.
3. Work with Engineering/Architecture on schedule-engine behavior, data contracts, resource rules, permissions, versioning, performance, and failure modes.
4. Prioritize the epic and stories; define non-goals, dependencies, analytics, acceptance criteria, and Definition of Done.
5. Keep the backlog ordered and ready; answer team questions, review demos, and manage scope as new information emerges.
6. Partner with QA on happy paths, stale/conflicting events, no-feasible outcomes, permissions, concurrency, regression, and recovery from failures.
7. Validate delivered behavior against user outcomes and agreed acceptance criteria, not just UI completion.
8. Prepare release notes, help content, implementation guidance, support runbooks, training, pilot controls, and customer communications.

## Proposed rollout phases

| Phase | Purpose | Exit / decision |
|---|---|---|
| Internal validation | Confirm data and current behavior; verify analytics and exception handling | No unresolved critical feasibility or safety issue |
| Design partner pilot | Test with selected, consenting customers and agreed workflow boundaries | Pilot metrics and guardrails meet pre-agreed thresholds |
| Limited release | Expand cautiously, monitor support and customer outcomes | Evidence remains positive across varied configurations |
| General availability | Scale documentation, enablement, support, and product analytics | Product/Engineering/Customer teams ready; rollback path known |

The exact customer count, duration, and feature flags should be chosen with Amtech teams and pilot customers; this case does not invent those operational commitments.

## Release readiness checklist

- Current behavior and affected product versions documented.
- Role permissions and approval policy confirmed.
- Data freshness, schedule versioning, and failure states tested.
- Analytics events validated against metric definitions.
- Customer workflow and rollback/fallback confirmed.
- Support, implementation, and customer-facing teams enabled.
- User guidance and release notes ready.
- Pilot owner, escalation path, and review cadence set.
- Success thresholds and stop conditions agreed before rollout.

