# Azure-Cloud-SOC-Lab-Incident-Response

Builds off repository Azure-Cloud-SOC-Lab showcasing the Incident Response process Microsoft Sentinel  
![final map](https://github.com/gervguerrero/Azure-Cloud-SOC-Lab-Incident-Response/assets/140366635/c1ef655b-4ebf-4b86-b7d7-3060246645a6)

This page builds off of my [Azure-Cloud-SOC-Lab](https://github.com/gervguerrero/Azure-Cloud-SOC-Lab/tree/main). 

In Microsoft Azure, I built a public facing Honey Net to attract real world cyber attackers to monitor their TTPs. Here I showcase basic methods to view the incidents caused by these threat actors in Microsoft Azure and implement controls to emulate the incident response process from NIST 800-61 used by Security Operation Center (SOC) Teams. 

This Incident Response process is a very basic demonstration of how a malicious cyber actor can brute force into an unprotected system that is left open, and how it is observed in Microsoft Sentinel and the Log Analytics Workspace in a Microsoft Azure Cloud environment. 

<br/> 
<br/> 

# Vulnerable Network 
![uncsecure net map](https://github.com/gervguerrero/Azure-Cloud-SOC-Lab-Incident-Response/assets/140366635/97549972-f13c-445c-9719-38f30ecf44ae)

The Azure cloud environment was left wide open without any real protection from cyber threat actors on the internet. The map shows  5 layers of defenses that were left open for threat actors to directly connect to the virtual machines and brute force/login into.

1. Azure Firewall
2. Network Service Group (NSG) covering the entire virtual network
3. Network Service Group specific to each virtual machine
4. Operating System Specific Firewalls to each virtual machine,
5. and Firewall rules specific to the Blob Storage/Key Vault
6. Private Endpoint Protection for Blob Storage/Key Vault
   
<br/> 

# Start of the Incident Response Process 
![IR](https://github.com/gervguerrero/Azure-Cloud-SOC-Lab-Incident-Response/assets/140366635/fdbc811a-f5bd-469b-9091-5dff69e0bf47)

For this specific incident, NIST 800-61's Incident Response model was used. 

## Step 1: Preparation

A majority of this step was covered in our Honeynet and SOC building period. The important part of this step in this environment was ingesting logs from our assets and importing them into our Log Analytics Workspace to be used by Microsoft Sentinel.
Click here to see the process used for this project: (PLACEHOLDER)

The main goals in this step is to gather as much information as possible before jumping into the analysis step. The ingestion of logs in any incident response or network assessment is crucial to a successful analysis of a network. Endpoint logs give your security team the telemetry and visibility that often isn't seen if only network traffic is collected, or if the security team isn't able to deploy Endpoint Detection (EDR) tools. 

In a real life Incident Response, here are some other items to consider for the preparation phase:

- Communication Plans with Key Stakeholders, Network Owners, and Security Response Team
- Acquisition of Network Map and Network Scope, IP/Inventory/Asset List
- Scoping Document/Questionnaire covering Pattern of Life/Baseline for the Network (When/How are backups performed? How many Administrators does the network Have?)
- Authorized Software List, Users List
- Identification of Crticial Assets to the Network Owners
- Developing Security Sensor Strategy, what kind of Security Tools to use, how the data wil be collected for analysis by the Security Team 
- Threat Intelligence published to the Information Security Community (APTs, widely known CVEs, information that might be relevant to the network if it is specific like Hospitals, Bank, Schools, etc.)
- All Data surrounding or related to the Initial Event found that led to an escalated Incident. 
  



