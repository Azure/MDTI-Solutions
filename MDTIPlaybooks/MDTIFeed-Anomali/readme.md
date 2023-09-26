# MDTI Feed To Anomali playbook

## Overview
The following Logic app key objective of this integration is to provide enrichment into Anomali from MDTI. This utilizes a few datasets from within MDTI’s broad range of data available. 
•	Use IoCs feeds provided in MDTI within Anomali to show if artefacts surfaced within Anomali have suspicious activity against them.
•	Use the reputation score to show if artefacts have been identified by Microsoft as having a poor or bad reputation
o	Value: As mentioned Threat Intelligence collection will always have gaps and there will be differences between providers of what has been seen. The value this provides is if there is an artifact that is surfaced within Anomali if this artifact is in one of the MDTI IoC feeds or has a poor reputation it provides the ability to add this enrichment to Anomali to show that Microsoft have identified malicious activity associated with the artifact.
•	IoCs vs Artifacts – Both of these refer to infrastructure like an IP address, host or a domain. A subtle difference to note is an artifact is something observed which is not necessarily associated with malicious activity, but an IoC is not known to be something associated with malicious activity. 


## Prerequisites
1.	Microsoft Sentinel Log analytics workspace (https://learn.microsoft.com/en-us/azure/sentinel/overview)
2.	Enabled Microsoft Defender Threat Intelligence Data Connector (https://learn.microsoft.com/en-us/azure/sentinel/connect-mdti-data-connector)
3.	Azure Logic Apps (https://learn.microsoft.com/en-us/azure/logic-apps/logic-apps-overview)
4.	Microsoft Defender Threat Intelligence API Access and Client App Registered (https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350)
5.	Anomali ThreatStream API Credentials (https://www.anomali.com/marketplace/sdks)


## Deployment


<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FMDTI-Solutions%2Fmaster%2FMDTIPlaybooks%2FMDTIFeed-Anomali%2Fazuredeploy.json"
target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FMDTI-Solutions%2Fmaster%2FMDTIPlaybooks%2FMDTIFeed-Anomali%2Fazuredeploy.json"
target="_blank">
    <img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"/>
</a>

## Post-Deployment Instructions
After deploying the playbook, you must authorize the connections leveraged.

1. Visit the playbook resource.
2. Under "Development Tools" (located on the left), click "API Connections".
3. Ensure each connection has been authorized.


## Steps to follow 
Integration Steps: Sending Defender Threat Intelligence to Anomali ThreatStream:
The process of sending Defender Threat Intelligence content to Anomali ThreatStream involves the following steps:
1.	On your Microsoft Sentinel environment, proceed to the Data connector Tab, look for the Microsoft Defender Threat Intelligence Connector and connect the source.
 
Once the data connector is connected, you can confirm the MDTI Data feeds are successfully being sent by pivoting to the threat intelligence blade. You can see it here: 
 
Figure: MDTI Indicators on Microsoft Sentinel Threat intelligence blade
2.	To proceed, you need to deploy the logic app which is available on the MDTI GitHub Link. You can find the Deploy to Azure Button on the page and clicking on it will prompt you to provide certain parameters.
 Once you have input the parameters, proceed to review and create. Once this has been done, run the logic App. 

3.	Once you run the logic app, it should proceed to query the Log analytics workspace and filter the MDTI feeds, for IP addresses and Host, it will run a reputation scoring against MDTI and depending on your Scoring parameter selection, it will provide a result of IOCs above a certain reputation score. The Result will then be sent as a POST command to Anomali ThreatStream. The successful running of the Logic app and the expected result can be seen as follows.:
 	 
4. The POST Command then sends the indicator to Anomali ThreatStream and dependent on the rules set on Anomali ThreatStream (auto approval / or Set approval) the indicator would be displayed allowing the user the ability to approve the indicator to be installed in ThreatStream.
 



