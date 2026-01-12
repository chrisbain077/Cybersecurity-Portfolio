# Lab 3: Verdict assesment and Escaalation 
(TryHackMe SOC simulation)

**Date:** Januaary 12, 2026
**Platform:** TryHackMe (SOC Alert Reporting room)

This lab simulates a real-time SOC alert triage: Involving a L1 analyst assessing threat alerts, reporting and escalating these alerts inside SIEM to a L2 analyst for remediation.

## Objective
Investigate alerts, assign to myself, mark in progress, review and report with a detailed comment, escalate to L2 analyst for remidiation.



## Steps Taken (Overall Process)
1. Review all incoming alerts on the simulated SIEM dashboard
2. Assigned alert to myself and updated status to "in progress"
3. Analyzed context of the alert
4. Rendered my verdict, and wrote out a detailed report
5. Reassigned the threat to the L2 analyst available


## Scenario Breakdown
 ### 1. Medium Security Alert
 - Description: A spike of domain discovery commands was detected like Whoami, net user, and Get-ADUser. unless the commands are confirmed as part of IT activity or legitimate scrripts, the device is likely compromised and needs to be contained immediately.
 - Comment: this alert shows a spike of domain discovery commands 'dir hostname whoami /priv net group "Domain Admins" /domain nltest /dclist:tryhackme.thm' being invoked on the host 
'DMZ-MSEXCHANGE-2013', User 'NT AUTHORITY\SYSTEM' which is running on Windows Server 2012 R2. The source process was 'C:\Windows\System32\cmd.exe'
- Reasoning: This alert was set to True Positive and Escalated to a L2 analyst for remidiation after reviewing the logs in SIEM showing invoked directory commands through Windows System32

## Skills Demonstrated
- SIEM dashboard navigation
- True positive alert identified
- Proper escalation and reporting

## Results
Succesfully identified a True Positive alert, wrote a detailed report and escalated the event to a L2 analyst for remidiation.

## Key Takeaways
This lab reinforced that escalations require context not just technical details. i learned to think about why activity is suspicious, not just what happened. 
