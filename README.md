# Network Redesign and Load Balancing Using Cisco Packet Tracer

## Overview
Internship project (Sept–Dec 2018) completed for the BCSE program at IUBAT
(Dept. of CSE). The project redesigns the network of Radial International
Ltd., a composite knitwear and garment manufacturer in Gazipur, Bangladesh,
and simulates the design in Cisco Packet Tracer. It introduces network
segmentation, dynamic IP allocation, redundancy and link aggregation, and
proposes a server load balancer.

## Objectives
- Redesign the existing network infrastructure
- Separate departments using VLANs, with inter-VLAN routing
- Allocate IP addresses dynamically using DHCP
- Add redundancy for better availability
- Use EtherChannel for link aggregation and redundant links
- Use Spanning Tree Protocol (STP) for loop prevention
- Control access between departments with ACLs
- Connect the branch and head office with EIGRP and a backup path
- Propose an SNAT-based load balancer for the servers

## Network Environment
Departments: General Manager (GM), CAD, Garments Store (GS), Industrial
Engineering (IE), Information Technology (IT), Dyeing, Merchandising,
Compliance. The design also covers connectivity between the Baridhara
head office and the Gazipur branch.

## Existing Network
A three-tier hierarchical network with these limitations:
- Older networking devices
- No immediate backup path
- No load balancing
- Weak separation between departments
- No dynamic IP allocation
- Limited access control between departments

## Proposed Network
1. **Redesign:** Cisco Catalyst switches in a three-tier model
   (core, distribution, access)
2. **VLANs and inter-VLAN routing:** logical separation of departments
3. **DHCP:** dynamic IP allocation per VLAN
4. **EtherChannel and STP:** link aggregation (traffic can be distributed
   across member links), redundant links and loop prevention
5. **EIGRP:** branch-to-head-office routing with a backup path
6. **ACLs:** department-level access control
7. **SNAT load balancer (proposed):** distributes server traffic. This is
   not simulated, because Packet Tracer does not support it.

## Results
Tested in Cisco Packet Tracer using ping scenarios (see Chapter 5 of the
report):
- **Before the redesign:** all departments could ping each other with no
  restrictions.
- **After VLAN and ACL configuration:** access was restricted by department.
  For example, CAD could not ping Dyeing, while GM could reach all
  departments.
- **Redundancy:** with several links broken, a PC on one floor could still
  send data to a PC on another floor over the redundant paths.
- **Load balancing:** the SNAT load balancer could not be simulated and is
  included as a proposal only.

No throughput or latency measurements were taken, so no performance
improvement is claimed.

## Limitations
- Simulation only; not tested on real devices
- The load balancer is a proposal, not an implementation

## Repository Contents
- `packet-tracer/existing-network.pkt`: original network
- `packet-tracer/proposed-network.pkt`: redesigned network
- `documentation/project-report.pdf`: full practicum report
- `documentation/project-presentation.pdf`: defense slides

Open the `.pkt` files with Cisco Packet Tracer.

## Tools
Cisco Packet Tracer, VLAN, DHCP, EtherChannel, STP, EIGRP, ACL

## Author
Jannatul Ferdus Mim
