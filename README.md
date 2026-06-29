# Lab: Windows Server Roles & Infrastructure

## Objective
To configure and manage essential network infrastructure services on Windows Server 2022. This lab demonstrates the deployment of Domain Name System (DNS) and Dynamic Host Configuration Protocol (DHCP) to support a domain-joined client environment.

## Technical Environment
- **Server:** Windows Server 2022
- **Client:** Windows 11 Enterprise
- **Services:** Active Directory Domain Services (AD DS), DHCP, DNS
- **Tooling:** Server Manager, DNS Manager, DHCP Console

## Lab Workflow: Step-by-Step

### 1. Server Role Installation
* Used **Server Manager** to add roles and features.
* Installed **AD DS** to promote the server to a Domain Controller.
* Added **DNS** and **DHCP** roles to enable automated network configuration and name resolution for client machines.

### 2. DNS Infrastructure Configuration
* Configured **Forward Lookup Zones** to map hostnames to IP addresses.
* Created **Reverse Lookup Zones** to ensure the server can resolve IP addresses back to names, a critical step for network troubleshooting and security.
* Verified that the Windows 11 client was correctly registering its A-record in DNS upon joining the domain.

### 3. DHCP Scope Management
* Defined a **DHCP Scope** (IP address pool) to automate the distribution of IP addresses, subnet masks, and default gateways.
* Configured **DHCP Options**, specifically setting the DNS server address to point client machines to the Domain Controller.
* Verified that the Windows 11 client successfully received an IP address lease from the server via `ipconfig /renew`.

### 4. Integration & Connectivity Validation
* Tested cross-machine communication using `ping` (by hostname, not just IP) to confirm that DNS resolution was working correctly.
* Validated server-to-client connectivity by checking active DHCP leases in the DHCP management console.


## Key Learnings
* **Service Interdependency:** Gained a clear understanding of how DNS and DHCP work together; without proper DNS configuration, Active Directory domain joins will fail.
* **Troubleshooting:** Learned to identify network misconfigurations by analyzing IP lease status and DNS resolution errors.
* **Scalability:** Understood how to pre-configure network services to allow for the seamless addition of multiple client workstations into the domain.
