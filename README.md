# IP Database (IPDB)

## Overview

The **IP Database (IPDB)** is a centralized system that serves as the **authoritative source of truth** for network infrastructure. It correlates devices, ports, VLANs, MAC addresses, physical locations, power and environmental data, authentication state, and operational status across multiple campuses and environments.

IPDB is designed to answer critical operational questions quickly and reliably:

- What is connected?
- Where is it connected?
- How is it authenticated?
- What is its current and historical state?

---

## Key Features

### Deep Network Awareness

IPDB models network infrastructure at a level beyond traditional CMDBs, including:

- Switches, stacks, line cards, ports, and VLANs
- End-to-end relationships:  
  `MAC → Port → Switch → Building → Campus`
- SNMP-derived operational state:
  - Interface status
  - Power supplies
  - Stack members
  - Temperature sensors
- Vendor-specific behavior and capabilities (Cisco Catalyst/Nexus, Juniper, etc.)

---

### Location-Driven Data Model

All objects are associated with **property IDs, campuses, buildings, closets, and rooms**, enabling:

- Scoped views and actions by campus or building
- Site-specific configuration and policy enforcement:
  - Credentials
  - ClearPass servers
  - SNMP profiles
- Correlation of physical constraints (power, HVAC, temperature) with network risk

---

### Security and Access Control Integration

IPDB integrates directly with network access control and security workflows:

- ClearPass integration for switches and MAC address management
- Static host lists and blacklist management
- Permission-aware UI and APIs
- Auditable actions with controlled privilege escalation (admin vs non-admin)

---

### Automation-First Architecture

IPDB is an active system, not a passive database:

- Automatic discovery and maintenance of MAC-to-port mappings
- API-driven integration with external systems
- Automated ticket and alert generation for hardware and policy violations
- Shared JSON interfaces for both CLI and web-based automation

---

### Unified Telemetry Pipeline

IPDB acts as a central correlation layer within a broader monitoring ecosystem:

- SNMP polling for hardware and interface state
- Time-series data integration (InfluxDB)
- Dashboard and alert consumption via Grafana
- Contextual linking of Elasticsearch and OpenNMS logs back to network devices

---

### Operator-Focused Design

The system is built for day-to-day network operations:

- Rapid navigation from switches to ports, MACs, logs, power, and history
- Inline modals for contextual actions (e.g. EOX lookups, live logs)
- Bulk operations for large-scale environments
- Fast answers during incidents (e.g. *“What is on this port right now?”*)

---

## Integrations

IPDB integrates with a number of existing network and infrastructure platforms to provide unified visibility and automation:

- **ClearPass** – Network access control integration for switch and MAC-based policy enforcement
- **Infoblox** – IP address management (IPAM), DNS, and DHCP correlation
- **OpenNMS** – Fault and performance monitoring with contextual device linkage
- **WhatsUp Gold** – Device availability, alerting, and operational state visibility
- **Aruba Controllers** – Wireless infrastructure integration for client and access point visibility
- **Cisco CMS** – Collaboration infrastructure integration for endpoint and service awareness
- **ServiceNow** *(in progress)* – Incident, change, and asset lifecycle integration
- **Cisco Support APIs** – Serial number validation and automated End-of-Support / End-of-Life checks / Version CVEs
- **Juniper Support APIs** – Automated End-of-Support / End-of-Life checks
---

## What Makes IPDB Different

IPDB stands apart by design:

- **Opinionated** – Encodes how the network actually operates
- **Deeply integrated** – Not a wrapper around vendor tools
- **State-aware** – Combines real-time visibility with historical context
- **Dual-purpose** – Functions as both a control plane and a visibility plane

---

## In Practice

IPDB functions as a hybrid of:

- CMDB
- Network discovery engine
- Automation framework
- Operational dashboard

Built to reflect the real-world complexity of a large, multi-campus enterprise network.
