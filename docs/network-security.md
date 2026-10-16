# Network segmentation and public documentation policy

## Network path

**Fiber ONT → ISP router/firewall → managed Cisco switch → wired infrastructure**

The router/firewall is a Nokia Beacon in the private environment. The specific Cisco switch model, management settings, firmware, and active port allocations are intentionally excluded.

The operator reports firewall rules on the gateway. Exact rule behavior and whether VLAN routing is performed exclusively at that device have **not** been verified.

## Logical security zones

| Network | Intended role | Isolation status |
| --- | --- | --- |
| Primary | Trusted personal workstations, storage, and infrastructure access | Separate logical zone; detailed rules unverified |
| Guest | Visitors and untrusted guest connectivity | Isolation reported, not independently tested |
| IoT | Connected appliances and devices | Isolation reported, not independently tested |
| CyberSandbox | Cybersecurity research and test systems | Isolation reported; most test VMs have internet access |

Sample documentation labels (not actual addresses):

| Field | Redacted example |
| --- | --- |
| Device IP | `xxx.xxx.xxx.xxx` |
| Default gateway | `xxx.xxx.xxx.xxx` |
| Network prefix | `xxx.xxx.xxx.xxx/xx` |
| Management interface | `xxx.xxx.xxx.xxx` |
| VLAN identifier | `REDACTED` |

## Threat and control considerations

- Restrict management interfaces to trusted administrative access.
- Preserve segmentation between trusted networks and guest/IoT/security testing.
- Distinguish access to the public internet from access to internal networks.
- Avoid publishing network appliance versions, firewall rule exports, and management endpoints.
- Validate isolation and device management exposure before describing security policies as verified enforcement.

This public repository contains **no live configuration exports** and is not an instruction manual for the network.
