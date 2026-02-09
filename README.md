# SOHO Network Security Audit

**By Matthew Barfield** | [LinkedIn](https://www.linkedin.com/in/matthew-barfield-grc/) | mattbarfield1@gmail.com

[![ISC2 Certified in Cybersecurity](https://img.shields.io/badge/ISC2-Certified%20in%20Cybersecurity-blue)](https://www.isc2.org/Certifications/CC) [![NIST CSF](https://img.shields.io/badge/Framework-NIST%20CSF%20v2.0-green)](https://www.nist.gov/cyberframework) [![GRC Focus](https://img.shields.io/badge/Focus-Governance%20Risk%20Compliance-orange)]()

---

## About This Project
This repository documents a **real, hands-on security audit** I conducted on my own Small Office / Home Office (SOHO) network environment. All sensitive or personally identifiable information (e.g., specific IP addresses, device hostnames, exact model numbers, account details) has been anonymized or generalized to protect privacy while preserving the authenticity and technical accuracy of the findings.

The audit covers actual configurations, vulnerabilities, and misconfigurations I discovered and remediated in a live consumer-grade setup — including router settings, endpoint hardening, network segmentation, authentication practices, and attached cloud services. The documentation reflects genuine defensive security work translated into clear, portfolio-ready GRC-style reporting.

**Key Focus Areas:** Network reconnaissance, configuration auditing, risk assessment (likelihood × impact), segmentation controls, authentication hardening, practical remediation planning, and lessons learned from a production environment.

## Table of Contents
- [Project Overview](#project-overview)
- [Repository Structure & Deliverables](#repository-structure--deliverables)
- [Technical Skills Demonstrated](#technical-skills-demonstrated)
- [Connect With Me](#connect-with-me)
---
## Project Overview
This SOHO audit simulates a real-world small-network security review, highlighting issues typical in consumer-grade setups (default configs, poor segmentation, weak auth). All findings and recommendations are documented in markdown for clarity and portability.

- **Environment Simulated**: Typical home/small-office setup with a consumer router, mixed endpoints (Windows/macOS), IoT devices, guest Wi-Fi, and common cloud services (email, storage).
- **Data Handled**: User credentials, personal files, device configs (no real PII collected).
- **Tools & Methods**: Manual reviews, Nmap discovery, config checks against CIS Benchmarks/vendor guides, simplified risk rating.

---
## Repository Structure & Deliverables
The project follows a phased audit workflow with dedicated folders for each major area.

### Phase 1: Asset Inventory & Discovery
* **Asset Inventory:** Cataloged devices, software, and data flows. [View File](/asset-inventory)

### Phase 2: Authentication & Access Controls
* **Authentication Audit:** Reviewed password policies, MFA/2FA adoption, and account hygiene. [View File](/authentication-audit/password-and-2FA-audit.md)

### Phase 3: Perimeter & Network Security
* **Router & Network Audit:** Evaluated router config, firewall rules, remote access, and segmentation. [View File](/router-and-network-audit/audit-findings.md)

### Phase 4: Cloud & Endpoint Review
* **Cloud Environment:** Assessed attached cloud accounts and services. [View File](/cloud-environment/cloud-security-audit.md)

### Phase 5: Remediation & Reporting
* **Remediations:** Prioritized hardening steps and implementation guidance. [View File](/remediations/remediation-log-feb2026.md)
* **Final Report & Lessons Learned:** Consolidated findings, risk summary, and key takeaways. [View File](/final-report/final-report-and-lessons-learned.md)

---
## Technical Skills Demonstrated
* **Security Frameworks:** NIST CSF alignment, basic CIS Benchmark application.
* **Network Security:** Perimeter enumeration, segmentation design, exposure checks.
* **Risk & Compliance:** Risk register-style prioritization, control gap identification.
* **Documentation:** Professional markdown reporting, evidence organization.
* **Defensive Mindset:** Blue-team focus on hardening consumer environments.

---
## Connect With Me
I'm actively seeking entry-level opportunities in defensive security, SOC analysis, GRC, or compliance where I can apply auditing, risk assessment, and documentation skills to real programs.

📫 **Contact:** mattbarfield1@gmail.com  
💼 **LinkedIn:** [matthew-barfield-grc](https://www.linkedin.com/in/matthew-barfield-grc/)  
📄 **Resume:** [View My Resume](https://drive.google.com/file/d/1PymVrf2F-FabCBFdkPxAqRKoJU-GQnId/view?usp=sharing)

*Open to opportunities in: Defensive Security | SOC Analysis | GRC | Risk Management | Compliance*
