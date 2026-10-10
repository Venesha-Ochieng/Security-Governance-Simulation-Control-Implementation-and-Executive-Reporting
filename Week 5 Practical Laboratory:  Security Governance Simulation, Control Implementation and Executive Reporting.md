# INTERNATIONAL CYBERSECURITY AND DIGITAL FORENSICS ACADEMY

## GRC102: INFORMATION SECURITY GOVERNANCE

### Week 5 Practical Laboratory
### Security Governance Simulation, Control Implementation and Executive Reporting

---

### Student Information

| Field | Details |
|---------|---------|
| **Full Name** | Venesha Adhiambo Ochieng |
| **Registration Number** | C11/26/CGRCE/17566 |
| **Email Address** | c11.cgrce2617566@icdfa.edu.ng |
| **Cohort / Batch** | Cohort11 |
| **Date Submitted** | 10th October 2026 |

---

# Official Lab Instructions

Use the official ICDFA repository instructions throughout this assessment:

<https://github.com/icdfa/grc-engineering-labs/blob/master/phase1/grc102/week8/LAB_INSTRUCTIONS.md>

---

# Executive Summary

This practical laboratory demonstrates the application of security governance principles through an evidence-based technical and management simulation. The exercise is based on governance weaknesses associated with the 2017 Equifax data breach, including delayed remediation of a known Apache Struts vulnerability, weak database authentication, inadequate network segmentation, ineffective monitoring, and unclear accountability. The purpose of the lab is to identify technical weaknesses and show how those weaknesses should be linked to ownership, escalation, control implementation, performance measurement, executive oversight, and Board-level reporting.

The lab demonstrates that major security incidents are rarely caused by a single technical vulnerability. Significant breaches are more likely to occur when technical weaknesses are combined with failures in governance, such as unclear responsibilities, ineffective remediation processes, inadequate control verification, weak monitoring, and limited executive visibility. The controls and reporting mechanisms developed in this exercise are therefore designed to address both the technical weaknesses and the governance conditions that allow those weaknesses to persist.

---

# Part 1: Setting Up a Simulated Environment

## 1.1 Objective

The objective of Part 1 is to establish a controlled and isolated Docker-based simulation environment that reproduces governance conditions similar to those associated with the 2017 Equifax breach. The environment is intended to demonstrate how weaknesses such as delayed vulnerability remediation, weak database security, insufficient network segmentation, and inadequate monitoring can increase organisational exposure when governance controls are ineffective.

Part 1 also establishes the governance mechanisms required to assess and manage the simulated environment. These include a vulnerability scanner for identifying security weaknesses, a patch-management utility for tracking and applying corrective actions, and a governance tracker for recording controls, risks, incidents, metrics, and assurance information.

---

## 1.2 Lab Environment

The laboratory environment is deployed using Docker and Docker Compose within an authorised Ubuntu-based lab host. All components are connected through a dedicated Docker network named **secgov_network**, which provides the internal communication path required for the simulation while keeping the exercise contained within the approved laboratory boundary.

The environment consists of three main containers together with the dedicated Docker network:

| Component | Laboratory Role | Governance Relevance |
|------------|----------------|----------------------|
| **web_server** | Customer-facing Apache Struts application using the intentionally vulnerable S2-045 image. | Demonstrates the risk created when a known critical vulnerability is not identified, prioritised, and remediated within an appropriate timeframe. |
| **database_server** | MySQL 5.7 database containing fictitious customer records and laboratory credentials. | Demonstrates the governance risks associated with weak authentication, inadequate database protection, and excessive application-to-database reachability. |
| **monitoring_server** | Ubuntu-based container used to support monitoring activities and evidence collection. | Represents the need for security telemetry, event detection, alerting, and reliable assurance evidence. |
| **secgov_network** | Dedicated Docker bridge network connecting the simulated components. | Establishes the laboratory network boundary and provides the basis for evaluating network segmentation and communication between services. |

---

## 1.3 Docker Environment

### 1.3.1 Create a directory for the lab

![Figure 1.3.1](1.3.1.png)

---

### 1.3.2 Create a Docker network for the lab

![Figure 1.3.2](1.3.2.png)

---

### 1.3.3 Create a docker-compose.yml file
![Figure 1.3.3](1.3.3.png)

---

## 1.4 Database Configuration

### 1.4.1 Create database initialization script

![Figure 1.4.1](1.4.1.png)


### 1.4.2 Create monitoring directory
![Figure 1.4.2](1.4.2.png)
---

### 1.4.3 Start the containers
![Figure 1.4.3](1.4.3.png)
---

## 1.5 Vulnerability Scanner

![Figure 1.5](1.5.png)

![Figure 1.5.1](1.5.1.png)

---

## 1.6 Patch Management System

### Create a patch management script
![Figure 1.6](1.6.png)

![Figure 1.6.1](1.6.1.png)

---

## 1.7 Governance Tracker

### 1.7.1 Create a security governance tracking script
![Figure 1.7.1](1.7.1.png)
---

### 1.7.2 Create a script to initialize the governance tracker with sample data

![Figure 1.7.2](1.7.2.png)

### Run the initialization script

![Figure 1.7.2.](1.7.2..png)
---

## 1.8 Baseline Vulnerability Assessment

![Figure 1.8](1.8.png)
---

## 1.9 Governance Dashboard

![Figure 1.9](1.9.png)
---

## 1.10 Equifax Relevance

The governance dashboard reflects several conditions that are directly relevant to the lessons from the Equifax breach. The most significant issue is the presence of one Critical, one High and one Medium risk, together with one High-severity security incident. This indicates that the simulated organisation is operating with material security exposure rather than with isolated low-level weaknesses. The dashboard therefore demonstrates the governance problem that can arise when known risks remain open while operational weaknesses continue to affect critical systems.

The strongest parallel with Equifax is the weakness in patch and vulnerability management. Patch Compliance is below target at 85% against a required 95%, which is correctly flagged as Red. This suggests that some critical or important patches are not being applied within the required governance threshold. The lab also records a Vulnerability Remediation Time of 12 days against a target of 7 days, showing that remediation is taking longer than expected. Even though the current script displays this metric as Green, the underlying values show that performance is actually worse than the target because a lower remediation time is preferable. This is an important governance observation and indicates that the dashboard logic should be reviewed for metrics where lower values represent better performance.

These conditions mirror the governance lesson illustrated by the Equifax case study: identifying a vulnerability is not sufficient unless the organisation has an effective process to ensure that remediation occurs within the required timeframe, is verified, and is escalated when deadlines are missed. In this lab, the combination of reduced patch compliance, delayed vulnerability remediation, and an existing High-severity incident demonstrates how weaknesses in technical controls can be compounded by governance failures in ownership, monitoring and follow-up.

The dashboard also shows that the organisation has established governance structures, including three policies, three controls, three risks, three metrics and one audit. However, the presence of these governance artefacts does not by itself demonstrate effective governance. Their effectiveness depends on whether they influence operational behaviour and trigger corrective action.

---

## 1.11 Part 1 Conclusion

Part 1 successfully established the simulated security governance environment required for the assessment. The Docker-based lab brought together the vulnerable Apache Struts web application, MySQL customer database, monitoring component, and dedicated **secgov_network**, creating a controlled environment in which technical weaknesses and governance failures could be assessed safely.

The supporting governance tools also provided a clear baseline for the remainder of the lab. The vulnerability scanner, patch-management utility, governance tracker, and dashboard created visibility into the organisation's simulated security posture. The dashboard showed three recorded risks, including one Critical and one High risk, as well as one High-severity incident. It also identified weak performance in patch compliance, with an actual value of 85% against a 95% target, and a vulnerability remediation time of 12 days against a 7-day target.

These findings demonstrate that the simulated environment contains both technical and governance weaknesses that require corrective action. In particular, the results highlight the importance of timely patching, effective vulnerability remediation, accurate security metrics, and clear management oversight. Part 1 therefore provides the evidence-based baseline needed for Part 2, where the identified weaknesses will be analysed further through the authorised attack simulation and comparison with the governance failures associated with the Equifax breach.

---

# Part 2: Analysing Security Governance Failures

## 2.1 Objective

The objective of Part 2 is to conduct an authorised and non-destructive attack simulation against the environment established in Part 1, assess the security and governance weaknesses that allow the simulated attack to succeed, and compare those weaknesses with the documented causes and governance lessons associated with the 2017 Equifax data breach.

The authorised simulation script is used to determine whether the intentionally vulnerable Apache Struts application can be identified as exposed and, where applicable, to simulate access to the customer-data environment. The exercise is educational and controlled: rather than carrying out unrestricted exploitation, the script records the simulated activity in `attack_log.json`.

The log captures key details such as:

- Attack type
- Target system
- Success status
- Data set accessed
- Number of fictitious customer records affected

This approach allows the lab to demonstrate how technical weaknesses can translate into broader governance failures, including ineffective vulnerability remediation, weak access controls, insufficient monitoring, poor segmentation, and inadequate accountability.

The evidence generated during the simulation therefore provides the basis for the governance-failure analysis and Equifax comparison that follow.

---

## 2.2 Attack Simulation

### 2.2.1 Create an attack simulation script

![Figure 2.2.1](2.2.1.png)
---

### 2.2.2 Create a log analysis script

![Figure 2.2.2](2.2.2.png)

---

## 2.3 Attack Results

![Figure 2.3](2.3.png)
---

## 2.4 Governance Failures

![Figure 2.4](2.4.png)
---

## 2.5 Root Causes

The root causes are as follows:

- **Incident Detection:** inadequate real-time monitoring and alerting allowed the simulated attack to occur without being detected.
- **Policy Implementation:** the patch management policy existed, but it was not effectively enforced, so the vulnerable system remained exposed.
- **Metrics and Measurement:** security metrics were being recorded, but they were not driving timely remediation or management action.
- **Security Architecture:** insufficient network segmentation allowed the web application environment to have unnecessary access paths toward the database environment.
- **Authentication and Access Control:** weak/default database credentials and insufficient access restrictions increased the risk of unauthorized database access.

---

## 2.6 Equifax Comparison

| Governance Area | Equifax Breach | Simulated Lab Environment | Similarity |
|-----------------|----------------|---------------------------|------------|
| Patch Management | A known Apache Struts vulnerability, CVE-2017-5638, was not remediated effectively. | The laboratory uses a vulnerable Apache Struts application and demonstrates weaknesses in patch implementation. | High |
| Security Monitoring | Inadequate monitoring contributed to delayed detection of malicious activity. | The simulated attack can succeed without real-time monitoring or alerting, producing an Incident Detection governance failure. | High |
| Network Segmentation | Weak segmentation increased the potential impact of compromise. | The lab identifies insufficient network segmentation as a Security Architecture failure. | High |
| Authentication & Access Control | Weak security controls increased exposure of sensitive systems and information. | The database environment uses weak/default authentication, resulting in an Authentication and Access Control finding. | Medium-High |
| Policy Implementation | Governance procedures were ineffective in ensuring identified risks were actually remediated. | A patch-management policy exists, but the vulnerable condition remains, showing a gap between documented policy and implementation. | High |
| Metrics & Accountability | Governance oversight did not ensure that security issues were resolved promptly. | Security metrics exist, but the analysis identifies that they are not driving effective remediation. | High |

---

## 2.7 Key Governance Lessons

### 1. Policies must be implemented and enforced

Having a patch-management or vulnerability-management policy is not enough. Controls must operate effectively in practice, with clear ownership, deadlines and follow-up. The lab specifically identifies failures where policies exist but critical weaknesses remain unresolved.

### 2. Critical vulnerabilities require timely remediation

Known high-risk vulnerabilities should be prioritised, tracked and remediated within defined service-level targets. Delays in patching can turn an identified technical weakness into a major business and data-security incident. The lab’s Equifax comparison identifies ineffective patching as a central governance failure.

### 3. Continuous monitoring is essential

Organisations need effective logging, alerting and incident-detection capabilities so attacks can be identified quickly. In the simulation, a successful attack without effective detection results in an Incident Detection governance failure.

### 4. Network segmentation reduces the impact of compromise

Sensitive systems such as databases should not be unnecessarily reachable from exposed application systems. Segmentation and least-privilege access can limit lateral movement and reduce the potential blast radius of a breach.

### 5. Strong authentication and access controls are required

Default or weak credentials undermine otherwise effective technical controls. Database and administrative access should use strong credentials, appropriate permissions, and controlled access paths.

### 6. Security metrics must lead to action

Metrics should not exist only for reporting. They must identify unacceptable conditions, assign accountable owners, trigger escalation and drive remediation. The lab explicitly identifies ineffective metrics when measurements do not result in security improvement.

### 7. Accountability and management oversight are critical

Security risks need named owners and clear escalation paths. Senior management should receive meaningful information about unresolved critical vulnerabilities, control failures and overdue remediation so that action can be taken before risk becomes an incident.

### 8. Governance should be continuous rather than reactive

The broader course material emphasises embedding governance throughout operational and development processes rather than relying on occasional reviews. Continuous monitoring, automated controls and regular management review provide stronger assurance than point-in-time checks.

---

## 2.8 Part 2 Conclusion

The Part 2 analysis demonstrated that the simulated environment contained several significant security governance weaknesses that could increase the likelihood and impact of a cyber incident. The governance failure analysis identified weaknesses in incident detection, policy implementation, metrics and measurement, security architecture, and authentication and access control.

These findings show that security risks can remain significant even when policies, metrics and technical controls exist if they are not effectively implemented, monitored, and enforced.

The comparison with the Equifax breach further demonstrated that ineffective patching, inadequate monitoring, weak segmentation, poor control enforcement and insufficient accountability can allow known security weaknesses to develop into serious breaches.

The main governance lesson is that organisations must move beyond simply documenting policies and instead ensure that controls are continuously monitored, assigned to accountable owners, supported by meaningful metrics and followed by timely remediation and escalation.

# Part 3: Implementing Security Governance Controls

## 3.1 Objective

Part 3's objective was to implement and verify a set of governance controls addressing the failures identified in Part 2, including patch management, network segmentation, database security, security monitoring, and governance oversight, and to document how each control maps back to a specific identified failure.

---

## 3.2 Create a Script to Implement Security Governance Controls

![Figure 3.2](3.2.png)

---

## 3.3 Implement the Security Governance Controls (Patch Management, Network Segmentation, Database Security, Security Monitoring, Governance Oversight)

![Figure 3.3](3.3.png)

## 3.4 Verification

Verification confirmed that the monitoring script and governance oversight document were implemented and that governance policies, controls and metrics were recorded. However, verification also revealed inconsistent patch-status persistence and the attack retest remained successful. These results demonstrate that governance controls were configured, but further technical remediation would be required before the vulnerable Struts service could be considered fully secured.

![Figure 3.4](3.4.png)

## 3.5 Equifax Control Mapping

| Equifax Governance Failure | Part 3 Control Implemented | How the Control Addresses the Failure |
|---------------------------|---------------------------|--------------------------------------|
| Failure to remediate a known Apache Struts vulnerability | Automated Patch Management and Critical Patch Compliance Metric | Establishes a formal patching process, assigns ownership to the Security Engineer and measures whether critical patches are applied within the defined seven-day target. |
| Weak security monitoring and delayed detection | Real-time Security Monitoring | Introduces monitoring for suspicious HTTP activity, database access and file changes, together with alert generation and a monitoring-coverage metric. |
| Insufficient network segmentation | Network Segmentation Control | Applies a least-privilege segmentation control intended to restrict unnecessary communication between systems and reduce the possibility of lateral movement. |
| Weak database authentication and access control | Database Security Control | Introduces stronger authentication and access controls for the database and assigns responsibility to the Database Administrator. |
| Weak accountability and unclear ownership | Security Governance Oversight Policy | Defines responsibilities for the CEO, CISO, CIO and CFO and establishes reporting and escalation relationships. |
| Insufficient executive and Board oversight | Executive Security Oversight Control | Establishes quarterly Board security briefings, annual security programme reviews and formal executive oversight of the security programme. |
| Security metrics not driving remediation | Critical Patch Compliance and Security Monitoring Coverage Metrics | Introduces measurable targets so management can track control performance, identify weaknesses and require remediation where targets are not achieved. |

## 3.6 Part 3 Conclusion

Part 3 demonstrated the implementation of governance controls designed to address the weaknesses identified in Part 2. The controls covered patch management, network segmentation, database security, security monitoring and governance oversight, with supporting metrics, ownership and reporting mechanisms recorded in the governance tracker.

The implementation improved the governance structure by assigning clear control ownership, introducing measurable targets for patch compliance and monitoring coverage, establishing executive and Board oversight, and creating mechanisms for security monitoring and escalation. The verification process also confirmed that the monitoring script and governance oversight documentation were implemented and that governance policies, controls and metrics were being tracked.

However, the post-control verification also revealed limitations in the simulation. The patch-status results were inconsistent because control states were not retained together, and the subsequent attack simulation still identified the Struts application as vulnerable. Therefore, the Part 3 evidence demonstrates that governance controls were configured and recorded, but it does not prove that every underlying technical vulnerability was fully remediated.

The main lesson from Part 3 is that implementing a control is not sufficient on its own. Effective security governance requires implementation, verification, measurable performance, clear accountability, continuous monitoring and follow-up remediation where controls do not operate as intended. This reinforces the Equifax lesson that known risks must be actively managed and validated rather than assumed to be resolved once a policy or control has been introduced.

---
