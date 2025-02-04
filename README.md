# Azure-load-balancer

## Objective
Azure Load Balancer ensures efficient traffic distribution, high availability, and scalability by balancing network traffic across multiple VMs. It improves performance, enhances security, supports global resilience, and monitors backend health. It enables both public (internet-facing) and internal load balancing for optimized application delivery.

## What is Azure Load-Balancer
Azure Load Balancer is a cloud service that distributes network traffic across multiple VMs to ensure high availability, scalability, and reliability. It supports both public (internet-facing) and internal (private network) load balancing, with health monitoring and automatic failover for optimized performance.

## How it works
#### Traffic Reception – It receives incoming network traffic (public or internal).
#### Rule-Based Distribution – Uses load-balancing rules to distribute traffic across backend virtual machines (VMs) in a pool.
#### Health Probes – Continuously checks the health of backend VMs and removes unhealthy ones from traffic routing.
#### Automatic Failover – Redirects traffic to healthy VMs if one fails, ensuring high availability.
#### Scalability Support – Works with Azure Autoscale to dynamically add or remove VMs based on demand.

## Summary
Azure Load Balancer is a cloud-based service that distributes incoming network traffic across multiple virtual machines (VMs) to ensure high availability, reliability, and scalability of applications.

### Key Features:
#### Traffic Distribution: Spreads incoming traffic across backend VMs to optimize performance.
#### High Availability: Ensures application reliability by rerouting traffic if a VM becomes unavailable.
#### Public & Internal Load Balancing:
#### Public Load Balancer: Distributes traffic from the internet to VMs.
#### Internal Load Balancer: Balances traffic within an Azure Virtual Network.
#### Health Probes: Monitors the health of backend VMs and removes unhealthy instances from the rotation.
#### NAT (Network Address Translation) Rules: Allows direct access to specific VM instances for maintenance or management.
#### Cross-region Load Balancing: Routes traffic across multiple Azure regions for global redundancy.

## Step-1

Creating 2 VMs

Creating first VM

##### *Keep in Availability set*

![image alt](Capture1.PNG)


Create an availability set with any name of your choice

![image alt](Capture2.PNG)


Select the ports

![image alt](Capture3.PNG)

Proceed with 'Review and Create'

#### *Create another VM machine with same configuration and ensure both VMs are deployed in same availability set and resource group*


## Step-2

Connect your first VM

![image alt](Capture4.PNG)


Download the RDP file

![image alt](Capture6.PNG)

![image alt](Capture7.PNG)

![image alt](Capture8.PNG)

#### *Do similar for the 2nd VM*

Click on 'Add Roles and Features'

![image alt](Capture9.PNG)

![image alt](Capture10.PNG)

![image alt](Capture11.PNG)

Check mark on 'Web Server (IIS) features and proceed further

![image alt](Capture11.PNG)

Click on Add Features

![image alt](Capture12.PNG)

Tick mark the above check box and than install

![image alt](Capture13.PNG)


## Step-3

Open file manager,go to C Drive

Click on inetpub folder and go into wwwroot folder

![image alt](Capture14.PNG)

![image alt](Capture15.PNG)

Open iistart file with Notepad

![image alt](Capture16.PNG)

### Make some changes to identify where we are redirected

![image alt](Capture17.PNG)

#### *Follow the same process in 2nd VM*


## Step-4

*Now, lets configure the the LOAD BALANCER*

![image alt](Capture18.PNG)

Configure bacis information

![image alt](Capture19.PNG)

![image alt](Capture20.PNG)

Add IP configuration to Backend pool

![image alt](Capture21.PNG)

![image alt](Capture22.PNG)

Configure Inbound Rules

![image alt](Capture23.PNG)

![image alt](Capture24.PNG)

Now,click on 'Review and Create'.

Click on 'Go to Resources'.

![image alt](Capture26.PNG)

Copy the IP Address and paste into the browser.

![image alt](Capture27.PNG)

#### *The Traffic is currently directed to 2nd VM

![image alt](Capture28.PNG)

Shut down the 2nd VM to verify the lody balancer redirects us to 1st VM

![image alt](Capture29.PNG)

### The load balancer successfully redirects us to 1st VM

![image alt](Capture30.PNG)




