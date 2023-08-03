# MDTI Heatmap Jupyter Notebook

MDTI Heatmap Jupyter Notebook is a Python script that utilizes the Microsoft Graph Security API to retrieve and analyze passive DNS information for a given domain. This notebook generates a heatmap visualization to display the first and last seen dates of various DNS record types (NS, SOA, AAAA) associated with the specified domain.

## Prerequisites

Before running the notebook, ensure you have the following:

- Python 3.x installed on your system.
- The required Python packages installed: `azure-identity`, `msgraph-sdk-security`, `pandas`, `matplotlib`, `boken` and `seaborn`.

## Setup

1. Clone the repository or download the notebook file to your local machine.
2. Install the required Python packages by running the following command in your terminal or command prompt:

```python
pip install azure-identity msgraph-sdk-security pandas matplotlib boken seaborn
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
Open Jupyter Notebook on your local machine.
Open the MDTI Heatmap Jupyter Notebook file.
Run the notebook cell by cell, following the instructions and comments provided.
When prompted, enter the domain you want to analyze and proceed to the next cell.
The notebook will retrieve passive DNS information for the specified domain and generate a heatmap visualization.
The heatmap will be displayed, showing the first seen and last seen dates of DNS records.
## Results
The notebook generates a heatmap that represents the occurrence count of DNS records over time. Each cell in the heatmap corresponds to a specific combination of "First Seen" and "Last Seen" dates for a particular DNS record type. The color intensity in each cell indicates the count of occurrences.

The generated heatmap will be displayed within the notebook.


## Disclaimer
This notebook is provided as-is and without warranty. Use it at your own risk. The notebook interacts with the Microsoft Graph Security API and utilizes your Azure AD credentials to retrieve passive DNS information. Make sure you have the necessary permissions and follow Microsoft's security best practices when handling authentication credentials.

## Additional Information
For information on Azure Libraries (SDK) for Python: https://learn.microsoft.com/en-us/azure/developer/python/sdk/azure-sdk-overview

What's New: APIs in Microsoft Graph: https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350


## Author:
Dennis Mercer\
CXE MDTI\
Microsoft Security