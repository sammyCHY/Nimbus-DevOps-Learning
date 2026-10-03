## How to Deploy window VM on the microsoft azure cloud.

**There are two common ways to connect (get into) a Microsoft Azure VM:**

1. RDP ***Remote Desktop Protocol*** — mainly for Windows VMs
Use Remote Desktop Connection on your computer.
Enter the VM's public IP address.
Sign in with the Windows username and password.


First you need to login into the microsoft azure platform, then search for virtual machine in the search box or select the virtual as shown in the image interface below.

![The image here shows the selection and creation of vm](image/virtual-machine.png)

Follow the procedures in the Image below to create a window microsoft virtual machine.


![The Image shows the creation of ms vm](image/creating-vm1.png)


![The Image shows the creation of ms vm](image/creating-vm2.png)


![The Image shows the creation of ms vm](image/creating-vm2.png)

After the steps above, proceed, click review and create.

![The Image shows review and create](image/review-create.png)

After the vm deployment completed, then **click** "go to resources"


![The VM deployment completed](image/vm-deployment-completed.png)

Below the Image is the view of the resources created

![the image shows the resources created](image/resources-created.png)


After creating the resource, select ***connect*** at the top left side of the screen and click ***connect***

![The Image below shows the connection window vm ](image/vm-connect.png)

Connect will take you to another page then proceed by clicking ***Download RDP File***


![The Image shows the downloading of RDP file](image/download-rdp-file.png)


![The Image shows the downloading of RDP file](image/rdp-login.png)

![The Image shows the downloading of RDP file](image/rdp-yes.png)

Window finally installed.

![The vm window installed](image/window-installed1.png)


![The vm window installed](image/window-installed2.png)


If you do not want to expose your IP, follow the alternative route on the Image below.

![The alternative route to creating of window vm](image/connect-via-bastion.png)

![The alternative route to creating of window vm](image/connect-via-bastion1.png)


Finally all the running resources is here.

![The Image shows all the running resources](image/running-resources.png)


After installing and viewing  all the resources. Follow the process below to delete the created resources.

![Deleting the created resources](image/resource-group.png)


![Deleting the created resources](image/resource-group1.png)


![Deleting the created resources](image/resource-group2.png)

Simple ways to remember

VM                              Common Connection Method

🐧 Linux VM                         SSH

🪟 Windows VM                       RDP



updating the last file



2. SSH (Secure Shell) — mainly for Linux VMs

From your terminal:

ssh username@<public-ip-address>
You can authenticate using an SSH key or password, depending on how the VM was configured.


