# PowerShell Abuse Detection with Wazuh & Sysmon

A blue-team lab demonstrating how suspicious PowerShell activity can be captured with Sysmon and detected using Wazuh.

## Project Summary

This lab simulates suspicious PowerShell execution in a controlled Windows environment. The activity is first recorded by Sysmon, forwarded to Wazuh, and then reviewed through the SIEM dashboard.

The objective is to understand the complete detection pipeline from endpoint telemetry to security alert generation.

## Skills Demonstrated

- Windows endpoint monitoring
- Sysmon configuration and event collection
- PowerShell telemetry analysis
- Wazuh alert investigation
- Detection validation
- SIEM workflow documentation
- Blue-team investigation methodology

## Detection Workflow

```text
Suspicious PowerShell activity
            ↓
      Sysmon records event
            ↓
    Wazuh Agent forwards logs
            ↓
     Wazuh processes rule
            ↓
     Alert appears in SIEM
            ↓
      Analyst investigates
```

## Tools Used

| Tool | Purpose |
|---|---|
| Wazuh | SIEM monitoring and alerting |
| Sysmon | Windows endpoint telemetry |
| Windows 10 | Test endpoint |
| PowerShell | Controlled activity generation |

## Walkthrough

### 1. Generate Suspicious PowerShell Activity

A controlled PowerShell command was executed to generate telemetry for the detection pipeline.

<img width="858" height="733" alt="PowerShell activity" src="https://github.com/user-attachments/assets/a28b6151-45bb-432e-a7d0-5e592875578e" />

### 2. Verify Sysmon Event

Sysmon logs were reviewed to confirm the PowerShell execution had been captured successfully.

<img width="1549" height="959" alt="Sysmon event" src="https://github.com/user-attachments/assets/a7e06784-feaa-4a9d-88a9-1c91f5cfd50e" />

### 3. Review Wazuh Alert

The forwarded telemetry was reviewed in Wazuh to verify that the activity generated the expected security alert.

<img width="1464" height="555" alt="Wazuh alert" src="https://github.com/user-attachments/assets/effc14d5-190e-4489-9276-228a4fadf63e" />

<img width="1063" height="447" alt="Alert details" src="https://github.com/user-attachments/assets/f44ce6b0-a328-4a37-8d69-a3527bd813cd" />

## Analyst Checklist

- Confirm the user and host involved.
- Review the PowerShell command line.
- Check the parent process.
- Determine whether the execution is expected or suspicious.
- Correlate with additional endpoint events.

## Key Takeaways

- Sysmon significantly improves visibility into PowerShell activity.
- Endpoint telemetry is essential for reliable detection engineering.
- Wazuh can convert detailed Windows events into actionable alerts.
- Every alert should be validated with supporting evidence before drawing conclusions.

## Future Improvements

- Add the relevant Sysmon Event IDs.
- Include the Wazuh rule used for detection.
- Map the detection to MITRE ATT&CK techniques.
- Add examples of legitimate PowerShell usage to discuss false positives.
