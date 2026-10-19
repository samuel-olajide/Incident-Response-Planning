# Task
1. Create a timeline using E01 to E08. Separate confirmed observations, working hypotheses, and unresolved questions.
2. Explain at least two plausible alternative explanations for ambiguous events.
3. Classify the incident type and initial severity. Define the criteria for Critical, High, Medium, and Low severity, then justify the selected level using operational impact, affected data, and uncertainty.
4. Identify confirmed and potentially affected assets. Assess confidentiality, integrity, and availability separately. Set response priorities that address the examination deadline and possible backup compromise.
5. List at least three priority investigation questions. For each, identify the additional log, artifact, interview, or validation check that could resolve it. Explain what findings would change your severity or scope assessment.
> Required outputs: incident timeline, severity assessment, and investigation priorities.

## 1. Incident Timeline

| Evidence | Time WAT | Confirmed observation | Working hypothesis or unresolved question |
| :---- | :---: | :---- | :---- |
| E01 | Day -1, 16:40 | A finance officer opened an unexpected payroll attachment on FIN-PC07. | The payroll attachment may have introduced malware, but the malicious code execution is yet to be verified. |
| E02 | Day 0, 01:15 | The finance officer account signed in from an unfamiliar IP and new device. | The account may have been compromised, but the MFA status and the user involvement is yet to be known. |
| E03 | Day 0, 01:35 | The `svc_backup` made remote administrator logons to FS01 and BAK01 outside its usual schedule. | The admin account may have been misused to access backups and file server. |
| E04 | Day 0, 01:50 | FIN-PC07 uploaded 1.2 GB over HTTPS to unfamiliar cloud storage. | This could be data exfiltration, but the uploaded contents are currently unknown. |
| E05 | Day 0, 02:00 | Backup jobs for FS01 and LMS01 reports success. | The backups may be unusable or compromised. However, a successful job does not confirm recoverability. |
| E06 | Day 0, 08:30 | Mass file changes occur on FIN-PC07 and FS01 shared folders contain `.locked` files and a ransom note. | There is a suspected ransomware, but the malware family is yet to be confirmed. |
| E07 | Day 0, 08:40 | The portal login page loads, but learners cannot open materials or submit assessments. | The portal may have been affected by the `locked` files on FS01, as the portal login page is on the server. |
| E08 | Day 0, 08:45 | The incident contact list on FS01 is inaccessible. Staff phones are available.  | The trustworthiness of corporate email is unverified, and the incident team cannot rely on the stored contact lists . |

## 2. Alternative explanations for ambiguous events.

1. **E02 (unfamiliar sign-in)**: The finance officer may also have signed in from a new device in a different location, which would be harmless. However, this can be resolved by inviting the user for questioning and reviewing the sign-in log (MFA result, device, location).
2. **E05 (backup success)**: The console only tells when a job finished and does not tell is the data is clean. The backups could hold encrypted or altered files, or the attacker could have changed retention. Every network backup should be treated as untrusted until restored and checked in isolation.

## 3. Incident type and severity

### Incident type
The incident should be classified as a suspected ransomware attack with potential account compromise, unauthorised privileged access, and possible data exfiltration. The `.locked` files and ransom note on FS01 provide strong evidence of ransomware activity, while the unusual Microsoft 365 sign-in, privileged logons, and large upload suggest that the incident may extend beyond file encryption.

### Initial severity

| Severity | Criteria |
| :---- | :---: |
| Critical | Major business services are unavailable or seriously disrupted; ransomware or a significant compromise affects critical systems; sensitive data exposure is suspected; or backups may be compromised. Immediate incident-team activation and executive oversight are required. |
| High | A confirmed security incident significantly affects a business function or important system, but the impact is contained and critical services can continue through safe alternatives. Rapid response and management notification are required. |
| Medium | A limited incident affects a small number of systems or users, with manageable operational impact and no current evidence of wider compromise. A coordinated response is required. |
| Low | A minor security event with limited impact, no confirmed compromise of important systems, and no significant disruption to business operations. Normal incident procedures are sufficient. |
