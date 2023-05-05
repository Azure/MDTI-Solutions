# Typosquat playbook 

## Overview
The Typosquat playbook provides a systematic approach for detecting and taking down potentially harmful typo squat domains. This playbook leverages an open source tool called Open Squat to identify new domains that are created with slight variations of legitimate domain names in relation to a keyword selected by the user.

After identifying these domains, the Typosquat playbook automatically runs them against the Microsoft Defender Threat Intelligence Reputation endpoint. This platform provides real-time scoring for domains in terms of reputation (malicious or suspicious). The results are then provided in an email , showcasing the domains against the reputational endpoint. By leveraging the reputation scoring provided by the endpoint, the Security team can prioritize their domain takedown activities based on the level of risk posed by each domain.

## Prerequisites
1. Access to Open squat API (https://rapidapi.com/atenreiro/api/opensquat1/), you will require access to the RAPID API Key , RAPID APRI -Host , you can sign up for a monthly quota trial in the link provided
2. Access to MDTI API , access to the logic app would be best through an Client App registration, details of that and how to do that can be found here : , you can also sign up for a trial for the API  and set up the client APP here :(https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350)

## Deployment


<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FKwachSean%2FMDTIplaybooks%2Fmain%2FTyposquat(openSquat)
%2Fazuredeploy.json"
target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FKwachSean%2FMDTIplaybooks%2Fmain%2FTyposquat(openSquat)
%2Fazuredeploy.json"
target="_blank">
    <img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"/>
</a>

## Post-Deployment Instructions
After deploying the playbook, you must authorize the connections leveraged.

1. Visit the playbook resource.
2. Under "Development Tools" (located on the left), click "API Connections".
3. Ensure each connection has been authorized.


## Steps to follow 
1. Before deploying the playbook you will need to add the credentials for both Open squat API https://rapidapi.com/atenreiro/api/opensquat1/)and also the MDTI API credentials (https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350)
![image](https://user-images.githubusercontent.com/67633117/236252023-2237dcb5-5fa7-42ce-bf8a-55e694934784.png)


2. Click on the Deploy button and it will prompt you for the details

![image](https://user-images.githubusercontent.com/67633117/236240536-183b70e9-3909-4d49-91fa-a17f48d21c4b.png)

3. The playbook should be ready to Run and should send results to your selected email on basis 

![image](https://user-images.githubusercontent.com/67633117/236242629-28d2cebc-2562-4d9a-987c-3431099aa6af.png)



