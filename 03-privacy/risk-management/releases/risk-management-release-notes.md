---
title: "Risk Management release notes"
slug: "risk-management-release-notes"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/risk-management-release-notes"
area: privacy
modulo: risk-management
tipo: release
data_captura: 2026-10-08
---

# Risk Management release notes

## 1.151

### Release updates - September 2026

#### Introducing the Controls Register in Risk Management

Securiti now lets you use the new Controls Register in Risk Management to link controls directly to the risks they manage. It lets you record and track mitigation work after the initial risk assessment. Create a control from a risk's details page or from the Controls Register itself. Track its status through implementation and record its effectiveness using the risk level or the severity and likelihood scales configured in your risk settings. Once a control reaches the "Implemented" status, Securiti factors its effectiveness into the risk's residual score.

For more information, see [Controls Register](/latest/docs/using-controls-register).

#### API updates

Use the following table to understand the API updates made for Risk Management in this release:

| Endpoint | Method | What's changed |
| --- | --- | --- |
| `/privaci/v1/user/assessments/control` | GET | We have added this API endpoint in the current release. It lets you fetch a list of all controls, with support for filtering by owner, reviewer, linked risk, compliance framework, compliance control, and tags. |
| `/privaci/v1/user/assessments/control/{id}` | GET | We have added this API endpoint in the current release. It lets you fetch a single control by its ID. |
| `/privaci/v1/user/assessments/control` | POST | We have added this API endpoint in the current release. It lets you create a new control, optionally linking it to risks, compliance frameworks, owners, and reviewers. |
| `/privaci/v1/user/assessments/control/{id}` | PATCH | We have added this API endpoint in the current release. It lets you update an existing control's fields, status, effectiveness rating, and linked risks, owners, reviewers, tags, and attachments. |
| `/privaci/v1/user/assessments/control/{id}` | DELETE | We have added this API endpoint in the current release. It lets you delete a control. |
| `/privaci/v1/user/assessments/control/attachment` | POST | We have added this API endpoint in the current release. It lets you upload a file as a control attachment. |
| `/privaci/v1/user/assessments/control/attachment` | GET | We have added this API endpoint in the current release. It lets you fetch short-lived signed URLs to download one or more control attachments. |
| `/privaci/v1/user/assessments/control/export` | POST | We have added this API endpoint in the current release. It lets you export controls to a `CSV` file, delivered by email once ready. |
| `/privaci/v1/user/assessments/control/export-evidence` | POST | We have added this API endpoint in the current release. It lets you export a control's attachments, comments, and links bundled together as `.zip`. |
| `/privaci/v1/user/assessments/control/import` | GET | We have added this API endpoint in the current release. It lets you download a sample `CSV` file showing the expected format for importing controls. |
| `/privaci/v1/user/assessments/control/import` | POST | We have added this API endpoint in the current release. It lets you bulk import controls from a `CSV` file. |
| `/privaci/v1/user/comments/{entityType}/{entityId}` | GET | We have added this API endpoint in the current release. It lets you fetch all comments on an entity, such as a control. |
| `/privaci/v1/user/comments` | POST | We have added this API endpoint in the current release. It lets you create a comment on an entity. |
| `/privaci/v1/user/comments/{commentId}` | PATCH | We have added this API endpoint in the current release. It lets you update an existing comment. |
| `/privaci/v1/user/comments/{commentId}` | DELETE | We have added this API endpoint in the current release. It lets you delete a comment. |
| `/privaci/v1/user/comments/{entityType}/{entityId}/counts` | GET | We have added this API endpoint in the current release. It lets you fetch your unread comment count and mention count on an entity. |
| `/privaci/v1/user/comments/{entityType}/{entityId}/mark-read` | POST | We have added this API endpoint in the current release. It lets you mark all comments on an entity as read. |
| `/privaci/v1/user/comments/attachments` | POST | We have added this API endpoint in the current release. It lets you upload a file as a comment attachment, without linking it to a comment yet. |
| `/privaci/v1/user/comments/attachments/{commentId}` | POST | We have added this API endpoint in the current release. It lets you upload a file and link it to an existing comment in one step. |
| `/privaci/v1/user/comments/attachments/{attachmentId}` | DELETE | We have added this API endpoint in the current release. It lets you delete a comment attachment. |
| `/privaci/v1/user/comments/attachments` | GET | We have added this API endpoint in the current release. It lets you fetch short-lived signed URLs to download one or more comment attachments. |

For more information, see [Risk Management API reference](https://securiti-doc-router.securiti.ai/modules/risk-register/apidocs/index.html).

---

## 1.150

### Release updates - August 2026

#### Introducing RBAC v2 for Risk Management

Securiti has introduced Role-Based Access Control (RBAC) v2 for Risk Management. This replaces hardcoded role checks with fine-grained, action-based permissions, so you can build custom roles scoped to exactly what each job needs. The new permissions cover assessment templates, questions, responses, and risk settings. Previously, only Access Profiles governed access to these modules. You can now select granular permissions for actions such as viewing, creating, or approving assessments and risks.

For more information, see [Risk RBAC permissions](/latest/docs/risk-management-rbac-permissions).

#### Resolved issue

- Fixed an issue where risk register list displays initial risk level instead of correct aggregate (inherent or residual) risk level when using the Risk Matrix (PRIV-249646).

---

## 1.149

### Release updates - August 2026

#### Risk Metrics Dashboard

Securiti now includes a risk dashboard under Risk Management. The dashboard displays risk data through nine widgets. Clicking a slice or segment on any widget opens a pre-filtered view. Each widget can also be expanded to a fullscreen view.

For more information, see [Risk Metrics Dashboard](/latest/docs/navigating-the-risk-metrics-dashboard).

#### Message digest for risk-flagged notifications

Securiti now supports message digest for risk flagged notifications. When a user is assigned to multiple risks in a day, Securiti groups notification emails according to each user's notification preference. Users with digest disabled receive one email per flagged risk. Users configured for hourly or daily digest receive a single collated email per the configured interval.

For more information, see [Message digest notifications](/latest/docs/assessment-v2-system-and-message-digest-email-notifications).

#### Flexible cell remapping when resizing the risk matrix

Securiti now lets you remap any cell when resizing the risk matrix. When reducing the matrix size, Securiti pre-maps overlapping cells by default and you can optionally remap them. You must manually remap any cells unique to the previous matrix. When increasing the matrix size, Securiti pre-maps all existing cells by default, and you can remap any cell.

For more information, see [Configuring risk settings](/latest/docs/configuring-settings-in-risk-v2).

#### Including recommendation text in risk register search

Securiti now includes recommendation text in risk register search results. Search queries return matches found in the Recommendation field.

#### Matrix editor retain unsaved values when changing matrix dimensions

Securiti now retains any unsaved cell values that exist in the matrix editor when you change the matrix dimensions.

---

## 1.148

### Release updates - July 2026

#### Risk Settings in Risk V2

Securiti now lets Risk Admins configure risk settings in Risk V2. You can choose between Linear or Risk Matrix, edit risk configuration, customize risk matrix, and select an aggregation methodology.

When a risk level label, score, or matrix cell score changes, existing risks update to reflect the new value for both inherent and residual risk, and aggregate values recalculate automatically. New risks created after the change use the updated values by default.

Note: While recalculation is in progress, risk settings are locked from editing.

For more information, see [Configuring risk settings](/latest/docs/configuring-settings-in-risk-v2).

---

## 1.147

### Release updates - June 2026

No updates
