# Data Classification Policy & Inventory
**Asset Owner:** Home Office Owner  
**System ID:** LAPTOP-ABCD123

---

## 1. Classification Definitions
We categorize data based on the "Impact of Disclosure" (what happens if this leaks?).

| Level | Label | Description | Impact |
| :--- | :--- | :--- | :--- |
| **L3** | **Confidential** | PII, Financials, Legal Docs. | **High:** Identity theft or financial loss. |
| **L2** | **Private** | Intellectual Property, eBooks, Projects. | **Medium:** Loss of work or privacy. |
| **L1** | **Public** | Gaming mods, public resumes, generic logs. | **Low:** No significant impact. |

---

## 2. Asset Inventory & Mapping
| Data Asset | Content Examples | Level | Storage Requirement |
| :--- | :--- | :--- | :--- |
| **Identity Scans** | SSN Card, Driver's License | **L3** | BitLocker + EFS (Encrypted Folder) |
| **Tax Records** | 1040 Forms, W2 Scans | **L3** | BitLocker + EFS |
| **Creative Works** | eBook Drafts, Design Files | **L2** | BitLocker + Cloud Backup |
| **Dev Environment** | Python Scripts, VS Projects | **L2** | BitLocker + Git/Cloud |
| **Fitness Data** | Workout Programs, Health Logs | **L2** | BitLocker |
| **Gaming/Media** | Fallout Mods, Steam Library | **L1** | Standard Volume |

---

## 3. Handling Requirements
* **Confidential (L3):** Must never be stored on unencrypted USB drives or unapproved cloud providers.
* **Private (L2):** Requires routine backups to an external encrypted drive.
* **Public (L1):** No specific encryption requirements.

 ---

## Mobile Asset Inventory: iPhone (L3 - Confidential)
| Field | Specification | GRC Requirement |
| :--- | :--- | :--- |
| **Asset Name** | iPhone-Mobile-01 | **Compliance:** Must be tracked in inventory. |
| **Owner** | Home Office Owner | **Compliance:** Assigned to primary user. |
| **OS Version** | iOS 26.2.1 | **L3:** Must be within 1 major version of current. |
| **Access Control** | FaceID + Passcode | **L3:** Minimum 6-digit alphanumeric preferred. |
| **Find My iPhone** | Enabled | **L3:** Mandatory for Remote Wipe capability. |
| **Credential Vault** | iCloud Keychain | **L3:** 2FA mandatory for Apple ID. |
| **Backup Status** | iCloud Encrypted | **L3:** Daily backup required for recovery. |
