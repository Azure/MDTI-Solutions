# Deploy-MDTI-Workbook
author: Yaniv Shasha


By clicking deploy above you will deploy an Azure Function App with the functions needed to run this project. This version will deploy the functions for MDTI API endpoints.

### Prerequisites

Prior to beginning the installation process, it's crucial to confirm that you have met the following prerequisites:
• You enabled the MDTI API license on your tenant
• You have created an application with a corresponding APP id and Secret.
https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350 
• You possess the necessary permissions to deploy resources in the designated resource group.

The above solution will deploy these resources into the target resource group:
•	Azure function – will ack as a middle layer between the workbook and the API
•	Key vault – will store the API key and secret.
•	Workbook – act as the presentation layer.


### Installing

1.	To install the solution, navigate to this GitHub repository and press deploy to Azure. 
In the custom deployment screen add the client ID and app secret you created.
This information will be saved in an Azure key vault.


<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FMDTI-Solutions%2Ftree%2Fmaster%2FWorkbooks%2FMDTI-Workbook-Solution%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

### Workbook configuration

1.	Post installation, navigate to the target Resource group you deploy the solution and copy the azure function name.

2.	Open the workbook and in the “Deployed-AzureFunction” select the name you copy in step 1.

To set up the MDTI Sentinel Incident View Tab, choose the subscription and workspace for the Sentinel instance. Keep in mind that although the remaining sections of this workbook do not depend on Sentinel data, you must still select a workspace in this tab.