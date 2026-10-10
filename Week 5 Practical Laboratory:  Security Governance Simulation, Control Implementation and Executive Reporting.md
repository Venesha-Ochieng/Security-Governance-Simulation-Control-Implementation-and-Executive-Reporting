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

```bash
mkdir -p ~/security-governance-lab
cd ~/security-governance-lab
```

---
