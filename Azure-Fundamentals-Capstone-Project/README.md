#  Azure Fundamentals Capstone Project.


# Project Overview

This project ties everything on Azure Fundamentals. By completing this task, I will design, deploy, and secure a realistic environment, preparing me for more advanced modules like Terraform automation and CI/CD.

Learning Objectives:

- Create multiple VNets and configure private communication between them.

- Deploy three Linux VMs into separate VNets.

- Use Azure Bastion for secure Private SSH access no public IPs.

- Configure NSGs to control inbound and outbound network traffic.

- Create an Azure Key Vault to securely store and manage secrets.

- Deploy Azure Blob storage and secure it with a private endpoint.

- Manually build a secure mini Azure infrastructure like a DevOps engineer.



## Project Architecture.

![The Image here shows the architectural diagram of Azure fundamental](image/azure-fundamental-architecture.png)

****************************************

This Capstone project marks the completion of the Azure fundamentals.

# Create Resource Group
# Step 1
- Login into the Azure platform and search **resource-group**

- Name of the Resource-group and create

- Below show the image process of creating Resource group in the Azure platform.

![The Image shows the creation resource group](image/resource-group1.png)

![The Image shows the creation resource group](image/resource-group2.png)

![The Image shows the creation resource group](image/resource-group3.png)

![The Image shows the creation resource group](image/resource-group4.png)


# Task
-  I have to deploy a secure, multi-VNet Azure environment entirely through the Azure Portal, step by step.

Goal: Build a production-style secure environment using Azure Portal only.


Module: Azure Fundamentals.

# Step2     Create the First Virtual Network.

  - Search for **Virtual Network** Click  **Create**

  - Resource Group: nimbus-labs

  - Name: nimbus-hub-vnet

  - Region: (e.g., East US)

  - Go to the **IP Addresses** tab:

  - Address space: 10.0.0.0/16

  - Subnet Name: nimbus-hub-subnet

  - Subnet Address Range: 10.0.1.0/24

  - Leave other options at default  Click **Review + Create** -----> **Create**

  Below shows the Image procedure's on the creation Virtual Network[VNet]and the Subnet.

  ![The Image shows the creation of Vnet and Subnet](image/hub-virtual-network-subnet1.png)

  ![The Image shows the creation of Vnet and Subnet](image/hub-virtual-network-subnet2.png)

  ![The Image shows the creation of Vnet and Subnet](image/hub-virtual-network-subnet3.png)

  ![The Image shows the creation of Vnet and Subnet](image/hub-virtual-network-subnet4.png)


# Step 3 Create the Second Virtual Network
    I have to repeat the same process but small adjustment on the IPs

   - Name: nimbus-spoke-vnet

   - Address Space: 10.1.0.0/16

   - Subnet Name: nimbus-spoke-subnet

   - Subnet Range: 10.1.1.0/24


I was trying to alter the subnet of the **Nimbus-Spoke-Subnet**

![The Image shows the creation of Spoke Vnet and Subnet](image/nimbus-spoke-vnet1.png)

![The Image shows the creation of Spoke Vnet and Subnet](image/nimbus-spoke-vnet2.png)

![The Image shows the creation of Spoke Vnet and Subnet](image/nimbus-spoke-vnet3.png)

![The Image shows the creation of Spoke Vnet and Subnet](image/nimbus-spoke-vnet4.png)


# Step 4  Deploy Three Linux VMs

- Create two VMs in the **nimbus-hub-vnet**  and one VM in **nimbus-spoke-vnet**.

Below the image samples of deploying procedures.

![The Image shows the vm-hub-created ](image/virtual-machine1.png)

![The Image shows the vm-hub-created ](image/virtual-machine2.png)

![The Image shows the vm-hub-created ](image/virtual-machine3.png)

![The Image shows the vm-hub-created ](image/virtual-machine4.png)

![The Image shows the vm-hub-created ](image/vm-hub-1-final.png)

I repeated the process to create vm-hub-2 and vm-spoke-1.

![The Image shows the "vm-hub-2" created ](image/vm-hub-2.png)

![The Image shows the "vm-hub-2" created ](image/vm-hub-2-final.png)

Below show the running of both the hub and spoke vm's.

![the Image shows the running of both hub and spoke vm](image/hub-spoke-vm-running.png)

At this point The three Vm's is installed and can be refer's "IAAS" (Infrastructure as a service.)  iaas simply means Azure provides the underlying computing infrastructure, while I control most of the infrastructure running on it.


# Error

After creating the first bastion Error started appearing,

![the error of the bastion](image/error-creating-bastion.png)

![the error of the bastion](image/error-creating-bastion2.png)


After the error, I have to go back to the Vnet-hub and adjust the subnet from default to using the same subnet of the bastion resource.

![Image shows the bastion subnet resource adjustment](image/bastion-selected-subnet.png)

![Image shows the bastion subnet resource adjustment](image/bastion-final.png)


After the bastion deployment, I have to select VM1-hub **click**  connect and select bastion. The Image below shows the process.


![I have to connect via bastion](image/connect-via-bastion.png)


![I have to connect via bastion](image/connect-via-bastion1.png)



![I have to connect via bastion](image/bastion-running.png)



# Phase 3 Configure NSGs

Control traffic between VNets and VMs.

## steps:

- Search Network Security Groups in the Azure portal.

- Create one NSG for **nimbus-hub-subnet** and one for **nimbus-spoke-subnet**

- Add inbound rules:

- Allow SSH (port 22) from Azure Bastion.

- Allow ICMP (ping) between VMs.

ICMP: Internet Central Message protocol.

 Used to check whether one computer, server or network device can communicate with another over an IP network.

- Associate NSGs with their respective subnets.

- Test connectivity: SSH into VM-hub-1 via Bastion and run ping to vm-spoke-1 private IP. 

![The Image shows the nsg between nimbus hub and nimbus spoke subnet](image/network-security-group.png)


![The Image shows the nsg between nimbus hub and nimbus spoke subnet](image/nsg-nimbus-hub-subnet.png)

![The Image shows the nsg between nimbus hub and nimbus spoke subnet](image/nsg-nimbus-spoke-subnet.png)


From this point below show the adding of inbound rule on the NSG nimbus-hub-subnet and NSG nimbus-spoke-subnet.

![The Image shows the adding of inbound rules on the hub and spoke subnet](image/nsg1.png)

![The Image shows the adding of inbound rules on the hub and spoke subnet](image/nsg2.png)

![The Image shows the adding of inbound rules on the hub and spoke subnet](image/nsg-inbound-security.png)


Associate NSGs with their respective subnets.

- Test connectivity: SSH into the vm-hub-1 via bastion and run ping to vm-spoke-1's via the private IP

More write up

![The Image here shows the ping between the vm-spoke to vm-hub](image/ping1.png)

![The Image here shows the ping between the vm-spoke to vm-hub](image/ping2.png)



# Phase 4 Azure Key Vault Integration

Goal: Securely store and manage secrets.

Go to the search box in the Azure platform "Search"  **Key Vault** Create.

- Set the name to **nimbus-keyyvault** and select the existing resource group.

- Enable RBAC (Role-Based Access Control).

- Go to **Access Control (IAM)** Add role assignment Select **Key Vault Secrets** assign it to my account.

- Navigate to **Secrets** Click **Generate/Import**   Add a secret:

- Name: db-password
- Value: Nimbus@123!
- Save and confirm that your secret is stored.

![The Image shows the azure key vault integration](image/key-vault.png)

![The Image shows the azure key vault integration](image/key-vault1.png)


![The Image shows the azure key vault integration](image/access-control1.png)

![The Image shows the azure key vault integration](image/access-control1-adding.png)

![The Image shows the azure key vault integration](image/access-control1-adding1.png)

![The Image shows the azure key vault integration](image/access-control1-adding2.png)

Review and Writeup

# Phase 5 Secure Blob Storage with Private Endpoint

**Goal:**   Store and access files securely.

 From the search box **Storage Account**

- Set the name to **nimbusstorage** and use the existing resources group.

- In the **Networking** tab, select **Private Endpoint Only**  no public access.

- Once deployed, go to **Containers**  **+ Container** Create a new container

- Upload a sample file (e.g., test.txt).

- Validate secure access via private  networking only.

![The Image shows the Blob storage](image/storage-center-blob-storage.png)

