# Home Office Security Audit: Phase 1 (Asset Discovery & Inventory)

## 1A: Network Device Inventory
**Objective:** Establish a comprehensive baseline of all hardware assets within the network perimeter.
**Methodology:** Reconciled ISP Router DHCP client list against physical device verification using MAC address.

| Asset Name | Connection Type | Frequency/Interface | Status |
| :--- | :--- | :--- | :--- |
| **ISP Gateway** (Router/Modem) | WAN/LAN | N/A | Known |
| **Owner iPhone** | Wireless | 6GHz | Known |
| **Owner Android Phone** | Wireless | 6GHz | Known |
| **Primary Laptop** | Hybrid (Eth/WiFi) | 2.4GHz (Wireless) | Known |
| **PS5 (Living Room)** | Ethernet | Hardwired | Known |
| **PS5 (Basement)** | Wireless | 5GHz | Known |
| **Smart TV** | Wireless | 5GHz | Known |
| **Smart Thermostat** | Wireless | 2.4GHz | Known |
| **Smart Lock** | Wireless | 2.4GHz | Known |
| **Printer** | Wireless | 2.4GHz | Known |
| **Guest Devices** | Wireless | Unmanaged | Known |

## Initial Observations & Gap Analysis
Based on the discovery phase, the following security gaps were identified for further assessment in the Risk Report:

* **Lack of Network Segmentation:** Guest devices and IoT (Smart Lock/Thermostat) reside on the same subnet as primary data-handling devices (Laptop/Phones), increasing the risk of lateral movement.
* **Unoptimized Wireless Perimeter:** The primary laptop utilizes the 2.4GHz band, which is more susceptible to interference and congestion compared to the 5GHz/6GHz bands used by mobile devices.
* **Unmanaged Guest Access:** Current configuration does not utilize a dedicated Guest Network, creating a persistent vulnerability regarding unauthorized access to internal resources.
