
# Network Access Control (NAC) Implementation with Cisco ISE

## Project Overview

This project focuses on the implementation of a Network Access Control (NAC) solution using **Cisco Identity Services Engine (ISE)** integrated with **Microsoft Active Directory**.

The main objective is to strengthen network security through centralized authentication, dynamic VLAN assignment, and role-based access control policies.

The solution was implemented and tested using physical Cisco networking equipment and virtualized Windows Server infrastructure.

This academic project was developed at **TechnoLAB-ISTA** as part of the Computer Systems and Networks program.

## Technologies Used

- Cisco Identity Services Engine (ISE) 3.0
- Microsoft Windows Server 2022
- Active Directory Domain Services (AD DS)
- Active Directory Certificate Services (AD CS)
- DNS and DHCP
- IEEE 802.1X and RADIUS
- Cisco Catalyst 3750 Layer 3 Switch
- Cisco 1900 Series Router
- VMware Workstation
- Windows 10 Client Devices

## Project Objectives

- Implement centralized network authentication using Cisco ISE.
- Integrate Cisco ISE with Microsoft Active Directory.
- Configure IEEE 802.1X authentication using RADIUS.
- Assign VLANs dynamically based on Active Directory groups.
- Implement downloadable Access Control Lists (dACLs).
- Enforce role-based network access policies.
- Verify authentication and authorization through practical tests.

## Network Architecture

The infrastructure consists of a Cisco router, a Cisco Catalyst switch, a Cisco ISE server, a Windows Server hosting Active Directory services, and Windows client devices.

Cisco ISE acts as the centralized authentication and authorization server, while the switch enforces network access policies.

### Network Segmentation

| VLAN | Name | Network |
|---|---|---|
| 2 | Management | 10.0.0.0/24 |
| 10 | Administrators | 10.0.10.0/24 |
| 20 | Employees | 10.0.20.0/24 |

### Authentication Workflow

1. A user connects a device to the network.
2. The Cisco switch initiates IEEE 802.1X authentication.
3. Cisco ISE processes the RADIUS authentication request.
4. User identity and group membership are checked through Active Directory.
5. Cisco ISE applies the corresponding authorization policy.
6. The switch assigns the appropriate VLAN and enforces the access restrictions.

## Network Access Policies

Four user profiles were tested during the implementation.

| User Role | VLAN | Authorized Access |
|---|---|---|
| Administrators | VLAN 10 | Internet, Active Directory, Cisco ISE, and network equipment |
| Employees | VLAN 20 | Internet access only |
| Network Sponsors | VLAN 20 | Internet and authorized network equipment |
| System Sponsors | VLAN 20 | Internet and Active Directory |

Access restrictions were enforced through Cisco ISE authorization policies and downloadable ACLs.

## Validation and Results

The implementation was validated through authentication and connectivity tests.

The tests confirmed:

- Successful IEEE 802.1X authentication.
- Dynamic VLAN assignment based on user roles.
- Successful RADIUS authentication through Cisco ISE.
- Enforcement of network access restrictions.
- Successful verification using Cisco ISE and switch logs.
- Separation of network privileges between administrators, employees, and sponsors.

The results demonstrated the effectiveness of centralized network access control in the implemented environment.

## Implementation Challenges

Several technical challenges were encountered during the project:

### Certificate Management

An internal Certificate Authority was configured using Active Directory Certificate Services.

Group Policy Objects (GPOs) were used to distribute trusted certificates to domain-joined computers.

### Authentication and Authorization Troubleshooting

Authentication failures were investigated through Cisco ISE logs and network device configurations.

Authorization policies were adjusted to allow successful authentication and enforce the appropriate access restrictions.

### Guest Access and Posture Assessment

Guest portal functionality and endpoint posture assessment could not be fully deployed due to infrastructure and licensing limitations.

These limitations were documented as potential future improvements.

## Project Documentation

| Document | Description |
|---|---|
| [Network Architecture](docs/architecture.md) | Network components, VLAN segmentation, and authentication workflow |
| [Validation Tests](docs/validation-tests.md) | Authentication results and access control verification |
| Project Report | Complete academic project report (coming soon) |
| Video Demonstration | Recorded authentication and authorization tests (coming soon) |

## Project Status

**Status:** Completed academic project — documentation in progress.

The implementation and validation tests were performed using physical Cisco networking equipment and virtualized servers.

The original laboratory environment is no longer available. This repository documents the configurations, implementation process, and results obtained during the project.

## Contributors

This project was developed collaboratively by:

- Seydou BA
- Aldjouma DOURBELA
- Samba SERY
- Exaucé NGOMAÏDE

**Institution:** TechnoLAB-ISTA

**Program:** Computer Systems and Networks

## Disclaimer

This repository is intended for educational and technical documentation purposes.

Sensitive authentication credentials and secrets must be removed from publicly shared configurations and documentation.
