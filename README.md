## Project 1 

The files in this repository were used to configure the network diagram depicted titled (Network Diagram)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. 

  elkstack.yaml.txt

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the Damn Vulnerable Web Application.

Load balancing ensures that the application will have a split load instead of having all traffic thrown at web-vm-1 and when full go to web-vm-2 in addition to restricting access to the network by having to go through both jumpbox, and the docker container.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and metrics of system and and services.

The configuration details of each machine may be found below.

| Name             | Function                | IP Address         | Operating System |
|------------------|-------------------------|--------------------|------------------|
|                  |                         |                    |                  |
| Jump Box         | Gateway                 | 104.215.125.110    | Linux            |
| Docker Container | Security                | Gallant_Lichterman | Linux            |
| Load balancer    | Load splitting          | 70.37.70.85        | HTML             |
| Web-VM-1         | Machine being monitored | 10.2.0.8           | Linux            |
| Web-VM-2         | Machine being monitored | 10.2.0.9           | Linux            |
| Elk Server       | Filebeat and Metricbeat | 52.151.60.13       | Linux            |

The machines on the internal network are not exposed to the public Internet. 

Only jumpbox and the elk server have public IPs and can be accessed through the internet.
Web-VM-1 and Web-VM-2 are only accessible through both Jumpbox and a docker container for addes security.

| Name       | Publicly Accessible | Allowed IP Addresses |
|------------|---------------------|----------------------|
| Jump Box   | Yes                 | 10.2.0.8 + 10.2.0.9  |
| Elk Server | Yes                 | 10.2.0.8. + 10.2.0.9 |

The main advantage of automating anything your deployment time as well as mistakes drops dramtically. When you do not have to configure every machine, setting, network security group, etc you will be less likely to make mistakes.

Configuring elk VM with docker
  installed docker.io
  installed python3
  increased virtual memory
  download and launch the docker elk container, on ports 5601, 9200, 5044
  
  ### Target Machines & Beats
This ELK server is configured to monitor the following machines: web-vm-1 and web-vm-2
