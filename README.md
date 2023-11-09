<h1>Active Directory Home Lab</h1>



<h2>Description</h2>
In this repository I covered the creation of a simple Active Directory Home Lab using Oracle Vitrual Box utilising Server 2019, Windows 10 and Powershell. Configuring and running this lab helped my undertsanding of how Active Directory and Windows Networking works 
<br />

<h2>Environments Used </h2>

- <b>[Oracle Virtual Box](https://www.virtualbox.org/)</b>
- <b>[Windows 10 .ISO](https://www.microsoft.com/en-us/software-download/windows10ISO)</b>
- <b>[Windows Server 2019 .ISO](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2019)</b>


## Diagram
- layout followed when making this Active Directory Home Lab

![Active Directory Home Lab Diagram](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/1634b6a2-3048-4dae-930b-9d4418563fbc)


<h2>Walk-through:</h2>

## To start, creating a new Virtual Machine inside Oracle Virtual Box by clicking on "New". Name the first virtual machine "Domain Controller", and selecting the "Windows Server 2019" ISO file as the boot media (ISO Image).

![create DC VM](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/516ee141-b6cb-41de-a1ee-4bf0233ef532)


##  After creating the "Domain Controller" VM, Click "Settings" and navigate to the "Network" tab and select the following options:
- Network Adapter 1 : NAT
  
The Network Adapter 1 serves as the primary link to the internet, bridging with the internal network to facilitate an internet connection from the domain controller to the client machine.

- Network Adapter 2 : Internal Network

The Network Adapter 2 will play a crucial role in hosting client machines (setup in the later stages of the walkthrough), ensuring a smooth and efficient network enviornment

![DC network settings 1](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/4cbf6942-791d-4040-adfb-3707586adad0)
![DC network settings 2](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/e338c406-6267-45ea-b2e0-d1eb0fc5b06d)

##  Booting the Virtual machine and assign IP addressing for the internal network.

![DC network connections](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/6ab15543-5abb-48d5-9502-bc5d23957400)

![DC IPv4 settings](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/2fd47488-d747-43f5-886b-bc032866056f)

## Installing Active Directory in order to create the domain, Naming the server 

![DC server roles AD DS](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/95a5cf16-98b0-4080-b5e2-6716447b5fe5)
![DC deployment config](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/2022bb2b-0de9-454e-a469-73d805158194)

## Installing and configuring Remote Access, and Routing so that clients on the private network (internal network) can access the internet through the domain controler

![DC server roles RA](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/bd5712e5-668d-43d5-ae9c-75f3f6ae1f41)
![DC server roles routing](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/d350d4e8-ac48-427a-ae7b-b32d97abb213)
![DC RAS NAT connection](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/assets/116461769/a4db360b-bf3d-4320-bb3e-06e0e550286a)


##  DHCP setup on the domain controller.

![DCHP Scope 1](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/blob/main/Walkthrough%20Images/DHCP%20scope%201.png)
![DC server roles DHCP](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/blob/main/Walkthrough%20Images/DC%20server%20roles%20DHCP.png)
![DC DHCP scope 1](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/blob/main/Walkthrough%20Images/DC%20DHCP%20scope%201.png)


##  After setting up DCHP, open Powershell ISA and run the script below, made by Josh Madakor to create 1000 users in Active Directory which are used to log into the client machine 

[Power Shell script for creating users](https://github.com/joshmadakor1/AD_PS)

## Now create a new virtual machine name "Client1" which we will use to access the client side of the Home Lab and select the Windows 10 ISO file.

![create Client VM](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/blob/main/Walkthrough%20Images/create%20Client%20VM.png)
![Client VM network settings](https://github.com/Shaun-Simon/ActiveDirectoryHomeLab/blob/main/Walkthrough%20Images/Client%20VM%20network%20settings.png)
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
