# MDTI-Base

## Overview
This playbook creates a shared Connection for all Microsoft Defender Threat Intelligence(MDTI) playbooks to leverage. This eases the configuration process for a user during deployment of the MDTI solution. In time, this base playbook may be extended to set more functionality. If you have trouble accessing your account or your credentials contact your account representative.

## Pre-deployment Instructions

1. Azure AD App Registration credentials(ClientId/ClientSecret/TenantId) with MDTI API Permissions are needed when configuring this playbook. Those can be found on your [Azure Client App](https://learn.microsoft.com/en-us/rest/api/azure/#register-your-client-application-with-azure-ad) page. If you have trouble accessing your account or your credentials contact your account representative or reach out to discussMDTI[@]microsoft.com.

## Deployment

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FAzure-Sentinel%2Fmaster%2FSolutions%2FMicrosoft%20Defender%20Threat%20Intelligence%2FPlaybooks%2FMDTI-Base%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>
<a href="https://portal.azure.us/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FAzure-Sentinel%2Fmaster%2FSolutions%2FMicrosoft%20Defender%20Threat%20Intelligence%2FPlaybooks%2FMDTI-Base%2Fazuredeploy.json" target="_blank">
    <img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"/>
</a>

## Post-Deployment Instructions
After deploying the playbook, you must authorize the connections leveraged.

1. Visit the playbook resource.
2. Under "Development Tools" (located on the left), click "API Connections".
3. Ensure each connection has been authorized.

**Note: If you've deployed the [MDTI-Base](https://raw.githubusercontent.com/Azure/Azure-Sentinel/master/Solutions/Microsoft Defender Threat Intelligence/Playbooks/MDTI-Base/azuredeploy.json) playbook, you will only need to authorize the Microsoft Sentinel connection.**