# Network Access Control (NAC) Implementation with Cisco ISE

## Project Overview

This project focuses on implementing a Network Access Control (NAC) solution using Cisco Identity Services Engine (ISE) integrated with Microsoft Active Directory.

The objective is to strengthen network security by authenticating users and dynamically applying access control policies based on their roles.

The project was developed as part of an academic network and systems administration program.

## Technologies Used

- Cisco Identity Services Engine (ISE) 3.0
- Microsoft Windows Server 2022
- Active Directory Domain Services (AD DS)
- Active Directory Certificate Services (AD CS)
- IEEE 802.1X and RADIUS
- Cisco Catalyst 3750 Layer 3 Switch
- Cisco Router
- VMware Workstation

## Project Objectives

- Implement centralized network authentication using Cisco ISE.
- Integrate Cisco ISE with Microsoft Active Directory.
- Configure IEEE 802.1X authentication.
- Assign VLANs dynamically based on user authorization policies.
- Apply downloadable Access Control Lists (dACLs).
- Test network access restrictions for different user roles.

## Network Access Policies

| User Role | Network Access |
|---|---|
| Administrators | Access to authorized internal resources and the Internet |
| Employees | Restricted access, primarily to the Internet |
| Network Sponsors | Access to authorized network equipment |
| System Sponsors | Access to authorized system resources |

## Implementation Challenges

During the implementation, several challenges were encountered:

- Certificate deployment and trust configuration.
- Authentication and authorization policy troubleshooting.
- Network access restrictions based on user roles.
- Guest portal deployment limitations.

These challenges provided practical experience in network access security, troubleshooting, and identity management.

## Project Limitations

The guest access portal and endpoint posture assessment were not fully implemented due to infrastructure and licensing constraints.

## Documentation

Additional documentation, network diagrams, configuration examples, and validation results will be added progressively.

## Contributors

This project was developed collaboratively as part of an academic program at TechnoLAB-ISTA.
