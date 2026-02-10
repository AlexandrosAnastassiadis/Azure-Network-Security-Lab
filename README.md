# Azure Network Security Project

## Overview
This project demonstrates how to secure an Azure virtual network using
Network Security Groups (NSGs) and Azure Firewall.

The goal was to build a defense-in-depth architecture, route traffic through
a firewall, and verify the behavior using real traffic tests and logs.

## Technologies Used
- Microsoft Azure
- Azure Virtual Network (VNet)
- Network Security Groups (NSG)
- Azure Firewall (Basic SKU)
- User Defined Routes (UDR)
- Windows Server 2022
- Azure Log Analytics

## Architecture
- Virtual Network: vnet-sec (10.0.0.0/16)
- Subnets:
  - WebSubnet (10.0.1.0/24)
  - AzureFirewallSubnet (10.0.10.0/24)
  - AzureFirewallManagementSubnet (10.0.20.0/26)

## Security Configuration
 NSG applied at subnet level:
  - Allow RDP (TCP 3389) from my IP
  - Deny HTTP (TCP 80) from any source
 Azure Firewall policy:
  - Allow HTTPS outbound traffic only
 UDR forces all outbound traffic through Azure Firewall

## Validation
- HTTP traffic blocked successfully
- HTTPS traffic allowed
- Traffic behavior verified using PowerShell and Log Analytics

## Outcome
This project shows practical experience in Azure networking, traffic routing,
and security controls using both NSGs and Azure Firewall.
