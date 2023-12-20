# Microsoft Sentiel

## Goal

In this challenge, we invite you to step into the role of a hacker. Your first objective will be to access to a corporate network by infiltrating a user's machine. Once you have gained access to this machine, your ultimate goal will be to gain control over the company's domain.

Are you ready? 

## Environment 

- Entra ID tenant with 2 users:
  - cohacker: allows you to connect to Azure to deploy resources
  - j.robert: disabled user, will be used to run tests
- subscription:
  - Resource Group "rg-co-hack"
  - Windows VM "vm-windows"
  - Vnet "co-hack-vnet"
- Deploy all resources in the resource group "rg-co-hack",in the same region of the existing resources.

![archi](./images/archi.png)

## Hacking Steps

1. Connect to Azure using "trainee" account. Your coach will provide you the password account.

2. Deploy Microsoft Sentinel.

3. Connect the following Logs/Data Sources 
   - Azure Activity
   - Microsoft Entra ID
   - Windows Security Event for vm-win11
   - Micrsooft Defender Threat Intelligence 
5.   

6. Discover the IP address of the domain controller Dc-vm.  

7. Use a tool from the toolbox, (a) to find the login and password hash of the Domain Admin then (b) to connect to the domain controller using RDP.


  >**Note**: Each tool should be used one time  

## Toolbox
1. Mimikatz
    - https://github.com/ParrotSec/mimikatz
    - https://techyrick.com/mimikatz-tutorial/
    - https://edermi.github.io/post/2018/native_rdp_pass_the_hash/

2. Nmap 
    - https://nmap.org/download.html

3. Hydra 
    - https://github.com/maaaaz/thc-hydra-windows
    - https://securitytutorials.co.uk/brute-forcing-passwords-with-thc-hydra/
    - https://github.com/adeldjama/Hacking-Game/blob/37fa336979bbdabf53f53ce07d7832900f47b2c4/resources/username.txt
    - https://github.com/adeldjama/Hacking-Game/blob/37fa336979bbdabf53f53ce07d7832900f47b2c4/resources/password.txt

