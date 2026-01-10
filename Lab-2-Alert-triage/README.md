## Lab 2: Alert Triage and verdict assignment 
(TryHackMe SOC simulation)

**Date:** January 10th, 2026

**Platform:** TryHackMe (SOC L1 Triage)

This Lab simulates real-time SOC alert triage: reviewing three alerts of varying severity (Critical, High, Low), assigning them, updating status, rendering verdicts and documenting reasoning.

## Objective
Prioritize and investigate alerts, assign to myself, mark alerts as in progress, select my verdict (True positive, False Positive, None), and provide comments explaining my desicion

## Steps Taken (Overall Process
1. Reviewed all incoming alerts in the simulated SIEM dashboard.
2. Prioritized alerts based on severity (starting at critical).
3. Assigned the alert to myself and updated status to "in progress".
4. Analyzed the logs for each alert (IP, Source host, activity patterns).
5. Rendered a verdict and added a detailed comment explaining my decision.
6. Closed alerts appropriately.

## Scenario Breakdown
### 1. Critical Severity Alert (Potential Data Exfiltration)
**Descrption**: The rule set detects 5 or more gigabytes of data being sent from a single device to a single destination within a day, which may indicate data exfiltration to an untrusted location

**Verdict**: False Positive

**Comment / Reasoning**: This alert was triggered from outbound traffic from source IP 192.168.45.66 to zoom.us. The data volume (5.8GB sent) aligns with meetings or file sharing in a video call. No indicators of compromise, unauthorized destination, 
or unusual patterns were found. Verdict set to False positive, no escalation required; activity is normal and consistent with authorized business use.

### 2. High Severity Alert (Double-Extension File Creation)
**Description**: This rule detects creation of double-extension files

**Verdict**: True Positive

**Comment / Reasoning**: This alert was triggered when a user downloaded a video off of a 'free' video site. This action does not align with authorized business use due to risk of installing malware unintentionally. The site should be blocked and verdict was set to True Positive.

### 3. Low Severity Alert (Download From GitHub Repository)
**Description**: This rule detects any download from GitHub. Github stores a lot of great projects that IT teams can use, it also stores malicious scripts and exploits that must not be downloaded by users.

**Verdict**: False Positive

**Comment / Reasoning**: The user downloaded a Facebook reaction off of GitHub, downloads via GitHub are common and it is harmless data being moved and this rule tracks any download from GitHub. Verdict proven False Positive due to no malicious content or misuse present.

## Results 
Successfully triaged three alerts of varying severity:
- Critical: False Positive (benign Zoom traffic)
- High: True Positive (malicious double-extension file)
- Low: False Positive (harmless GitHub reaction GIF)

Demonstrated prioritization, context-based analysis, and proper alert disposition to focus on real threats and minimize time waste
