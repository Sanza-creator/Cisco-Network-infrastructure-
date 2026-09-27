# Network Infrastructure Projects

Two tiers of networking work: a full enterprise-grade capstone design, and a set of foundational Cisco Packet Tracer labs that built up the skills behind it.

---

## 1. Enterprise Multi-Site Network Redesign — Nexus Logistics (Capstone)

### Scenario
Nexus Logistics, a regional shipping firm, was running on a flat, unsegmented Layer 2 network between its Central Warehouse (CW) and a new Distribution Hub (DH) — causing broadcast storms and exposing financial data across the whole internal network. I redesigned the infrastructure as a secure, hierarchical, hybrid-cloud-ready network.

### What I did
- **Addressing & subnetting:** Subnetted a `10.10.0.0/18` supernet using VLSM to support Central Warehouse Operations (400 hosts), CW Management (100 hosts), DH Logistics (200 hosts), DH Security/CCTV (50 hosts), and a `/30` WAN point-to-point link — sized with 30% future growth headroom
- **Hierarchical design:** Implemented Cisco's Three-Layer Model (Core, Distribution, Access) across the topology
- **Routing:** Configured hierarchical OSPF (Area 0 for CW, Area 10 for DH) with loopback-based Router IDs, passive interfaces on LAN-facing ports, and verified adjacencies/route propagation via `show ip ospf neighbor` and `show ip route`
- **Segmentation:** Built VLANs per department (Finance, Admin, Warehouse Operations), configured SVIs for inter-VLAN routing, 802.1Q trunking, and ACLs on Layer 3 switches to control inter-department access
- **Resilience:** Deployed Rapid PVST+ for loop prevention and fast failover, and EtherChannel (LACP) between distribution and access switches for increased bandwidth and link redundancy
- **Edge security:** Configured port security (one MAC per port, shutdown on violation), PortFast and BPDU Guard on all end-user ports
- **Hybrid cloud readiness:** Designed the architecture around a site-to-site IPsec VPN concept to securely link CW and DH as the organisation migrates tracking data to the cloud
- **Validation:** Simulated a link failure between Distribution and Access switches and documented how RSTP and EtherChannel restored connectivity

### Skills demonstrated
`OSPF (multi-area)` · `VLSM subnetting` · `VLANs & inter-VLAN routing (SVIs)` · `RSTP/EtherChannel` · `ACLs` · `Port security` · `Three-layer hierarchical design` · `IPsec VPN concepts`


---

## 2. Foundational Network Builds (Cisco Packet Tracer)

Before the capstone, I built and configured a series of smaller networks to develop core skills in addressing, switching, routing, and services — framed around a small retail chain expanding its IT footprint.

**Scenario:** A growing retail business needed its head office and branch locations connected and properly managed as it scaled from a single office to a multi-site operation.

- **Company Network Setup** — Designed and configured the head office network: device addressing, switch/router configuration, and end-to-end connectivity verification via `ping`/`tracert`
- **Small Office Networking** — Built a lean branch-office network suitable for a small user base, with basic connectivity and access configuration
- **DHCP Server Configuration** — Deployed DHCP scopes to automatically assign addressing across the network, removing the need for manual IP configuration on client devices
- **VLAN Configuration** — Segmented the network by department for traffic control and security, configuring trunk/access ports and verifying with `show vlan brief`
- **Campus Area Network** — Extended the design into a multi-building, campus-style topology as the business grew to multiple physical locations

### Skills demonstrated
`Cisco IOS` · `Static & default routing` · `DHCP` · `VLANs & trunking` · `Network troubleshooting`


