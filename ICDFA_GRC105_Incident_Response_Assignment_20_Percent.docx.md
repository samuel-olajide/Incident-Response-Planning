**INTERNATIONAL CYBERSECURITY AND DIGITAL FORENSICS ACADEMY**

# **Incident Response Planning Assignment**

## GRC105  Incident Management and Business Continuity  Week 20

Act as the Incident Response Lead for a fictional training institute facing a suspected ransomware incident. Analyse the evidence, prepare a coordinated response plan, and test your decisions through a documented tabletop exercise.

| Assessment detail | Requirement |
| :---- | :---- |
| Programme | Governance, Compliance, and Risk Training Program |
| Assessment type | Individual assignment  |  Complete all six tasks |
| Total marks and weighting | 100 marks  |  20% of the final course grade |
| Submission | One Word document through the E-Campus assessment page |
| Deadline | As published for this assessment in E-Campus |
| Suggested effort | 10 to 12 hours |

## **Learning outcomes**

* Classify incidents and prioritise response using evidence and business impact.  
* Develop an incident response plan with clear roles, authority, and escalation.  
* Sequence containment, evidence preservation, eradication, and validated recovery.  
* Evaluate response decisions through communication, exercises, and lessons learned.

# **Scenario and evidence**

## **Northbridge Skills Institute**

Northbridge Skills Institute is a fictional education and training provider with 1,800 learners and 90 staff. It holds learner contact details, admission documents, assessment records, and finance files. An online examination for 100 learners is scheduled for 11:00 on Day 0\. You take control of the incident at 08:45 on Day 0, a Monday. All times are West Africa Time (WAT).

Its systems are FIN-PC07, a finance workstation; FS01, the shared file server; LMS01, the learning portal; and BAK01, the network backup repository. Microsoft 365 provides identity and email. The portal depends on files stored on FS01. The svc\_backup account has administrator access to FS01 and BAK01.

The last disconnected backup is from 17:00 on Day minus 3, the preceding Friday. Network backups are not immutable. Neither backup route has undergone a restoration test in the last 90 days. EDR covers workstations, but server coverage is incomplete. The IT team has three staff and one security analyst.

## **Initial evidence pack**

| ID | Time WAT | Source and observation |
| :---- | :---: | :---- |
| E01 | Day minus 116:40 | User report and mail record: a finance officer opened an unexpected payroll attachment on FIN-PC07. Execution of malicious code is not yet verified. |
| E02 | Day 001:15 | Microsoft 365 audit: the finance officer account signed in from an unfamiliar IP and new device. MFA status and the user's involvement are unknown. |
| E03 | Day 001:35 | Windows logs: svc\_backup made remote administrator logons to FS01 and BAK01 outside its usual schedule. The reason is unknown. |
| E04 | Day 001:50 | Proxy record: FIN-PC07 uploaded 1.2 GB over HTTPS to unfamiliar cloud storage. The record does not reveal the transferred content. |
| E05 | Day 002:00 | Backup console: the FS01 and LMS01 job reports success. Recoverability and freedom from compromise have not been established. |
| E06 | Day 008:30 | EDR and helpdesk: mass file changes occur on FIN-PC07. FS01 shared folders contain .locked files and a ransom note. The malware family is unconfirmed. |
| E07 | Day 008:40 | Helpdesk: the portal login page loads, but learners cannot open materials or submit assessments. The scope of damage to LMS01 remains unknown. |
| E08 | Day 008:45 | Operations report: the incident contact list on FS01 is inaccessible. Staff phones are available. The trustworthiness of corporate email is unverified. |

These observations do not establish attacker identity or prove that personal data was stolen. Cite evidence IDs in your decisions and label additional assumptions. Use fictional contact details and record proposed evidence collection as planned.

# **Incident assessment and governance**

## **Task 1 Incident classification and initial assessment**

**15 marks**

* Create a timeline using E01 to E08. Separate confirmed observations, working hypotheses, and unresolved questions. Explain at least two plausible alternative explanations for ambiguous events.  
* Classify the incident type and initial severity. Define the criteria for Critical, High, Medium, and Low severity, then justify the selected level using operational impact, affected data, and uncertainty.  
* Identify confirmed and potentially affected assets. Assess confidentiality, integrity, and availability separately. Set response priorities that address the examination deadline and possible backup compromise.  
* List at least three priority investigation questions. For each, identify the additional log, artifact, interview, or validation check that could resolve it. Explain what findings would change your severity or scope assessment.

**Required outputs: incident timeline, severity assessment, and investigation priorities.**

## **Task 2 Incident response plan and team responsibilities**

**20 marks**

* Prepare a concise policy and plan covering mission, objectives, scope, incident declaration, activation and escalation rules, authority to isolate systems, documentation requirements, and plan review. Explain how the plan connects with business continuity.  
* Define a Computer Security Incident Response Team (CSIRT) with at least six roles. Include incident management, security analysis, forensics, IT operations or a business owner, legal or privacy advice, and communications. Explain how the small team will obtain additional support when needed.  
* Create a RACI matrix for at least eight activities: detection, analysis, containment, evidence handling, stakeholder communication, assessment of reporting obligations, restoration approval, and closure or review. Define Responsible, Accountable, Consulted, and Informed. Assign exactly one accountable role and at least one responsible role per activity. A combined A/R assignment is acceptable.  
* Recommend at least four preparation improvements. Include backup readiness and an accessible incident contact list. For each improvement, name the owner, resources needed, and how readiness will be checked. Cover tools, secure communication, and training where relevant.

**Required outputs: policy and plan outline, team structure, RACI matrix, and readiness checklist.**

# **Response operations and communication**

## **Task 3 Response playbook and evidence preservation**

**25 marks**

* Create a playbook containing at least ten ordered actions for the first 60 minutes after 08:45 and the remainder of the first 24 hours. Use columns for time or stage, action, owner, required approval, evidence to retain, and completion check.  
* Cover short term containment, investigation, longer term containment, eradication, recovery, and closure. Address affected endpoints, privileged and cloud accounts, the shared server, suspicious transfers, and backup access. Explain how you will check for broader compromise.  
* Justify two difficult decisions: containment while preserving useful evidence, and restoring examination access while backup safety is uncertain. Explain when immediate isolation is necessary and how you will document any evidence loss or operational impact.  
* Create an evidence register for at least four relevant items. Record ID, source, proposed collection method, collector role, date and time with timezone, integrity check, secure storage, and custody transfers. Describe access restrictions. Use planned or not yet collected where appropriate; do not invent hashes or claim acquisitions you did not perform.  
* Describe how you will remove persistence, address the likely entry point, and secure compromised credentials. Set recommended restoration order, recovery targets, and acceptable data loss. Explain how you will select and validate a backup, restore in a controlled environment, check data integrity, and monitor for recurrence before the business owner approves service return.

**Required outputs: playbook, evidence register with custody arrangements, and recovery acceptance criteria.**

## **Task 4 Communication and escalation**

**10 marks**

* Create a communication matrix for at least six stakeholder groups. Record trigger, message owner, channel, approver, and update frequency. Include learners, management, IT or security staff, a relevant service provider, and legal or privacy advisers. Provide an alternative channel if corporate email is unsafe or unavailable.  
* Draft a 150 to 200 word executive briefing with confirmed impact, uncertainty, decisions requiring approval, and the next update time. Draft a separate 100 to 150 word learner notice with practical instructions and the status of the examination.  
* Explain how legal or privacy advisers will assess notification obligations and confirm the relevant recipients and deadlines. Distinguish operational notices from any formal breach notification. If you assert a legal deadline, identify the jurisdiction and cite an authoritative source.

**Required outputs: communication matrix, executive briefing, learner notice, and escalation rules.**

# **Exercise and critical reflection**

## **Task 5 Tabletop exercise and improvement plan**

**15 marks**

Design a 60 minute tabletop exercise that tests your plan. State objectives, participant roles, an agenda, and at least three measurable success criteria. Walk through the exercise individually, taking the role of each participant. Clearly label the results as a simulation.

| Exercise time | Required inject |
| :---- | :---- |
| Minute 10 | Management asks you to reopen the learning portal before the 11:00 examination, even if the most recent backup is unverified. |
| Minute 20 | An attacker claims to hold all 1,800 learner records and threatens publication in 12 hours. A screenshot is provided, but its authenticity is unknown. |
| Minute 35 | A test restoration of the latest network backup fails with an unreadable snapshot error. |
| Minute 45 | A social media post claims the examination is cancelled. A journalist asks whether learner information has been exposed. |

* Add one further inject of your own. Record at least five decisions in a log with inject, decision, decision owner, rationale, communication, and effect on the response or recovery plan.  
* Evaluate the simulated results against your success criteria. Identify at least five improvements and give each a priority, owner, target completion time, and measurable evidence of completion. Set a post incident review deadline and explain who closes the actions.

## **Task 6 Case study analysis and critical reflection**

**10 marks**

Write 300 to 400 words analysing the illustrative healthcare ransomware case on slide 16 of the teaching deck. Identify three response strengths and two limitations or unresolved issues. Explain two changes you would transfer to the Northbridge plan and justify their relevance.

Discuss why restoring critical systems within 72 hours differs from full restoration over seven days. Explain what evidence would be needed before claiming that no patient data was stolen. Identify one decision in your own plan that you would revise after the tabletop exercise.

## **Submission checklist and authorship**

Use the filename GRC105\_IRP\_Assignment\_StudentID.docx. Include your name, student ID, official email, word count, all six tasks, and a reference list. Cite the teaching slides and at least two authoritative sources. Use one consistent citation style and link each source to the decision it supports.

Submit your own analysis. Acknowledge sources and any AI assistance in line with the course policy. Keep all data fictional and be prepared to explain your decisions if the instructor requests clarification. Submission and late submission arrangements follow the assessment details in E-Campus.

# **Marking rubric and reading**

The assignment is marked out of 100\. The weighted contribution is a maximum of 20 points toward the final course score.

| Assessment area | Mark allocation and evidence expected | Marks |
| :---- | :---- | :---: |
| Task 1Initial assessment | Severity and justification (5); evidence linked timeline with uncertainty (6); impact, priorities, and investigation checks (4). | 15 |
| Task 2Plan and roles | Usable policy, authority, and escalation (6); realistic CSIRT and correct RACI (8); readiness, resources, and continuity integration (6). | 20 |
| Task 3Response playbook | Sequenced containment and justified tradeoffs (7); evidence integrity and custody (5); eradication and scope checks (6); safe restoration, monitoring, and acceptance (7). | 25 |
| Task 4Communication | Stakeholders, channels, approval, and escalation (5); accurate executive briefing (3); clear learner notice with practical next steps (2). | 10 |
| Task 5Tabletop exercise | Objectives, roles, agenda, injects, and success criteria (5); reasoned simulated decision log (5); measurable improvement plan and review (5). | 15 |
| Task 6Case study analysis | Evidence based critique of the healthcare case (4); justified transfer to Northbridge (4); reflection on a revised decision (2). | 10 |
| Report qualityand referencing | Clear structure and usable tables (2); credible sources and consistent citations (2); transparent assumptions and professional writing (1). | 5 |
| Total | Maximum contribution to the course grade: 20%. | 100 |

Full credit requires accurate, complete work applied to the supplied case with justified decisions and usable outputs. Partial credit applies where the approach is sound but incomplete, generic, or insufficiently supported. Missing or technically incorrect elements earn no credit for those elements. Multiple defensible response choices can earn full marks.

## **Framework guidance**

Use the four teaching stages to organise your work: preparation; detection and analysis; containment, eradication, and recovery; and post incident activity. When citing NIST SP 800-61 Revision 3, use its CSF 2.0 alignment: Detect, Respond, and Recover form incident response, while Govern, Identify, and Protect support preparation. Continuous improvement feeds lessons into all functions. Do not attribute the four stage teaching model directly to Revision 3\.

## **Core reading**

ICDFA. Incident Response Planning. GRC105, Week 20\. Teaching deck, slides 1 to 18\.

NIST (2025). SP 800-61 Revision 3\. Incident Response Recommendations and Considerations for Cybersecurity Risk Management. [Official publication](https://csrc.nist.gov/pubs/sp/800/61/r3/final)

NIST. Incident Response project. [Framework and life cycle overview](https://csrc.nist.gov/projects/incident-response)

CISA and partners. \#StopRansomware Guide. [Prevention guidance and response checklist](https://www.cisa.gov/resources-tools/resources/stopransomware-guide)