# Router & Network Security Assessment

## 1. Scope & Methodology
- **Target:** AT&T Residential Gateway (Perimeter Security)
- **Methodology:** Manual configuration review via web interface and external vulnerability scanning.
- **Audit Date:** February 9, 2026

## 2. Gateway Information
- **ISP:** AT&T
- **Device Model:** [e.g., BGW320 / BGW210]
- **Management IP:** (nnn.nnn.n.nnn)

## 3. Findings Summary Table
| Finding ID | Control Category | Vulnerability | Likelihood | Impact | Risk Rating | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **NET-001** | Authentication | Default Device Access Code in use | High | Critical | **CRITICAL** | **Remediated** |
| **NET-002** | Vulnerability Mgmt | Firmware 2 versions behind current | High | High | **HIGH** | Pending Update |
| **NET-003** | Network Services | UPnP Capability | N/A | Low | **PASS** | No Support |
| **NET-004** | Remote Access | Remote Management Port | Low | High | **PASS** | Disabled |

---

## 4. Detailed Findings & Evidence

### [NET-001] Default Admin Credentials
- **Description:** The gateway was using the manufacturer-provided "Device Access Code" printed on the physical label.
- **Risk:** If an attacker gains physical proximity or local network access, they can gain full administrative control of the network perimeter.
- **Remediation:** Admin password was changed to a unique, 16+ character complex string.

### [NET-002] Outdated Firmware
- **Description:** The router firmware was identified as being two versions behind the latest release from AT&T.
- **Risk:** Outdated firmware often contains known vulnerabilities (CVEs) that can be exploited to bypass security controls.
- **Recommendation:** Perform a manual update check via the "Diagnostics" or "Status" tab to reach current version.

### [NET-003] UPnP Configuration (Technical Limitation)
- **Description:** Investigation confirmed that the AT&T Gateway firmware does not support UPnP. 
- **GRC Analysis:** This is a positive "Inherent Control." By omitting UPnP, the device prevents internal software from automatically opening inbound firewall holes, enforcing the **Principle of Least Functionality**.

### [NET-004] External Perimeter Scan (ShieldsUP!)
- **Tool:** GRC ShieldsUP! (grc.com/shieldsup) 
- **Scope:** 1,056 Common Service Ports
- **Result:** **PASSED (100% Stealth)**
- **Finding:** A comprehensive external perimeter scan resulted in a perfect 'Stealth' rating, confirming that the AT&T Gateway firewall is correctly configured to drop all unsolicited inbound traffic and effectively hide the network from external discovery.
- **GRC Significance:** This validates the "Boundary Protection" control, ensuring that only authorized communication is permitted through the network perimeter.

### [NET-005] WiFi Configuration Review
- **Encryption:** WPA3 (Verified)
- **SSID Broadcast:** Enabled (Standard Compliance)
- **WPS Status:** Not supported/Disabled (Inherent Security Control)

### [NET-006] Network Segmentation (Guest Network)
- **Finding:** No Guest Network currently active.
- **Risk:** Lack of segmentation between trusted and untrusted (guest) devices.
- **Likelihood:** Medium | **Impact:** Medium | **Risk Rating:** MEDIUM
- **Recommendation:** Enable Guest SSID with a unique password and "Internet Only" permissions to isolate visitor traffic from the internal LAN.

### [NET-007] DHCP Scope Configuration
- **Observation:** DHCP range is configured from .64 to .253 (190 addresses).
- **Risk:** An excessively large DHCP pool increases the difficulty of identifying unauthorized "rogue" assets joining the network.
- **Likelihood:** Low | **Impact:** Low | **Risk Rating:** LOW
- **Recommendation:** Shrink the DHCP pool to the number of known assets + 5-10 for guests to improve network visibility.

### [NET-008] DNS Privacy & ISP Constraints
- **Observation:** Gateway utilizes ISP default DNS servers; manual override is restricted by firmware.
- **Risk:** DNS traffic is unencrypted, allowing for potential ISP logging or DNS hijacking/poisoning.
- **Compensating Control:** Implement Endpoint-level DNS protection (e.g., DNS-over-HTTPS via Cloudflare 1.1.1.1) on the laptop to bypass router-level limitations.

### [NET-009] Ingress Filtering (Port Forwarding)
- **Status:** **PASS**
- **Evidence:** Verified via "NAT/Gaming" interface that no application hosting entries exist.
- **Result:** The perimeter is closed to unsolicited inbound traffic, maintaining a "Default Deny" posture.

---

## 5. GRC Reflection
Securing the network perimeter is a fundamental "Hardening" activity. By identifying the default password and outdated firmware, I am performing **Vulnerability Management** and **Access Control** reviews—core components of frameworks like NIST 800-53 and ISO 27001.
