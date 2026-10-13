# HomeLab
Documentation for HomeLab Environment

Included in this repo are the following: 
  - This readme file, with written documentation regarding my HomeLab environment. Some data is removed for anonymity.
  - Diagram explaining the physical and logical topology of the HomeLab environment
  - Any Ansible, Python, or Jinja2 scripting that is used in the HomeLab environment.

General documentation: 

DNS:
- Technitium DNS Server(s): 
    - All running DNS over TLS (Port tcp_853)
    - Homelab domain: *."example"."com"

    - Goals: 
        - Auto-create DNS entries when new VM stood up

    - NPD-VM has its own DNS Server
        - Can be used to test new features
    - PRD-VM (and possibly Wired and Wireless can point to these?)
        - Running in Cluster Mode
        - Updates to 01 propegate to 02 automatically

Windows AD: 
    - Goals:
        - Get it setup
        - Deploy a Windows 10 22H2 client and get it to join a domain. 
        - Test AD functions on FortiGate 


Validation/Test Hosts:
    - NPD-VM: 
        - (Ubuntu 26.04)
        - (windows 10 22H2) *Not yet active*
    - PRD-VM
        - (Ubuntu 26.04) *Not yet active*
        - (windows 10 22H2) *Not yet active*

Monitoring: 
    - Goals: 
        - Get monitoring established for Linux hosts. 
        - Get monitoring established for Windows hosts.
        - Get monitoring established for FortiNet devices.

    - NPD-VM
        - (Zabbix Server)
            - Still need to configure post setup, need more hosts to test against

Automation: 
    - Goals: 
        - Automate VM deployment in Proxmox
            - Add DNS entry to Technitium DNS
            - Add monitoring for Zabbix

    - AWX (Prev. Ansible Tower / AAP)
        - Difficulty setting up Kubernetes as full K8s. 
            - Continue troubleshooting and working this. 
        - Deploy microK8s/k3s as simple solution? 
            - Need to validate what Kubernetes platforms AWX/AAP is able to run on. 
    
    - Possibly look into other Automation Platforms to use? 

Repositories & Documentation: 
    - Self hosting GitLab/Gitea/Git Repo
        - Investigating several options. Unsure as to what will work best given environment.

Other Platforms & Services: 
    - Docker:
        - Goals: 
            - Automate container deployment
            - Automate container updates

        - Dev/Prod hosts
        - Portainer Front End
        - Bitwarden for PW management
        - Scrupting/Repo secrets manager of sorts? 

    - IPAM:
        - Need to investigate self hosted IPAM solutions.
            - Goal: Automate IPAM updates and tracking

    - TailScale:
        - Research and possibly POC/Test Deploy. 
