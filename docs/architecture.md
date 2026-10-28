# Network Architecture

## Overview

This project implements a Network Access Control (NAC) solution using Cisco Identity Services Engine (ISE) and Microsoft Active Directory.

The infrastructure uses IEEE 802.1X authentication, RADIUS, dynamic VLAN assignment, and downloadable Access Control Lists (dACLs) to enforce role-based network access.

## Infrastructure Components

| Component | Technology | Function |
|---|---|---|
| NAC Server | Cisco ISE 3.0 | Centralized authentication and authorization |
| Directory Server | Windows Server 2022 | Active Directory, DNS, DHCP, and AD CS |
| Network Switch | Cisco Catalyst 3750 | 802.1X enforcement and VLAN assignment |
| Router | Cisco 1900 | Network connectivity |
| Endpoints | Windows 10 | Domain-joined client devices |
| Virtualization | VMware Workstation | Hosting the virtual servers |

## Network Segmentation

| VLAN | Name | Subnet |
|---|---|---|
| 2 | Management | 10.0.0.0/24 |
| 10 | Administrators | 10.0.10.0/24 |
| 20 | Employees | 10.0.20.0/24 |

## Authentication Workflow

1. A client connects to an 802.1X-enabled switch port.
2. The switch initiates authentication through Cisco ISE using RADIUS.
3. Cisco ISE validates the user's identity through Active Directory.
4. An authorization policy is selected according to the user's role.
5. Cisco ISE returns the appropriate network authorization attributes.
6. The switch applies the authorized VLAN and access restrictions.

## Access Control

The project uses role-based authorization policies to differentiate network access for administrators, employees, network sponsors, and system sponsors.

Dynamic VLAN assignment and dACLs help restrict access to network resources according to each role.

## Implementation Limitations

Guest portal functionality and endpoint posture assessment were not fully deployed due to infrastructure and licensing constraints.
