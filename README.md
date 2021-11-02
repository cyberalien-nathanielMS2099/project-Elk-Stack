 

Automated-ELK-Stack-
Deployment

09.04.2021

Nathaniel Shaw



Automated ELK Stack Deployment

The files in this Project were used to configure the network below.



![Screenshot 2021-11-02 120803 new revised again](https://user-images.githubusercontent.com/83778250/139929268-c5b9042f-e8ee-44a8-aa59-aeb046a5f2cd.png)





These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Or, select portions of the Playbook file to install certain pieces of it, such as Filebeat.yml file.
This document contains the following details:
Description of the Topologu
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the Topology.

The main purpose of this network is to expose a load-balancer and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be Available, in addition to restricting Access to the network.
Load balancing routes the incoming traffic to make sure there is always A wed-server is available . 
The advantages of a jump box is it allows easy administration  to systems and provides extra security.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the events log and system metrics.
Filebeat watches specific log directories and files, it collects data and then saves it.
Metricbeat gathers  data and stats and sends them to be stored in a logstash. The  data can be seen in apps like Kibana.
The configuration details of each machine may be found below. 

Name
Function
IP Address
Operating System


![Screenshot 2021-11-01 144614 jpj1](https://user-images.githubusercontent.com/83778250/139902266-608835d5-47ca-41f3-b020-e02c0612a682.png)


Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Jump-Box-Provisioner  machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: John's and personal IP address
My person ip address, 47.224.143.241

Machines within the network can only be accessed by  Jump-Box-Provisioner.
Only the Jump-Box-Provisioner can access the Elk-stack through SSH.  Its IP address?  10.1.0.4

A summary of the access policies in place can be found in the table below.

![Screenshot 2021-11-02 092654 jpg2](https://user-images.githubusercontent.com/83778250/139906098-8849ad5a-cc47-486f-9a18-7292ad5ccd77.png)

Elk Stack Configuration

![Screenshot 2021-11-02 104137 elk asnible config](https://user-images.githubusercontent.com/83778250/139917854-34bca72c-a0c5-4056-9d0f-bf77007bc1ce.png)
    
Ansible was used to automate configuration of the ELK machine. No configuration are performed manually, which is advantageous because...
There cannot be any configurations done manually.
The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

![Screenshot 2021-11-01 143956 docker ps ](https://user-images.githubusercontent.com/83778250/139906824-65526470-2581-4f01-acaa-4ea29a0d0578.png)


This ELK server is configured to monitor the following machines:
Web-1 10.0.0.5
Web-2 10.0.0.7

We have installed the following Beats on these machines: Filebeat and Metricbeat
These Beats allow us to collect the following information from each machine:
Filebeats collects system events like logins to see who is actively logging into the servers.
Metricbeats collects information like cpu usage and memory, this is useful when seeing if there are any threatening  programs or process taking system resources
Using the Playbook

In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below: 
Copy the elk_install.yml file to /etc/ansible/roles/elk_install.yml 
Update the /etc/ansible/hosts  file to include. The internal IP address
Run the playbook, and navigate to http://[your_elkserver_ip]:5601/app/kibana to check that the installation worked as expected.

![Screenshot 2021-11-01 104553 Kibana](https://user-images.githubusercontent.com/83778250/139901519-2cace90b-b6a5-4d97-babc-f1b838d25e8e.png)



Elkstack.yml copy this to /etc/ansible

Use the ansible.cfg file to confifgure Ansible to run the playbook on a specific machine.  To make sure the correct file is being installed, by going to that server and installing the correct .yml file.

You can navigate to http://[your_elkserver_ip]:5601/app/kibana in order to check that the ELK server is running.

![Screenshot 2021-11-01 111903 syslog](https://user-images.githubusercontent.com/83778250/139901584-08b9359f-91ef-4b1d-af14-ebe9381cd3bc.png)


(ansible-playbook elkstack.yml) is the commands that lets user to run the download ansible playbook,  and to update the files, sudo apt update.


