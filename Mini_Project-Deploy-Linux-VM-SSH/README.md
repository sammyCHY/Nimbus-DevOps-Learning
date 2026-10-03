## Deploy Linux VM and SSH 

Search for the VM in the Azure interface.

![The Image here shows the creation of linux vm](image/linux-vm-machine.png)

![The Image here shows the creation of linux vm](image/linux-vm-machine1.png)

After the selecting all the required input then click ***"Review + Create"***

![The Image shows review and create](image/review-create.png)

Immediately the create is clicked download download private key will display

![The Image shows the download of the private keys](image/create-resources-key.png)

![The Image shows the download of the private keys](image/resources-key-created.png)

Then, click go to resources in the interface.

![The Image shows access to the resources](image/go-to-resources.png)


![The Image shows the running resources](image/running-resources.png)

Click on the connect drop-down and select connect.

![The Image shows the connection to the resources](image/connect-resources.png)

Click connect and link to connecting key link.

![The Image shows the resource connect ](image/connect-resources.png)

Copy the ssh key then go to the downloaded key path and open it in a powershell then paste the copied ssh-key from the linux resource.

![The Image shows the resource ssh key path](image/resource-ssh-key-path.png)

Replace file path-name with pem key name in the download folder

![The Image shows the pem key name replaced in file path](image/pem-key-name.png)

![The Image shows the pem key name replaced in file path](image/pem-key-name-replaced.png)

My first login encountered error as a result of not adding  ".pem" as the extension file.

![The Image shows the pem extension error](image/pem-error.png)


![The Image shows the pem extension error](image/linux-vm-ssh-resource.png)

Below are some few commands run on linux

![The Image shows some commands on the linux VM machine](image/commands-on-linux.png)