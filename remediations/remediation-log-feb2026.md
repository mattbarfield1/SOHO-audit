# Security Remediation Log - 2026
**Asset ID:** LAPTOP-ABCD123  
**Owner:** Home Office Owner

---

## Log Entries

### [2026-02-09] RC-01: BitLocker Encryption Restoration
* **Vulnerability:** Volume C: reported "Protection Off" despite being encrypted.
* **Action:** Generated new 48-digit Recovery Password; forced protection status to "On" via PowerShell.
* **Status:** **RESOLVED**
* **Verification:** `manage-bde -status` confirms protection is active.

### [2026-02-09] RC-02: Firewall Profile Correction
* **Vulnerability:** Private Network Firewall profile was set to Disabled.
* **Action:** Re-enabled Private Firewall profile via PowerShell `Set-NetFirewallProfile`.
* **Status:** **RESOLVED**
* **Verification:** Windows Security Center confirms all three profiles (Domain, Private, Public) are Active.

### [2026-02-09] RC-03: Unauthorized Software & Registry Scrub
* **Vulnerability:** Identified "repacked" VC++ binaries and residual registry artifacts (Shadow IT).
* **Action:** Uninstalled software and executed a recursive PowerShell scrub of the HKLM Registry keys.
* **Status:** **RESOLVED**
* **Verification:** `Get-ItemProperty` search for "*repacked*" returns 0 results.

### [2026-02-09] RC-04: Attack Surface Reduction (Browser & Startup)
* **Vulnerability:** Redundant extensions and unauthorized startup persistence (Steam, OneNote).
* **Action:** Manually removed Chrome extensions; disabled non-essential startup items in Task Manager.
* **Status:** **RESOLVED**
* **Verification:** Task Manager reflects "Disabled" status for non-core boot items.

---
**Total Risks Remediated:** 4  
**Current Security Posture:** Hardened / Baseline Compliant
