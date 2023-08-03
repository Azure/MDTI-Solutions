# MDTI Host Component Information Retrieval Jupyter Notebook

MDTI Host Component Information Retrieval is a Python script that utilizes the Microsoft Graph Security API to retrieve host component information for a given domain.

## Prerequisites
Before running the script, ensure you have the following:

- Python 3.6+ installed on your system.
- The required Python packages installed: azure-identity, requests, json, and os.

## Setup
1. Clone the repository or download the script file to your local machine.
2. Install the required Python packages by running the following command in your terminal or command prompt:
```python
Copy code
pip install azure-identity requests json os
```

## Configuration
Open the script file and provide the necessary configuration details in the designated placeholders:

```Python
Copy code
credential = ClientSecretCredential(
    tenant_id='Place your Tenant ID Here',  # Your Azure AD tenant ID
    client_id='Place your Client ID Here',  # Your Application Client ID
    client_secret='Place your client secret Here'  # Your application client Secret which should never be stored in plain text
)

hostname = "example.com"  # Replace with your domain
```
Replace the placeholder values with your Azure AD tenant ID, application client ID, and Client Secret. The Client ID and Client Secret would be obtained when you register an App with in the Azure Active Directory.

As with the previous script, ensure that your client secret is properly secured and not stored in plain text.

## Usage
Open Jupyter Notebook on your local machine.
Open the MDTI Host Component Information Retrieval script file.
Run the script cell by cell, following the instructions and comments provided.
The script will retrieve host component information for the specified domain and print the JSON response from the API.

## Results
The script prints a JSON response from the API containing host component information for the specified domain. This information includes properties of the host and associated entities.

## Disclaimer
This script is provided as-is and without warranty. Use it at your own risk. The script interacts with the Microsoft Graph Security API and utilizes your Azure AD credentials to retrieve host component information. Make sure you have the necessary permissions and follow Microsoft's security best practices when handling authentication credentials.

Additional Information
For information on Azure Libraries (SDK) for Python: https://learn.microsoft.com/en-us/azure/developer/python/sdk/azure-sdk-overview

What's New: APIs in Microsoft Graph: https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350

## Author:
Dennis Mercer\
CXE MDTI\
Microsoft Security
