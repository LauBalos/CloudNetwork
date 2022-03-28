## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

!Images/Network_Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML files may be used to install only certain pieces of it, such as Filebeat.

  - ansible-playbook.yml
  - install-ELK.yml
  - ansible-config.cfg
  - ansible-hosts.txt
  - filebeat-playbook.yml
  - filebeat-config.yml
  - metricbeat-playbook.yml
  - metricbeat-config.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly accessible, in addition to restricting traffic to the network.
- What aspect of security do load balancers protect? What is the advantage of a jump box?
	- Load balancers protect the availability of a network resource by evenly distributing network traffic.
	- The advantage of a jump box is that you can securely connect to other machines without exposing them to the public.You can also manage multiple machines from one main machine.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- What does Filebeat watch for?
	- Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- What does Metricbeat record?
	-  Metricbeat records metrics and statistics and ships them to the output that you specify, such as Elasticsearch or Logstash.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
|JumpBoxVM | Gateway  | 10.0.0.4   | Linux            |
| Web-1    |Web Server| 10.0.0.5   | Linux            |
| Web-2    |Web Server| 10.0.0.6   | Linux            |
| ELK-VM   |ELK Server| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 40.78.45.132

Machines within the network can only be accessed by Private IP Addresses.
- Which machine did you allow to access your ELK VM? What was its IP address?
	- JumpBox VM: 10.0.0.4, SSH Port: 22

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |     No              |Home IP Port: 22      |
|  Web-1   |     No              |10.0.0.4 Port: 22     |
|  Web-2   |     No              |10.0.0.4 Port: 22     |
|  ELK-VM  |     No              |10.0.0.4 Port: 22     |  

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible?
	- The main advantages of automating configuration with Ansible is that there's less chance for mistakes and time efficient.

The playbook implements the following tasks:
- In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
	- Install Docker.io
	- Download image
	- Increase virtual memory
	- Set restart policy to `always`

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Images/docker-ps.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Logs
- System data

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
