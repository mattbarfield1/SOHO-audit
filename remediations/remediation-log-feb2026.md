# Security Remediation Log - 2026 
**Owner:** Home Office Owner

---

## Log Entries [2026-02-09]

### RC-01: BitLocker Encryption Restoration
* **Vulnerability:** Volume C: reported "Protection Off" despite being encrypted.
* **Action:** Generated new 48-digit Recovery Password; forced protection status to "On" via PowerShell.
* **Status:** **RESOLVED**
* **Verification:** `manage-bde -status` confirms protection is active.

### RC-02: Firewall Profile Correction
* **Vulnerability:** Private Network Firewall profile was set to Disabled.
* **Action:** Re-enabled Private Firewall profile via PowerShell `Set-NetFirewallProfile`.
* **Status:** **RESOLVED**
* **Verification:** Windows Security Center confirms all three profiles (Domain, Private, Public) are Active.

### RC-03: Unauthorized Software & Registry Scrub
* **Vulnerability:** Identified "repacked" VC++ binaries and residual registry artifacts (Shadow IT).
* **Action:** Uninstalled software and executed a recursive PowerShell scrub of the HKLM Registry keys.
* **Status:** **RESOLVED**
* **Verification:** `Get-ItemProperty` search for "*repacked*" returns 0 results.

### RC-04: Attack Surface Reduction (Browser & Startup)
* **Vulnerability:** Redundant extensions and unauthorized startup persistence (Steam, OneNote).
* **Action:** Manually removed Chrome extensions; disabled non-essential startup items in Task Manager.
* **Status:** **RESOLVED**
* **Verification:** Task Manager reflects "Disabled" status for non-core boot items.

### RC-05 Legacy Service Inventory & Logic Verification
- **Vulnerability:** Observed legacy manufacturer-default service profiles (e.g., "Act of War - Direct Action") within the Gateway's internal application library.
- **Risk:** Low - Potential for accidental exposure of non-essential ports if legacy profiles are erroneously assigned to active internal assets.
- **Action Taken:** Performed a manual reconciliation of the 'Hosted Applications' table against the 'Service List'. Confirmed that zero (0) legacy profiles are active or mapped to local IP addresses.
- **GRC Principle:** Enforcing **Least Functionality** by verifying that dormant firmware "bloatware" remains logically isolated from the active production environment.
- **Status:** **VERIFIED INACTIVE**

### RC-06 DHCP Scope Optimization
- **Vulnerability:** The default DHCP pool was set to a broad range (.64 - .253), creating an unnecessarily large logical footprint for unauthorized device association.
- **Action Taken:** Shrinkage of the DHCP scope is scheduled to match the current asset inventory + a 10% buffer for guest traffic.
- **Status:** **PENDING**

### RC-07 Network Perimeter Validation (Post-Remediation)
- **Vulnerability:** Verification of the 'Default Deny' firewall posture following the rotation of the Device Access Code.
- **Action Taken:** Executed a full-spectrum external scan of 1,056 ports via GRC ShieldsUP!.
- **Result:** **100% STEALTH**. The scan confirmed that the gateway does not respond to unsolicited probes, effectively masking the presence of the home network from the public internet.
- **Status:** **PASSED / COMPLETE**

---

**Total Risks Remediated:** 7  
**Current Security Posture:** Hardened / Baseline Compliant
