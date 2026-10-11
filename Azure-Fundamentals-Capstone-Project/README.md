#  Azure Fundamentals Capstone Project.

## Project Architecture.








****************************************

This Capstone project marks the completion of the Azure fundamentals.

# Create Resource Group
# Step 1
- Login into the Azure platform and search **resource-group**

- Name of the Resource-group and create

- Below show the image process of execution.

![The Image shows the creation resource group](image/resource-group1.png)

![The Image shows the creation resource group](image/resource-group2.png)

![The Image shows the creation resource group](image/resource-group3.png)

![The Image shows the creation resource group](image/resource-group4.png)


# Task
-  I have to deploy a secure, multi-VNet Azure environment entirely through the Azure Portal, step by step.

Goal: Build a production-style secure environment using Azure Portal only.


Module: Azure Fundamentals.

# Step2     Create the First Virtual Nertwork.

  - Search for **Virtual Network** Click  **Create**

  - Resource Group: nimbus-labs

  - Name: nimbus-hub-vnet

  - Region: (e.g., East US)

  - Go to the **IP Addresses** tab:

  - Address space: 10.0.0.0/16

  - Subnet Name: nimbus-hub-subnet

  - Subnet Address Range: 10.0.1.0/24

  - Leave other options at default  Click **Review + Create** -----> **Create**

  Below shows the Image procedure's on the creation Virtual Network and the Subnet.

  ![The Image shows the creation of Vnet and Subnet](image/hub-virtual-network-subnet1.png)

  ![The Image shows the creation of Vnet and Subnet](image/hub-virtual-network-subnet2.png)

  ![The Image shows the creation of Vnet and Subnet](image/hub-virtual-network-subnet3.png)

  ![The Image shows the creation of Vnet and Subnet](image/hub-virtual-network-subnet4.png)


# Step 3 Create the Second Virtual Network
    I have to repeat the same process but small twick on the IP

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

# Error

After creating the first bastion Error started appearing,

![the error of the bastion](image/error-creating-bastion.png)

![the error of the bastion](image/error-creating-bastion2.png)


After the error, I have to go back to the Vnet-hub and adjust the subnet from default I was using the same subnet of the bastion resource.

![Image shows the bastion subnet resource adjustment](image/bastion-selected-subnet.png)

![Image shows the bastion subnet resource adjustment](image/bastion-final.png)



After the bastion deployment, I have to select any VM then connect and select bastion

![I have to connect via bastion](image/connect-via-bastion.png)


![I have to connect via bastion](image/connect-via-bastion1.png)



![I have to connect via bastion](image/bastion-running.png)



Phase 3 Configure NSGs

Control taffic between VNets and VMs.

steps:

- Search Network Security Groups in the Azure portal.

- Create one NSG for **nimbus-hub-subnet** and one for **nimbus-spoke-subnet**

Need to complete the write up later.

![The Image shows the nsg between nimbus hub and nimbus spoke subnet](image/network-security-group.png)


![The Image shows the nsg between nimbus hub and nimbus spoke subnet](image/nsg-nimbus-hub-subnet.png)

![The Image shows the nsg between nimbus hub and nimbus spoke subnet](image/nsg-nimbus-spoke-subnet.png)


From this point below show the adding of inbound rule on the NSG nimbus-hub-subnet and NSG nimbus-spoke-subnet.

![The Image shows the adding of inbound rules on the hub and spoke subnet](image/nsg1.png)

![The Image shows the adding of inbound rules on the hub and spoke subnet](image/nsg2.png)

![The Image shows the adding of inbound rules on the hub and spoke subnet](image/nsg-inbound-security.png)


Associate NSGs with their respective subnets.

- Test connectivity: SSH into the vm-hub-1 via bastion and run ping to vm-hub-2's private IP

More write up

![The Image here shows the ping between the vm-spoke to vm-hub](image/ping1.png)

![The Image here shows the ping between the vm-spoke to vm-hub](image/ping2.png)



# Phase 4 Azure Key Vault Integration

Goal: Securely store and manage secrets.


more write up........  many....

![The Image shows the azure key vault integration](image/key-vault.png)

![The Image shows the azure key vault integration](image/key-vault1.png)


![The Image shows the azure key vault integration](image/access-control1.png)

![The Image shows the azure key vault integration](image/access-control1-adding.png)

![The Image shows the azure key vault integration](image/access-control1-adding1.png)

![The Image shows the azure key vault integration](image/access-control1-adding2.png)


Review and Writeup

# Phase 5 Secure Blob Storage with Private Endpoint

Store and access files securely.

More Write up

![The Image shows the Blob storage](image/storage-center-blob-storage.png)

