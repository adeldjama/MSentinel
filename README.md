# Microsoft Sentiel Unveiled

## Goal

You are members of the Contoso SOC (Security Operation Center) team. Contoso aims to modernize its SIEM/SOAR solutions, and the CISO has learned about Microsoft Sentinel. To assess its capabilities, the CISO has assigned you to lead the development of a Proof of Concept (PoC). The objective is to evaluate how Microsoft Sentinel efficiently collects logs and threat indicators, automatically detects incidents, and responds to them.

Are you ready to embrace this challenge?

## Environment 

- Entra ID tenant with 2 users:
  - cohacker: Allows you to connect to Azure to deploy resources
  - j.robert: Disabled user, will be used to run generate events
- subscription:
  - Resource Group "rg-cohack"
  - Windows VM "vm-win11"
  - Vnet "co-hackvnet"
>**Note**: Deploy all resources in the resource group "rg-cohack",in the same region of the existing resources.

![archi](./images/Picture1.jpg)

## Hacking Steps

1. Connect to Azure using "cohacker" account. Your coach will provide you the password account.

2. Deploy Microsoft Sentinel with a new log analytics workspace.

3. Connect the following Logs/Data Sources 
   - Azure Activity logs
   - Microsoft Entra ID sign-in logs
   - Windows Security Event for vm-win11
   - Micrsooft Defender Threat Intelligence 
   >**Note**: You will need first to install solutions from content hub

4. Create analytics rule to detect automatically the following incidents:
   - Creation of expensive computes in Azure,i.e, every Azure VM using more than 16vcpu.
   - Attempts to sign in to disabled accounts.
   - Security Event log cleared on Windows VM.
   - SigninLogs matching IP indicators of compromise

    >**Note**: Use NRT rules whenever is possible and the frequency of the scheduled rules should be reduced to 5 minutes.

5. Generate Events:
   - Connect to "vm-win11" using RDP, copy and run the provided script "" to clear all event logs.
   
   - On a browser private windows, sign in with "j.robert" account to:
    
      - Azure portal https://portal.azure.com
      
      - Outlook https://outlook.office.com
      - Microsoft 365 https://microsoft365.com
   
   - On Azure subcription, create a linux VM with the size.   

6. On Azure subscription, deploy the Playbook (Logic APP) "...." using the provided bicep template.

7. Respond to the incident "...." by isolating the "vm-win11" using the deployed Playbook.

8. Confirm that sentinel has received some indicators of compromise.
  

## Resources
