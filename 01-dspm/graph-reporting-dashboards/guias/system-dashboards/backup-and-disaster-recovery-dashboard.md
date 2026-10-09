---
title: "Backup and Disaster Recovery dashboard"
slug: "backup-and-disaster-recovery-dashboard"
updated: 2026-06-08T12:44:05Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/backup-and-disaster-recovery-dashboard"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Backup and Disaster Recovery dashboard

The **Backup and Disaster Recovery** dashboard provides a centralized view of your organization’s Business Continuity (BC) and Disaster Recovery (DR) readiness within the Compliance module. With this dashboard, compliance, risk, and IT teams can monitor documented plans, training, testing coverage, and technical safeguards such as replication and backups.

The dashboard lets you view insights for all your projects or a specific project including:

- Monitoring overall BC/DR readiness across projects and frameworks
- Tracking attestation coverage for documented plans, training, and testing
- Validating technical safeguards such as system replication and daily backups
- Reviewing framework pass percentage and identify control gaps

![Dashboard displaying backup and disaster recovery metrics and project statuses for compliance.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/backupanddisasterrecovery_dashboard.png)

The table below provides an overview of the predefined widgets in the Backup and Disaster Recovery dashboard.

| Widget Title | Widget Type | Description |
| --- | --- | --- |
| Frameworks | Grid | Displays the total number of frameworks mapped to BC/DR controls. |
| Controls | Grid | Displays the total number of controls mapped to BC/DR controls. |
| Attestation Tests | Grid | Displays the total number of attestation-based tests related to Business Continuity and Disaster Recovery controls. |
| BC-02: Disaster Recovery System Replication | Grid | Displays the status of Failed Data Volume and Failed Data Systems with reference to critical system replication to a disaster recovery center. |
| BC-03: Active Backups | Grid | Displays the status of Failed Data Volume and Failed Data Systems with reference to daily backups for critical system components. |
| Project Status | Chart | Displays the status of BC/DR projects (Complete, In Progress and Under Review) to quickly assess overall progress. |
| Frameworks | Chart | Displays the passed percentage of business continuity control tests against each framework. |
| Business Continuity & Backup Readiness (Based on Attestation) | Chart | Displays the target controls for manual attestations related to Business Continuity (BC) and Disaster Recovery (DR). It provides: - Passed percentage - Number of tests against each control - An executive-level summary of the results. Target controls focus on ensuring the organization maintains documented, annually approved and tested BC/DR plans, provides training to relevant stakeholders, and performs annual testing of recovery strategies. They also verify that the organization has alternate processing capabilities with similar capacity to the primary site and has established agreements with service providers and alternate technology/telecommunication providers to ensure service continuity during disruptions. |
| Business Continuity & Backup Readiness (Based on Attestation) Metrics | Chart | Provides the organizational-level visibility into preparedness, confirming through metrics that Business Continuity and Disaster Recovery plans exist, are maintained, and are regularly tested. These include Passed Percentage of tests and the number of Passed Tests. |
| Business Continuity & Backup Readiness (Based on Technical Controls) | Chart | Displays the target controls for technical disaster recovery readiness for the service continuity in the event of a disruption. Target Controls: - BC-02: Critical system components are replicated in a disaster recovery center to enable resumption of services in case of a disaster. - BC-03: Backups of critical system components are performed at least daily. |
| Business Continuity & Backup Readiness (Based on Technical Controls) Metrics | Chart | Provides visibility into how well your technical disaster recovery and back up controls are performing, based on actual system data. For each control, it displays: - Compliance percentage - Number of passed vs. total tests - Data volume covered - Number of systems or assets evaluate |
| Critical Systems Replicated Across Multiple Availability Zones | Grid | Provides visibility into the organization’s structural resilience for BC-02 target controls. Key insights include: - Failed Data Systems Count - Data Systems Failure - Data Systems Failure with Sensitive Data - Passed Tests Coverage - Failed Tests Coverage - Score Trend - Data Systems Failure Trend |
| Critical Systems being Actively Backed up | Grid | Delivers a critical technical resilience metric to the executive team by validating our ability to perform granular, near-instantaneous data restoration for our most essential assets. Key insights include: - Failed Data Systems Count - Data Systems Failure - Data Systems Failure with Sensitive Data - Passed Tests Coverage - Failed Tests Coverage - Score Trend - Data Systems Failure Trend |
