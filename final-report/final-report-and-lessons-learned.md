# Final Report and Lessons Learned

**Project:** SOHO Network Security Audit  
**Author:** Matt Barfield  
**Date:** February 2026  
**Repository:** [https://github.com/mattbarfield1/SOHO-audit](https://github.com/mattbarfield1/SOHO-audit)

## Executive Summary

This project performed a full-scope security assessment of a realistic Small Office / Home Office (SOHO) environment. The audit covered network infrastructure, endpoint security, authentication & access controls, common applications, and attached cloud services.

**Major findings included:**

- Use of default or weak administrative credentials on the router
- Outdated firmware on several IoT and consumer-grade devices
- Lack of MFA on high-value accounts (email, cloud storage, remote access)
- Inadequate network segmentation between guest, IoT, and trusted devices
- Several medium/high-risk misconfigurations in firewall and DNS settings

All critical and high-risk issues received remediation recommendations with priority rankings. Implementing the top 5–7 remediations would significantly improve the overall security posture of a typical SOHO environment.

This work demonstrates applied skills in:

- Network reconnaissance & enumeration
- Configuration hardening (routers, firewalls, endpoints)
- Risk assessment and prioritization (likelihood × impact)
- Practical GRC documentation
- Blue-team / defensive security mindset

## Scope

**In scope**

- SOHO router (firmware version, admin access, port forwarding, firewall rules, remote management)
- LAN segmentation and guest/IoT isolation
- Windows/macOS/Linux endpoints (patching, AV/EDR, user privileges)
- Common applications (browsers, email clients, file sharing, remote desktop)
- Cloud accounts & services commonly used in SOHO (Google Workspace, Microsoft 365, Dropbox, etc.)
- Authentication mechanisms (password policies, MFA adoption, SSO usage)

**Out of scope**

- Physical security
- Mobile device management (MDM)
- Deep web application penetration testing
- Custom/internal business applications
- Social engineering / phishing simulation

## Methodology

1. Asset discovery & inventory (manual + Nmap)
2. Credential & default account auditing
3. Configuration review against CIS Benchmarks / vendor hardening guides
4. External exposure enumeration (Shodan-style thinking + manual checks)
5. Vulnerability scanning (OpenVAS / Nessus-style, manual validation)
6. Risk rating using simplified CVSS-like approach (likelihood + impact)
7. Remediation recommendation development
8. Lessons learned & control improvement mapping

## Summary of Key Findings

| ID     | Finding                                      | Risk   | CVSS-like Score | Remediation Priority |
|--------|----------------------------------------------|--------|------------------|----------------------|
| SOHO-01| Default/weak router admin credentials        | Critical | 9.8             | Immediate            |
| SOHO-02| Router remote management exposed to WAN      | High   | 8.1             | High                 |
| SOHO-04| No network segmentation (IoT on main LAN)    | High   | 7.2             | High                 |
| SOHO-05| Several IoT devices running EOL firmware     | High   | 8.6             | High                 |
| SOHO-06| No MFA on primary email / cloud accounts     | Medium-High | 6.8        | Medium               |
| SOHO-07| Guest Wi-Fi allows LAN access                | Medium | 5.9             | Medium               |
| SOHO-08| Outdated browser / plugin versions on endpoints | Medium | 6.1          | Medium               |
| SOHO-09| Weak local account password policy           | Medium | 5.3             | Medium               |
| SOHO-10| DNS rebinding protection not enabled         | Low-Medium | 4.7         | Low                  |

## Top Recommended Remediations (Prioritized)

1. Change all default credentials → enforce strong, unique passwords
2. Disable WAN admin access on router
3. Implement VLANs or separate Wi-Fi SSIDs for IoT / guest / trusted devices
4. Enable MFA everywhere it is available (especially email & cloud storage)
5. Update/patch/replace EOL IoT devices
6. Deploy a modern software firewall & disable unnecessary services on endpoints
7. Use a password manager + enforce minimum complexity & rotation

## Lessons Learned

- **Default configurations are still the #1 easiest way in** — even in 2026, many SOHO routers ship with weak/default creds and dangerous features enabled by default.
- **IoT continues to be a massive liability** — most consumer devices never receive meaningful security updates.
- **Segmentation is cheap and powerful** — even basic VLANs or multiple SSIDs dramatically reduce blast radius.
- **MFA is no longer optional** — it stops the majority of credential-stuffing and phishing credential reuse attacks.
- **Documentation matters** — writing clear, prioritized findings + remediation steps is as important as finding the issues.
- **Small environments still need defense-in-depth** — assuming “it’s just home” leads to compromise.

## Final Thoughts

This audit shows that even modest home/small-office networks can have enterprise-level weaknesses when left on factory defaults. Applying basic hardening steps (the top 5 above) would move this environment from “easy target” to “reasonably defensible” against most opportunistic attackers.

The skills practiced here — asset visibility, configuration auditing, risk communication, and practical remediation — directly translate to real-world blue-team, SOC analyst, and security consultant roles.

Feedback and suggestions for improvement are welcome.

---
