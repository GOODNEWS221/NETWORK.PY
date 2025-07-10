# NETWORK.PY



# 🧠 MPLS Layer 3 VPN: Multi-VRF Enterprise Simulation

## 📘 Overview

This project is a hands-on simulation of a **service provider-grade MPLS Layer 3 VPN** deployment, built to deliver **scalable and secure enterprise connectivity** using Cisco IOS routers.

I configured a full MPLS backbone that supports **multiple isolated customer networks** via **VRFs**, using **OSPF, MP-BGP, and LDP** to establish a robust control and data plane. This topology mimics how real ISPs provide **multi-tenant L3VPN services** to clients across distributed locations.

---

## 🧱 Architecture

- **PE Routers (Provider Edge)**: Multi-VRF configuration, responsible for separating customer routing tables.
- **P Router (Provider/Core)**: MPLS core, no customer awareness, pure label switching.
- **CE Routers (Customer Edge)**: Each enterprise runs OSPF with the PE to advertise and learn routes.
- **Backbone**: MPLS using LDP over OSPF, with loopbacks as router-IDs and MP-BGP peering endpoints.

---

## 🔧 Technologies Used

| Protocol | Purpose                         |
|----------|----------------------------------|
| **MPLS** | Label-switched transport core    |
| **LDP**  | Label distribution between P/PE  |
| **VRF**  | Per-customer route separation    |
| **MP-BGP**| VPNv4 route exchange between PEs|
| **OSPF** | CE-to-PE dynamic routing         |

---

## 🧪 Features Implemented

- ✅ **Multiple VRFs** on a single PE: `PRESHHQ`, `PRESHBR`, `GOODHQ`, `GOODBR`
- ✅ **OSPF routing within each VRF**
- ✅ **MP-BGP (VPNv4)** peering between PEs with `send-community both`
- ✅ **Route-Target (RT)** configuration to control import/export between customer sites
- ✅ **LDP + MPLS label switching** for end-to-end forwarding

---

## 📶 Test Coverage

| Test | Result |
|------|--------|
| OSPF adjacency per VRF | ✅ |
| BGP VPNv4 routes exchanged | ✅ |
| VRF route segregation | ✅ |
| CE ↔ CE reachability across PE-P core | ✅ |
| Multiple customer coexistence | ✅ |

🌍 Use Cases Simulated
Multi-site enterprise with HQ and Branches over MPLS

Different customers on same infrastructure without IP conflict

Dynamic routing with automatic redistribution between BGP and OSPF

📈 Future Improvements
 Route Leaking between VRFs (shared services)

 NAT or Internet breakout from PE router

 CE redundancy (dual-homed)

 Python automation of VPN provisioning

 Integration with network monitoring dashboard (Netmiko + Django)

📌 Skills Demonstrated
Designing scalable service provider topologies

Advanced MPLS and VRF configuration

BGP route control and L3VPN fundamentals

CE-PE routing with OSPF

Isolation and multi-tenancy through RT/RD

🤝 Connect
This project is a demonstration of my networking proficiency at a CCNP/Service Provider level.
I'm open to feedback, contributions, or collaboration.

Built by Goodnews Atekha
💼 Network Engineer | Backend Dev in Progress | Cybersecurity Enthusiast
📫 LinkedIn | Twitter | GitHub
