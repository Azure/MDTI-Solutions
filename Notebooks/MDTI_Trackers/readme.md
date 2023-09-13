# Microsoft Graph API Cookies Retrieval Jupyter Notebook


This notebook provides a Python script that leverages the Microsoft Graph Security API to fetch trackers associated with a given domain.

## Prerequisites
Before executing the script, ensure the following:

- Python 3.6+ is installed on your system.
- The necessary Python packages are installed: azure-identity, requests, and os. (Note: You don't need to install the json module as it's part of Python's standard library.)


## Setup
1. Clone the repository or download the notebook file to your local machine.
2. Install the required Python packages by executing the following command in your terminal or command prompt:


```Python 
pip install azure-identity requests os
```

## Configuration
Open the notebook and adjust the necessary configuration details in the appropriate sections:

```Python
credential = ClientSecretCredential(
    tenant_id='Your Tenant ID',  # Your Azure AD tenant ID
    client_id='Your Client ID',  # Your Application Client ID
    client_secret='Your client secret'  # Ensure this secret is fetched securely
)
```

Replace the placeholders with your Azure AD tenant ID, application client ID, and client secret. When registering an App within Azure Active Directory, you will obtain the Client ID and Client Secret.

Ensure your client secret is fetched securely and isn't stored in plain text.

## Usage
1. Launch Jupyter Notebook on your system.
2. Open the "MDTI_Trackers.ipynb" notebook.
3. Execute the cells sequentially, adhering to the guidelines and comments provided.
4. The script will fetch trackers related to the specified domain and display the JSON response from the API.

## Results
The notebook will output a JSON response from the API that lists trackers tied to the input domain.

## Disclaimer
This notebook is supplied "as-is" and without any warranties. Utilize it responsibly. It communicates with the Microsoft Graph Security API and employs your Azure AD credentials to fetch domain-specific cookies. Always adhere to Microsoft's security recommendations when managing authentication credentials.

## Additional Information
## Additional Information
Azure Libraries for Python: https://learn.microsoft.com/en-us/azure/developer/python/sdk/azure-sdk-overview  \
Microsoft Graph SDK Overview: https://learn.microsoft.com/en-us/graph/sdks/sdks-overview  \
Microsoft Learn Threat Inteligence Graph API: https://learn.microsoft.com/en-us/graph/api/resources/security-threatintelligence-overview?view=graph-rest-1.0 \
What's New: APIs in Microsoft Graph: https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350

Author:\
Dennis Mercer\
CXE MDTI\
Microsoft Security\