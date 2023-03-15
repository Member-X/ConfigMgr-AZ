---
description: This template creates new Azure VMs based on which configuration you choose. It configures a new AD domain controler, a new hierarchy/standalone bench with SQL Server, a remote site system server with Management Point and Distribution Point and clients. 
page_type: sample
products:
- azure
- azure-resource-manager
urlFragment: sccm-currentbranch
languages:
- json
---
# Install Configuration Manager Current Branch in Azure

![Azure Public Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/application-workloads/sccm/sccm-currentbranch/PublicLastTestDate.svg)
![Azure Public Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/application-workloads/sccm/sccm-currentbranch/PublicDeployment.svg)

![Azure US Gov Last Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/application-workloads/sccm/sccm-currentbranch/FairfaxLastTestDate.svg)
![Azure US Gov Last Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/application-workloads/sccm/sccm-currentbranch/FairfaxDeployment.svg)

![Best Practice Check](https://azurequickstartsservice.blob.core.windows.net/badges/application-workloads/sccm/sccm-currentbranch/BestPracticeResult.svg)
![Cred Scan Check](https://azurequickstartsservice.blob.core.windows.net/badges/application-workloads/sccm/sccm-currentbranch/CredScanResult.svg)

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FMember-X%2FConfigMgr-AZ%2Fmain%2Fazuredeploy.json)
[![Deploy To Azure US Gov](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.svg?sanitize=true)](https://portal.azure.us/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FMember-X%2FConfigMgr-AZ%2Fmain%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FMember-X%2FConfigMgr-AZ%2Fmain%2Fazuredeploy.json)

## Description
This template was modified from the MECM-currentbranch quickstart template to be used as the basis for the SDA environment.

This template deploys the latest Microsoft Endpoint Configuration Manager (ConfigMgr) general release with following configuration:

* A new AD domain controller
* A standalone primary site with SQL Server, ADK and ConfigMgr installed. ConfigMgr is the latest general release
* A remote site system server to host managemenent point and distribution point
* Windows 11 client(s)

## Updated
The following is a list of items updated from the original template.

* Added a storage account
* Updated the ADK version
* Increased the number of deployable clients
* Update the VM size of the primary server
  * Increased the size of the OS disk to 512GB
  
## Stilling working on
The following is a list of items that still need implementation

* Add a managed disk to Primary and site servers
  * Format and mount the disk
* Download all required applications to storage account

Each VM has its own public IP address and is added to a subnet protected with a Network Security Group, which only allows RDP port from Internet.

Each VM has a private network IP which is for ConfigMgr communication.

For more information, Visit [Create a Configuration Manager lab in Azure](https://docs.microsoft.com/configmgr/core/get-started/azure-template)

`Tags: Microsoft.Compute/virtualMachines, Microsoft.Compute/virtualMachines/extensions, DSC, Microsoft.Network/virtualNetworks, Microsoft.Network/networkInterfaces, Microsoft.Network/publicIpAddresses, Microsoft.Network/networkSecurityGroups`
