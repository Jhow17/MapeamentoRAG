---
title: "Transitioning from Risk V1 to Risk V2"
slug: "transitioning-from-risk-v1-to-risk-v2"
updated: 2026-06-16T07:40:31Z
published: 2026-06-16T07:40:31Z
canonical: "helpcenter.securiti.ai/transitioning-from-risk-v1-to-risk-v2"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Transitioning from Risk V1 to Risk V2

Risk V2 introduces a unified risk model so you can standardize how you score, track, and report risks across the organization.

You can configure scoring in Risk V2 using Linear or Risk Matrix frameworks, configurable risk levels, and aggregation logic to help you view risk at both an individual and program level.

> [!NOTE]
> Note
> 
> This content explains what’s changing in Risk V2. We’ll release step-by-step guidance as more workflows roll out.

### What stays the same during the transition

When you upgrade to Risk V2:

- Your existing risk statues, assignments, and remediations are copied as-is.
- Your risk history is preserved.
- You can still flag risks in the assessment.
- Risk statuses and lifecycle stay the same.

### Data migration from Risk V1 to Risk V2

A key difference between Risk V1 and V2 is the consistency of risk methodology across your register. In Risk V1, risks could span across linear risks, 3x3 matrix, and 5x5 matrix. This creates confusion for organizations who need a clear comparison of risks to help ensure correct priority.

Risk V2 will support a single global risk framework for all risks in your tenant. When moving from Risk V1 to Risk V2, Securiti will automatically align your risks to a single framework.

You will be able to further customize the risk framework in a follow up release.

#### How risks will be upgraded

The risk framework selected will be reflected based on your current risk settings. All risks will then be updated to reflect the new risk settings.

You can see an example scenario of how Securiti will handle the update on your behalf. In this scenario, the organization has their V1 settings configured to 5×5 matrix and has a few 3×3 and 5×5 risks in their register. This table outlines what happens to each of those risks.

**Step 1: Determine the target Risk V2 settings**

| Risk V1 Settings | Risk V2 Settings | Result |
| --- | --- | --- |
| 3×3 Matrix | 3×3 Matrix | Risk V2 settings will copy the risk score of 3×3 matrix from Risk V1 |
| 4×4 Matrix | 4×4 Matrix | Risk V2 settings will copy the risk score of 4×4 matrix from Risk V1 |
| 5×5 Matrix | 5×5 Matrix | Risk V2 settings will copy the risk score of 5×5 matrix from Risk V1 |

**Step 2: Determine any required matrix mappings**

| **V1** Source Risk | V2 Target Risk | Result |
| --- | --- | --- |
| 3×3 Matrix | 5×5 Matrix | The risk scores are updated per the 3×3 to 5×5 mapping below. |
| 5×5 Matrix | 5×5 Matrix | Risk scores are copied as-is. |

**Step 3: Apply mapping**

| Severity \ Likelihood | Low | Medium | High |
| --- | --- | --- | --- |
| Low | 3 → 1 | 6 → 2 | 8 → 3 |
| Medium | 6 → 2 | 11 → 4 | 17 → 6 |
| High | 8 → 3 | 17 → 6 | 25 → 9 |

This approach allows organizations to transition to Risk V2 without losing their existing scoring context while giving them the option to expand the scoring model if needed. By preserving existing matrix structures and mapping values into the updated framework, Risk V2 maintains continuity for historical risk data while allowing organizations to refine their scoring configuration over time.

### What changes in Risk V2

Risk V2 introduces updates across how you configure risk scoring, how you score risks, and how you track remediation and reporting. These updates include:

- New Risk Settings for configuring Linear or Risk Matrix scoring
- Custom risk levels and score thresholds (Very High to Very Low)
- Risk aggregation methodology (Sum, Mean, Median)
- Expanded risk detail view with linked objects, trend, relationship graph, and activities
- Remediation and exception workflows tied to risk activities and audit history
- Risk register and risk metrics dashboard views for program-level reporting

---

## Linear vs Risk Matrix risk

You can score risks in two ways in Risk V2: Linear and Risk Matrix. Both frameworks help you score risks consistently, but they differ in how Risk V2 represents risk severity and how users interact with scoring in the product.

### What is changing

- Risk V2 lets you choose a scoring framework in Risk Settings: Linear or Risk Matrix.
- Risk V2 supports a unified risk model so you can manage risks consistently, even when you use different scoring frameworks across programs.
- Risk V2 introduces Risk Matrix setup options so you can define how the matrix behaves for your organization.

### What customers should understand

#### Linear risk

- Linear risk uses a single scale to represent risk severity.
- Each risk maps to one score and one risk level, such as Very High, High, Medium, Low, or Very Low.
- Linear scoring works well when teams want a straightforward severity model and consistent classification across many risks.

#### Risk Matrix risk

- Risk Matrix scoring uses a two-dimensional grid to represent risk severity based on two dimensions:
  - Likelihood (Y-axis)
  - Severity (X-axis)
- Each position in the matrix maps to a numeric score that Risk V2 uses to determine the risk level.
- You can configure the matrix size within supported limits, with a minimum grid of 3x3 and a maximum grid of 10x10.
- Risk V2 also lets you define labels for likelihood and severity, so scoring aligns with how your organization describes risk conditions.

### How Risk V2 keeps score consistent

Regardless of whether you choose Linear or Risk Matrix scoring:

- Risk V2 classifies risks into risk levels using your configured thresholds.
- Risk V2 uses aggregation methodology to roll up risk outcomes across linked risks and scopes.
- Risk V2 supports inherent risk and residual risk views so teams can evaluate exposure before and after remediation.

### Why it matters

- Teams can score risks in a way that matches their existing program model without losing the ability to report consistently.
- A consistent mapping between scores and risk levels helps stakeholders compare risks across assessments, assets, vendors, processes, and other linked objects.

### Related glossary terms

- Risk framework
- Linear risk
- Risk Matrix risk
- Likelihood
- Severity
- Risk score
- Risk level

---

## Risk levels, risk score, and Max Risk Range

You can use configurable risk levels to interpret risk consistently across scoring, reporting, and remediation workflows. Each risk level maps to a numeric threshold that determines how Risk V2 classifies and displays risk severity.

### What is changing

- Risk V2 introduces configurable risk level labels such as Very High, High, Medium, Low, and Very Low.
- Risk V2 assigns a numeric score threshold to each risk level.
- You can configure Max Risk Range to define the numeric ceiling for risk scoring.

### What customers should understand

- Risk V2 uses risk scores to represent risk severity numerically.
- Risk levels help translate numeric risk scores into consistent categories for decision-making and reporting.
- Max Risk Range defines the upper boundary of your scoring model so the system can classify scores into your configured risk levels.

### Why it matters

- Risk scoring stays consistent across different types of risks and linked objects.
- Teams can apply the same severity interpretation across dashboards, risk register views, and remediation workflows.

### Related glossary terms

- Risk score
- Risk level
- Max Risk Range

---

## Risk aggregation methodology

Risk aggregation helps you calculate an overall risk outcome when multiple risks contribute to the same object or scope. For example, a single assessment, asset, vendor, or process can have multiple associated risks, and aggregation determines how Risk V2 summarizes those risks at the roll-up level.

### What is changing

- You can choose an aggregation methodology: Sum, Mean, or Median.
- Risk V2 uses your risk level thresholds to classify aggregated risk results as Very High, High, Medium, Low, or Very Low.
- Risk V2 aligns aggregation inputs with your Max Risk Range configuration so results stay consistent with your scoring model.

### What customers should understand

- Aggregation determines how Risk V2 summarizes multiple risks into an overall result.
- Each methodology produces a different outcome depending on what you want the roll-up to represent:
  - The sum shows cumulative exposure across items.
  - Mean shows the average exposure across items.
  - Median shows the middle score and reduces the effect of outliers.
  - Max highlights the highest individual risk contributing to the roll-up.

### Why it matters

- Teams can choose the roll-up method that matches how they report risk at the program level.
- Aggregation supports consistent reporting for aggregated inherent risk and aggregated residual risk.
- Risk V2 can show risk breakdown by level to make roll-ups easier to interpret.

### Related glossary terms

- Risk aggregation
- Aggregation methodology
- Sum
- Mean
- Median
- Max
- Risk level
- Max Risk Range

---

## Risk lifecycle and risk statuses

Risk V2 strengthens how you track risk progression over time by tying risk scoring, remediation activity, and exception decisions into a single model. This helps teams understand not only the current severity of a risk, but also what actions are in progress and what decisions have been recorded.

### What is changing

- Risk V2 expands how lifecycle context appears across the risk detail view, risk register, and dashboards.
- Risk V2 makes it easier to track remediation and exception outcomes alongside inherent and residual risk.

### What customers should understand

Risk lifecycle represents how a risk moves from identification to an outcome, such as remediation or retention. In the product today, you may already use Risk Status values as filters to organize and report on risks in the risk register and dashboards.

These Risk Status values help teams sort risks based on remediation and exception context, for example:

- Flagged
- Reduced Pending
- Reduced
- Retained Pending
- Retained Extended
- Retained

Risk V2 builds on this approach by keeping lifecycle context visible so teams can review risk decisions, track progress, and report consistently across the program.

### Why it matters

- Teams can filter and report on risks using consistent lifecycle signals.
- Stakeholders can track remediation and exception outcomes without relying on informal updates.

### Related glossary terms

- Risk lifecycle
- Risk status
- Flagged
- Reduced Pending
- Reduced
- Retained Pending
- Retained Extended
- Retained

---

## Risk remediation and exceptions

You can track remediation workflows in a more structured way through proposed remediation and review flows. It also supports exception workflows for cases where the business formally requests a deviation from remediation expectations.

### What is changing

- Risk V2 introduces structured remediation workflows through proposed remediation and review flows.
- You can attach evidence to remediation, including links and uploaded files.
- Risk V2 supports exception activities alongside remediation activities.
- Risk V2 can reflect remediation and exception history in risk activities and audit logs.

### What customers should understand

#### Risk remediation

- Remediation captures the actions the organization plans to take to reduce risk exposure.
- Risk V2 lets teams propose remediation, attach evidence, and route remediation through a review and approval flow.

#### Risk exceptions

- Exceptions capture cases where the business requests approval to accept or defer remediation.
- Risk V2 tracks exception activity so stakeholders can review what was requested and what was approved or sent back.

#### Residual risk impact

- Risk V2 can show the current residual risk level and a projected residual risk level when remediation decisions change expected risk outcomes.
- This supports a clearer view of what risk remains after remediation.

#### Why it matters

- Teams can standardize how they document remediation work across recurring risk scenarios.
- Evidence attachments support audit readiness and traceability.
- Remediation and exceptions help distinguish between risks being reduced and risks being accepted as-is.

### Remediation activities

Remediation activities represent the actions taken to address an identified risk. A remediation activity documents the proposed action to reduce risk, along with supporting evidence and review outcomes. These activities create a structured record of how risk reduction decisions are evaluated and approved over time.

Remediation activities do not replace risk scoring. Instead, they provide context for how and why residual risk changes.

### Why it matters

Tracking remediation activities helps teams demonstrate progress, validate effectiveness, and maintain accountability across risk programs.

### Related glossary terms

- Risk remediation
- Risk exception
- Evidence
- Residual risk
- Projected residual risk
- Remediation activity

---

## Risk UI updates (risk detail, register, dashboards)

Risk V2 updates the risk experience so users can interpret scoring, linked context, and activity in one place. These updates help users view inherent and residual risk context, see linked objects, and interpret trends over time.

### What is changing

You’ll see updates such as:

- A redesigned risk detail view that combines risk scoring, trend, and linked context
- A risk relationship graph that shows how risk connects to objects such as assessments, vendors, institutions, assets, processes, and controls
- Risk activities and audit logs that capture changes and workflow actions
- A risk register view for centralized reporting across many risks
- A risk metrics dashboard for visual program tracking

### What customers should understand

#### Risk detail view

- Risk V2 shows inherent risk and residual risk side-by-side to support clearer interpretation.
- Risk trend helps teams track how risk changes over time.
- Linked objects provide context for where the risk applies.

#### Risk register

- The risk register provides a centralized view of risks across linked object types.
- It supports reviewing inherent and residual risk levels and the controls linked to each risk.

#### Risk metrics dashboard

- Dashboards summarize risk by status, level, scope, and closure trends.
- This supports program-level visibility across the organization.

#### Why it matters

- Users can interpret risk faster by viewing scoring, relationships, and activities in one place.
- Leaders can track risk posture and progress through roll-ups and trend views.

## Risk owners and reviewers

Risk owners and reviewers define accountability for identifying, managing, and validating risk decisions. Each risk has designated individuals responsible for oversight and decision quality. Risk owners manage the risk and its remediation or exception decisions. Risk reviewers provide an independent review to ensure decisions align with policy and risk appetite.

This separation supports governance by ensuring that risks are not managed or approved in isolation.

### Why it matters

Clear ownership improves follow-through on remediation and helps organizations maintain consistent decision-making across teams and business units.

---

## Audit log

The audit log records how a risk evolves over time. The audit log captures changes made to a risk, including updates to risk scores, ownership, linked objects, remediation decisions, and exceptions. It preserves historical context so teams can understand what changed, when it changed, and who made the change.

This history remains available even as risk definitions, scoring models, or frameworks evolve.

### Why it matters

Audit logs support internal reviews, external audits, and ongoing governance by providing traceability without relying on manual documentation.

### Related glossary terms

- Risk detail page
- Risk register
- Risk metrics dashboard
- Risk trend
- Risk activities
- Audit logs
- Risk owner
- Risk reviewer

---

## Linked objects and linked controls

You can link a risk to the business objects it impacts and the controls used to manage it. This helps teams track where risks apply and how they manage them.

### What is changing

- Risk V2 links risks to objects such as assessments, assets, vendors, processes, and institutions.
- You can link controls to risks so remediation stays connected to governance actions.

### What customers should understand

- Linked objects show where a risk applies so teams can understand the scope.
- Linked controls show what remediation actions the organization uses to manage that risk.
- Together, linked objects and linked controls help create consistent remediation patterns across common risk scenarios.

### Why it matters

- Teams can manage recurring risks more consistently.
- Stakeholders can trace risk ownership, impacted scope, and linked remediation actions in one view.

### Related glossary terms

- Linked objects
- Linked controls
- Controls
- Control monitoring

Proceed to [Risk Management configuration](/latest/docs/using-the-risk-register-list-view).

The risk framework defines how Risk V2 scores risk. Risk V2 supports Linear and Risk Matrix frameworks.

Linear risk uses a single scale to represent overall risk severity.

Risk Matrix uses a two-dimensional grid to score risk based on Likelihood and Severity.

Likelihood represents how probable it is that a risk event or condition will occur.

Severity represents how serious the outcome is if the risk event or condition occurs.

Risk score is the numeric value Risk V2 assigns to represent risk severity.

Risk level groups risks into severity categories such as Very High, High, Medium, Low, and Very Low.

Max Risk Range defines the maximum score value Risk V2 uses for scoring and classification.

Risk aggregation calculates an overall risk result when multiple risks apply to the same scope.

Aggregation methodology defines how Risk V2 calculates aggregated risk results.

Sum adds values together to calculate an aggregated result.

Mean calculates the average value to produce an aggregated result.

Median selects the middle value to produce an aggregated result.

Max selects the highest value to produce an aggregated result.

Risk lifecycle represents how a risk progresses through review, remediation, and exception outcomes over time.

Risk status indicates the current lifecycle state of a risk based on remediation and exception outcomes.

Flagged indicates the risk has been created and requires review or next steps.

Reduced Pending indicates the user has proposed remediation for the risk.

Reduced indicates the remediation outcome has been accepted.

Retained Pending indicates the user has requested an exception for the risk.

Retained Extended indicates the exception has been approved for an extended retention period.

Retained indicates the exception has been approved and the business has chosen to retain the risk.

Risk remediation represents the actions taken or planned to reduce risk exposure.

Risk exception represents a request to retain a risk instead of remediating it.

Evidence represents supporting material attached to remediation or exception activities, such as links or uploaded files.

Residual risk represents the level of risk after applying controls or remediation.

Projected residual risk represents the expected residual risk level after proposed remediation or exceptions take effect.

A documented action proposed or taken to reduce risk, including evidence and review outcomes.

The risk detail page shows a consolidated view of a single risk, including inherent and residual risk scores and levels, linked objects, activities, and audit history.

The risk register provides a centralized view of risks across the program.

The risk metrics dashboard summarizes risk posture and trends using aggregated and lifecycle-based views.

Risk trend shows how a risk score or risk level changes over time.

Risk activities capture key actions and updates performed on a risk over time.

Audit logs record changes to risks and related workflow events for traceability.

The individual responsible for managing a risk, including remediation or exception decisions.

The individual responsible for reviewing and validating risk decisions to ensure alignment with policy and governance requirements.

Linked objects connect a risk to the business entities it applies to, such as assessments, vendors, assets, processes, or institutions.

Linked controls connect a risk to the controls intended to remediate or manage it.

Controls represent defined actions used to reduce, manage, or monitor risk.

Control monitoring tracks control status over time to show remediation progress.

## Related

- [Frequently asked questions (FAQs)](/faq-risk-v2.md)
