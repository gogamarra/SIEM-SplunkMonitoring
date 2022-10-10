# SIEM - Design A Splunk Monitoring Solution 

## Introduction

<ins>OBJECTIVE</ins>: Demonstrate my ability to design a powerful Splunk Enterprise Security monitoring solution to protect a customer from security attacks.

<ins>My Skills and Knowledge Applied</ins> 
- Researching and adding new apps
- Installing new apps
- Uploading files
- Splunk searching
- Using fields
- Custom reports
- Custom alerts

<ins>What is Splunk ES?</ins>

Splunk Enterprise Security (ES) is a Security Information and Event Management (SIEM) tool based on the Splunk data platform, a big data software solution that also provides many solutions outside cybersecurity. Splunk ES specializes in assisting with the key defensive concepts of continous monitoring, log collection, aggregation, parsing, normalization, searching and correlation. 

Splunk solutions can be enhanced by <ins>Splunk Apps</ins>, which users can add to their Splunk base product that have custom searches and features, with their own interface.  These differ from <ins>Splunk Addons</ins>, which are smaller components that provide additional functionality without their own interface.

## Attack Scenario
For the purposes of this project, I presume to be a new SOC Analyst for a company, Vandalay Industries. Vandalay uses Splunk ES as their SIEM.  

The following attacks and challenges ocurring:
- Web server outage due to a DDOS attack
- Upload/Download speed have been significantly impacted
- Brute force attacks against administrator accounts
- Management suspects the database servers might be vulnerable and are in need of an assessment.

## Outline of SIEM Deliverables
- Install monitoring features
- Report To Determine Impact on Download/Upload Speed and Ratio of upload/download
- Report: Identify Critical Vulnerabilities in the database server.
- Create Alert Notification
 
## Install Monitoring Features
- Install the Splunk App, **Network Toolkit**, on Splunk ES.

![InstallNetworkToolkit](./images/1-01-BrowseInstallNetworkToolkit.jpg)

- Restart Splunk to finalize install

![Restart](./images/1-02-RestartRequired.jpg)
![Restarting](./images/1-03-Restarting.jpg)

- Login as Admin to continue analysis

![AdminLogin](./images/1-04-SplunkAdminLogin.jpg)

- Configure where the index for searches will be stored.

![ConfigIndex](./images/1-05-ConfigLocationSearchIndex.jpg)

## 
- Ping Vandalay's web servers, **198.153.194.1** and **198.153.194.2**. Provide Results
- Run a speed test and provide results




![ Deployment Architecture](./images/network-diagram-elkstack.jpg)

## Playbooks, Configuration Files
Ansible files, known as **PLAYBOOKS**, 

- ![ANSIBLE Playbook Files](./files/playbook)

## Description of the Topology

The main purpose of this network is to host a load balanced and monitored instance of DVWA (D*mn 

(The public IP addresses will vary by deployment effort.)

|         Name         | Function  | Load Balancer | Private IP |    Public IP   |  Operating System  |
|----------------------|-----------|---------------|------------|----------------|--------------------|
| Jump-Box-Provisioner | Gateway   |      No       |  10.0.0.4  | 52.247.211.204 | Linux-Ubuntu 18.04 |
| DVWA-VM1             | Webserver |      Yes      |  10.0.0.5  | 52.191.166.158 | Linux-Ubuntu 18.04 |
| DVWA-VM2             | Webserver |      Yes      |  10.0.0.6  | 52.191.166.158 | Linux-Ubuntu 18.04 |
| ELK-Stack            | ELKserver |      No       |  10.0.0.7  | 52.183.78.79   | Linux-Ubuntu 18.04 |

### BEATS in Use
I have installed the following ELASTIC "Beats" lightweight shippers on the monitored machines to facilitate collection and transmission of data to the ELK Stack:
- **Filebeat**

These Beats allow collecting the following information from the web servers.:
- **Filebeat collects file system logs**

## SCREENSHOTS - Successful Build and Dashboard Confirmation
The following images display the actual results after running `DOCKER-ANSIBLE` PLAYBOOKS.  
- The ELK stack server was deployed.

### DASHBOARDS Working and Receiving Data

![filebeat System Overview](./images/dashboard-filebeat-system.jpg)
