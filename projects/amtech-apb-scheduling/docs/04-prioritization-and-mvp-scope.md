# 04 · Prioritization and MVP Scope

## Alternatives considered

| Option | What it does | Strength | Risk / learning need |
|---|---|---|---|
| A · Improve event visibility | Make disruption and affected jobs easier to find in the existing schedule | Small, potentially quick to validate | May not help the planner choose between trade-offs |
| B · Explain and review a recovery proposal | Compare current/proposed lineups, show operational impact, and let an authorized planner decide | Addresses understanding and control while preserving human review | Depends on reliable data, explainable constraints, and clear approval rules |
| C · Automatically publish the new schedule | Recalculate and publish with little or no planner review | Could reduce handling time for proven, routine cases | Higher operational risk; automation policy and exceptions must be understood first |

## Candidate first slice

Test **Option B** if discovery confirms that proposal understanding and decision-making are the main pain. It is a contained way to learn what schedulers need to trust a recovery plan before considering broader automation.

## Feature prioritization

| Priority | Feature | Reason | Evidence / dependency |
|---|---|---|---|
| Must test in prototype | Current vs proposed schedule comparison | Directly supports understanding what changed | Confirm the best comparison layout with schedulers |
| Must test in prototype | Affected jobs, delivery risk, setup impact, and constraint explanation | Makes trade-offs reviewable | Validate rules and data availability; label estimates |
| Must test in prototype | Event time and input freshness | Helps users judge whether a plan is current | Confirm data sources and customer freshness thresholds |
| Must test in prototype | Apply / adjust / defer decision states | Tests user control and decision workflow | Confirm roles, permissions, and publication behavior |
| Must test as exception state | Stale inputs or no feasible proposal | Prevents false confidence and reveals recovery path | Confirm system behavior with Engineering and users |
| Should build if validated | New schedule version and decision history | Supports shift handoff, support, and traceability | Confirm audit needs and existing APB capabilities |
| Could add after discovery | Compare multiple schedule options | Helps users choose between delivery and setup trade-offs | Test whether one proposal is insufficient and how options should rank |
| Could add after discovery | Configurable priority weights / what-if controls | Could fit different plant policies | Measure configuration complexity and user demand |
| Could add later | Shift notifications or acknowledgements | May improve adoption and handoff | Map current screens, displays, integrations, and notification ownership |
| Could add later | Learn from actual run performance | Could improve estimates over time | Requires clean outcome data and a safe feedback method |
| Won’t for this case | Auto-publish, predictive maintenance, AI-generated advice, machine-vision integration | Adds risk or unrelated complexity before the core problem is proven | Revisit only with separate evidence and product strategy |

## Feature recommendation

The prototype should add **a clear current-versus-proposed comparison, a short “why this plan” explanation, and explicit stale/no-feasible states**. These close gaps in the current concept and are needed to test trust and decision quality. Do not add full multi-option optimization or automated publication until discovery shows that users need them and the product can support them safely.

## Prioritization method

Prioritize with customer reach, severity/frequency, strategic fit, expected outcome, confidence, effort, business viability, and operational risk. Do not score with made-up numbers. Revisit the order after interviews, current-product review, prototype tests, market/alternative review, and technical feasibility.

## Lightweight business case

Estimate the customer cost of the validated problem using customer evidence: event frequency, recovery time, affected roles, delivery/service impact, and schedule disruption. Compare the expected customer value with engineering effort, implementation/configuration cost, ongoing support burden, and operational risk. Consider commercial fit (retention, expansion, or competitive need) only where Amtech has evidence. Document uncertainty and assumptions; do not claim ROI from synthetic data.

### Framework fit

- Use **RICE** = (Reach × Impact × Confidence) ÷ Effort when there is credible data for reach and effort and comparable opportunities. Here, those inputs are not yet known, so the work sample intentionally avoids a fabricated RICE score.
- Use **MoSCoW** to make the validated MVP boundary visible: Must, Should, Could, Won’t for now. It is a scope conversation, not a substitute for comparing strategic opportunities.
- Use the **Opportunity Solution Tree** during discovery to link an outcome to opportunities and experiments; use prioritization after those opportunities are better evidenced.
