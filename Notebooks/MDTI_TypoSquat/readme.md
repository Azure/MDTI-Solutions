# OpenSquat API Script

This repository contains a modified version of the OpenSquat API script. The script allows you to fetch and check the reputation of domains using the OpenSquat API and Microsoft Graph Security API in a Jupyter Notebook environment.

## Prerequisites
Before using the script, make sure you have the following prerequisites:

* OpenSquat API Key: Obtain an API key from OpenSquat and replace 'Enter your OpenSquart API Key' with your actual API key in the script.
* Azure Tenant ID, App Client ID, and Client Secret: You need these credentials to authenticate and access the Microsoft Graph Security API. Replace 'Enter your Azure Tenant ID', 'Enter your App Client ID', and 'Enter your Client Secret' with your actual credentials in the script.

## Setup

1. Clone the repository or download the notebook file to your local machine.
2. Install the required Python packages by running the following command in your terminal or command prompt:

```python
pip install azure-identity msgraph-sdk-security pandas matplotlib  
```
## Configuration

Open the notebook file and provide the necessary configuration details in the designated placeholders:

```Python
credential = ClientSecretCredential(
    tenant_id='Place your Tenant ID Here',  # Your Azure AD tenant ID
    client_id='Place your Client ID Here',  # Your Application Client ID
    client_secret='Place your client secret Here'  # Your application client Secret which should never be stored in plain text
)

scopes = ['https://graph.microsoft.com/.default']  # Scopes or permissions required for API access
```

Replace the placeholder values with your Azure AD tenant ID, application client ID, and Client Secret.  The Client ID and Client Secret would be obtain when you register an App with in the Azure Active Directory.  

It's important to ensure that your client secret is properly secured and not stored in plain text.  You can place the Client Secret in the Notebook cell when running the Notebook and remove after it's use.  You can also use Azure Key Vault (https://learn.microsoft.com/en-us/azure/key-vault/general/basic-concepts)

You can also use a file outside of the Notebook to hold the Client Secret and call it in this manner:
```Python
# Read the client secret from a text file
with open("client_secret.txt", "r") as f:
    client_secret = f.read().strip()

# Set the client secret as an environment variable
os.environ["CLIENT_SECRET"] = client_secret
```


## Usage
1. Download and open the Jupyter Notebook file (opensquat_api_script.ipynb) in Jupyter Notebook or JupyterLab. 

2. In the Notebook, locate the following variables at the top of the code cells:

*  X-RapidAPI-Key: Replace 'Enter your OpenSquart API Key' with your actual OpenSquat API key.
* tenant_id: Replace 'Enter your Azure Tenant ID' with your Azure Tenant ID.
* client_id: Replace 'Enter your App Client ID' with your App Client ID.
* client_secret: Replace 'Enter your Client Secret' with your Client Secret.
3. Run each code cell in the Notebook sequentially by selecting the cell and clicking the "Run" button or using the keyboard shortcut.

4. When prompted, enter the keyword you want to search for.

5. The script will fetch the domains related to the keyword using the OpenSquat API. It will then check the reputation of each domain using the Microsoft Graph Security API.

6. The reputation and score of each domain will be displayed in the output of the Notebook.

## Disclaimer
This notebook is provided as-is and without warranty. Use it at your own risk. The notebook interacts with the Microsoft Graph Security API and utilizes your Azure AD credentials to retrieve passive DNS information. Make sure you have the necessary permissions and follow Microsoft's security best practices when handling authentication credentials.

## Additional Information
For information on Azure Libraries (SDK) for Python: https://learn.microsoft.com/en-us/azure/developer/python/sdk/azure-sdk-overview

What's New: APIs in Microsoft Graph: https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350

## Author
Dennis Mercer\
Sr Program Manager\
Microsoft CxE\
Microsoft Defender Threat Intelligence