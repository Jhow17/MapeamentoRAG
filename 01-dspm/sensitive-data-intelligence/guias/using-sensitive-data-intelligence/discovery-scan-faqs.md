---
title: "Discovery scan FAQs"
slug: "discovery-scan-faqs"
updated: 2026-09-29T11:33:47Z
published: 2026-09-29T11:33:47Z
canonical: "helpcenter.securiti.ai/discovery-scan-faqs"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Discovery scan FAQs

---

### FAQ

### Is there a report that shows which files have been overridden?

Whenever Securiti applies classification labels to a file, it generates a log entry in the policy's logs. If Securiti overrides the file's classification labels, you can see that in the logs section of the policy with the original labels as well. You can view the most recent label assigned to a file and use filters in the [Unstructured Data Scans dashboard](/latest/docs/using-the-unstructured-data-discovery).

### Why is the scan job stuck in a scheduled state?

There could be several reasons for it to happen:

- The pod associated with the scan job is inactive.
- The download worker (task consumer) on the pod is getting ready to process tasks.
- The scan job launch task has not reached the pod.
- The scan job state switch is malfunctioning.
- The scan job launch task on the pod has malfunctioned.
- The scan job launch task is successful, but the pod resources are insufficient for the scan job to start.

### The scan job is running, but nothing is getting scanned. Why?

Possible reasons include:

- The pod is not running or is in an Inactive state.
- API quota limit reached for one or more connectors.
- Producers or consumers are scaled down during an update.
- Multiple scan jobs running in parallel on the same pod may affect task processing.
- Redis is in high utilization (above 50%).
- Disk usage is above 50%.
- A node is unhealthy.

### The scan job is completed on the pod but still running on the portal. Why?

This may be due to post-processing tasks running for the scan job.

### What is the pause-scheduled state?

When a pause is initiated, the scan moves to a pause-scheduled state. It may take some time for the scan to fully transition to the paused state as pending launched tasks must be processed first.

### Why does the pause not take effect instantly?

Some already-launched tasks must be processed before the scan transitions to the paused state.

### Why am I unable to start a scan because the pod is not healthy, even though it shows as Active?

Verify the state of pod services, such as Redis and Elasticsearch from the pod cluster status dashboard.

### Why can't we clone the structured connector's scan job?

Structured data systems can have only one scan job associated with them for table training.

### What happens if the scan is running and the pod goes offline?

Securiti does not update the scan status. The state remains as scheduled or running until the pod is back online.

### What happens if the scan is in a scheduled or running state and the pod goes offline for more than 7 days?

The scan remains in a Scheduled or In-progress state until the pod is back online. After the pod starts, the scan job resumes. If it does not resume within 30 minutes, it is marked as timed out.

### What happens if the scan is in a scheduled or in-progress state with no activity for 14 days?

The scan is considered timed out after 14 days of inactivity. However, the scan job's state on the UI is shown as Completed.

### What happens if the scan is initiated when the pod is offline?

The pod is not running or is in an Inactive state. The scan cannot start.

### What happens if the scan job is canceled when the pod is down?

Securiti does not allow scan cancellation when the pod is down or offline.

### What happens in the case of multiple data systems in a single scan job, such as one completed and one running?

The scan job state shows as Running until all data systems are completed.

### What happens in the case of multiple data systems in a single scan job one completed and one timed out?

The scan job state remains Running until any scan is in progress, but is marked as timed out if even one data system times out.

### What happens in the case of multiple data systems in a single scan job, such as one completed and one errored?

The scan job state shows as Error.

### Can I update the pod when a scan job is running?

You must wait for the scan job to complete or pausing the scan before any pod-related operation. However, the pod can be updated during a running scan job. Contact your Customer Success Manager or Account Representative for guidance on upgrades.

### How can I improve scanning performance?

This depends on a variety of variables. We recommend that you consult our Technical Expert team (CS) for the most appropriate steps.

### Can we start creating DSRs with a running scan job?

No. You must complete the scan job before executing any DSR.

### How can we see the status of all data systems associated with a single scan job?

Click **View Status** under the **Job Status** section.

### Does Securiti support compressed files?

Yes. Securiti supports scanning the following compressed file types, such as `GZ`, `RAR`, `TAR`, and `ZIP`.
