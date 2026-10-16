# Network segmentation and public documentation policy

## Network path

**Wired:** Fiber ONT → Nokia Beacon router/firewall → managed Cisco switch → wired infrastructure

**Wireless:** Nokia Beacon → Primary Wireless Network, Guest Wi-Fi, and IoT Wi-Fi

The router/firewall is a Nokia Beacon in the private environment. The specific Cisco switch model, management settings, firmware, and active port allocations are intentionally excluded.

Network separation is managed through rules on the Nokia Beacon. Detailed enforcement configurations are not published.

## Logical security zones

Primary Wireless Network, Guest Wi-Fi, and IoT Wi-Fi are wireless networks provided by the Nokia Beacon; this table does not imply that storage or wired servers are connected over Wi-Fi.

| Network | Role | Access model |
| --- | --- | --- |
| Primary Wireless Network | Trusted wireless clients | Primary network |
| Guest Wi-Fi | Visitor wireless connectivity | Segmented from other networks |
| IoT Wi-Fi | Wireless connected appliances and devices | Segmented from other networks |
| CyberSandbox | Proxmox cybersecurity nodes and their Kali/Fedora/Parrot VMs | Segmented testing environment; most VMs have internet access |

Sample documentation labels (not actual addresses):

| Field | Redacted example |
| --- | --- |
| Device IP | `xxx.xxx.xxx.xxx` |
| Default gateway | `xxx.xxx.xxx.xxx` |
| Network prefix | `xxx.xxx.xxx.xxx/xx` |
| Management interface | `xxx.xxx.xxx.xxx` |
| VLAN identifier | `REDACTED` |

The **CyberSandbox is the cybersecurity Proxmox VM environment**, rather than a separate external network appliance or another independent set of machines. Exact physical and virtual network configuration remains redacted.

## Threat and control considerations

- Restrict management interfaces to trusted administrative access.
- Preserve segmentation between trusted networks and guest/IoT/security testing.
- Distinguish access to the public internet from access to internal networks.
- Avoid publishing network appliance versions, firewall rule exports, and management endpoints.

This public repository contains **no live configuration exports** and is not an instruction manual for the network.
