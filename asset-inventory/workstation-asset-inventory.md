# Workstation Asset Inventory

**Objective:** Conduct a granular audit of the primary workstation to identify software-level vulnerabilities and configuration gaps.
**Scope:** Primary Laptop identified in Network Inventory.

## System Configuration
| Component | Specification | Compliance Status |
| :--- | :--- | :--- |
| **Operating System** | Windows 11, 25H2 | Up To Date 2/9/2026 |
| **Hostname** | LAPTOP-ABCD123 | Managed |
| **Primary Browser** | Chrome | Version: 144.0.7559.133 (64-bit) |

## Initial Endpoint Observations
* **Patch Management:** Automatic updates enabled.
* **Attack Surface Reduction:** No unnecessary profiles found.

## Security Controls Baseline
| Control | Status | Methodology |
| :--- | :--- | :--- |
| **Antivirus** | Active | System Settings Review |
| **System Firewall** | Partially Enabled | Configuration Audit |
| **Disk Encryption** | Disabled | Security Settings Check |
| **VPN Client** | None | Application Review |

## Security Controls Baseline (Post-Audit)
| Control | Status | Methodology |
| :--- | :--- | :--- |
| **Antivirus** | Active (Windows Defender) | PowerShell `Get-MpComputerStatus` |
| **System Firewall** | Active (All Profiles) | Verified & Remediation Applied |
| **OS Patch Level** | Windows 11 25H2 | `winver` / Windows Update |
| **Disk Encryption** | Enabled (BitLocker) | `manage-bde -status` (Protection On) |

## Approved Software Inventory
| Application | Publisher | Purpose |
| :--- | :--- | :--- |
| **Visual Studio Community 2022** | Microsoft | Development |
| **Adobe Creative Cloud / InDesign** | Adobe Inc. | Creative / Design |
| **Google Chrome / Microsoft Edge / Firefox** | Google / MSFT / Mozilla | Web Browsing |
| **Python Launcher** | Python Foundation | Development |
| **Steam** | Valve Corp | Personal / Gaming |

## Audit Findings (Software)
* **Unnecessary Services:** Canon Extended Survey Program (Privacy Risk).
* **High Risk:** "Microsoft VC++ redistributables repacked" - Non-standard source for system files.
* **Bloatware:** Dell SupportAssist Remediation (Historical vulnerability risk).

## Browser & Extension Audit: Comparative Analysis

### Pre-Audit Snapshot (Baseline)
| Browser | Initial Status | Extension Count | Identified Risks |
| :--- | :--- | :--- | :--- |
| **Google Chrome** | At Risk | 2 | Adblock Plus (Data privacy), McAfee WebAdvisor (Bloat) |
| **Mozilla Firefox** | Hardened | 0 | None |
| **Microsoft Edge** | Baseline | 0 | None |

### Post-Audit (Current Hardened State)
| Browser | Final Status | Extension Count | Remediation Action |
| :--- | :--- | :--- | :--- |
| **Google Chrome** | **Hardened** | 0 | Manual removal of all 3rd party extensions |
| **Mozilla Firefox** | **Hardened** | 0 | Verified zero-extension policy |
| **Microsoft Edge** | **Hardened** | 0 | Verified zero-extension policy |

## Startup Program Audit: Persistence Management

### Pre-Audit Startup Snapshot (Unfiltered)
| Process Name | Publisher | Impact | Risk/Reason for Review |
| :--- | :--- | :--- | :--- |
| **Steam** | Valve Corp | High | Non-business persistence; background resource drain. |
| **Send to OneNote** | Microsoft | Low | Redundant bloatware; unnecessary background process. |
| **OneDrive (x2)** | Microsoft | Low | Configuration drift; redundant setup entries identified. |
| **Adobe Acrobat Sync** | Adobe Inc. | Medium | Third-party background telemetry and update checker. |

### Post-Audit Hardened State (Persistence Control)
| Process Name | Final Status | Justification |
| :--- | :--- | :--- |
| **SecurityHealth** | **Enabled** | Critical: Windows Defender/Security Center notification tray. |
| **RtkAudUService** | **Enabled** | Necessary: Core hardware driver for system audio. |
| **Steam** | **Disabled** | Remediated: Manual launch only to reduce attack surface. |
| **Send to OneNote** | **Disabled** | Remediated: Removed non-essential background utility. |
| **OneDrive** | **Consolidated** | Optimized: Cleaned redundant setup triggers. |

> **Audit Note:** All unauthorized or non-essential startup persistence has been disabled via Task Manager. The system boot sequence is now restricted to "Known Necessary" services only.
