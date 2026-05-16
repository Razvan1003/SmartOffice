# SmartOffice LAN

Cisco Packet Tracer project for designing and validating a segmented LAN for a smart office environment.

The project demonstrates VLAN-based department separation, inter-VLAN routing, DHCP, NAT, switching features and basic access-control configuration.

## Scenario

The office network is split into departments and services:

| VLAN | Name | Subnet | Gateway |
| --- | --- | --- | --- |
| 10 | ADMIN | `192.168.10.0/24` | `192.168.10.1` |
| 20 | FIN_HR | `192.168.20.0/24` | `192.168.20.1` |
| 30 | SALES | `192.168.30.0/24` | `192.168.30.1` |
| 40 | IT | `192.168.40.0/24` | `192.168.40.1` |
| 50 | VOIP | `192.168.50.0/24` | `192.168.50.1` |
| 99 | GUEST_WIFI | `192.168.99.0/24` | `192.168.99.1` |

## Implemented Features

- Star-style LAN topology with a central Cisco router and Cisco 2960 switches
- VLAN segmentation by department
- Trunk links between switching/routing devices
- Inter-VLAN routing
- DHCP address allocation
- NAT for simulated external access
- STP verification
- VTP status verification
- Hierarchical local user access for router administration

Telnet is used only as a Packet Tracer lab mechanism. In production, SSH should be used instead.

## Files

```text
Proiect.pkt        # Cisco Packet Tracer topology
smartoffice.pdf    # project documentation and validation screenshots
README.md          # repository documentation
```

## Devices Used

- Cisco 2911 router
- Cisco 2960 switches
- PCs and laptops
- IP phones
- wireless router / access point
- simulated Internet cloud

## Validation Commands

| Area | Command |
| --- | --- |
| VLANs | `show vlan brief` |
| Trunks | `show interfaces trunk` |
| Routing | `show ip route` |
| DHCP | `show ip dhcp binding` |
| NAT | `show ip nat translations` |
| STP | `show spanning-tree` |
| VTP | `show vtp status` |
| Remote access | `telnet` / `login local` |

## How To Open

1. Install Cisco Packet Tracer.
2. Open `Proiect.pkt`.
3. Review VLANs, trunk links and router configuration.
4. Use the commands above to verify each configured feature.
5. Read `smartoffice.pdf` for the full project report and screenshots.

## What This Project Demonstrates

This lab shows the ability to design, document and validate a small enterprise LAN with practical Cisco networking concepts. It is useful as a foundation for later automation work with GNS3, Netmiko and configuration backup/verification scripts.

## Suggested Improvements

- Add exported router and switch configuration files under `configs/`
- Add a topology image under `docs/topology.png`
- Add validation command outputs under `validation/`
- Add an ACL section to separate guest traffic more clearly
- Create a follow-up automation repo using GNS3 and Netmiko
