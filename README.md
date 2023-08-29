<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This overview outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Virtual Machines
- Ensure Connectivity between the Client and Domain Controller
- Install Active Directory
- Join the Client to the Domain
- Create Users 

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="487" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/cac9b6d1-5d2f-4e5e-b00c-aff206c74c45">

<img width="300" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/e691779f-fe8d-4c2a-ace8-82bdb9f962fb">


<p>
In Microsoft Azure create a client VM using Windows 10 and a Domain Controller using Windows Server 2022. For the Domain Controller you will need to set the Network Interface Card to static.
</p> 


<p>
<img width="195" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/235ece0c-6a56-4bef-8c9b-30f7cd18eb58">

<img width="569" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/9a1fc82b-f866-47f7-b932-b63907ca4802">


</p>
<p>
Ensure connectivity between the CLient and Domain Controller by opening up command prompt and pinging the Domain Controllers private IP Address. For this to work go to Windows Defender Firewall with Advanced Security and click inbound rules. Afterwards enable the ICMPv4 rules to make a hole in the firewall and allow traffic to go through. 
</p>
<br />

<p>
<img width="416" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/2dcc9f3e-1fbc-4f85-8123-9adc47dfc449">

<img width="365" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/5258f77c-8690-4426-a3c2-2704ff37afdd">

</p>
<p>
Install Active Directory on the Server Manager by going to Add Roles and Features. When you get to server roles click Active Directory Domain Services and proceed through until installed successfully.
</p>


<img width="209" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/0fc10cbe-7b12-419a-8dce-bbb1a045b8f8">

<img width="192" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/fedd9fb2-d6c5-4980-a9ca-defc02d845ec">


Using Active Directory Users and Computers, create a user account and make that user a member of the Domain Admins security group. You will use this main account as the Domain's Administrator.


<img width="385" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/183e23d9-c318-4847-a2bf-fd897f275d63">

<img width="455" alt="image" src="https://github.com/Jess20A/configure-ad/assets/142112890/da9b2526-bcce-417a-aa43-afffa42a1357">


To join your Client VM to your Domain Controller, set the Client's DNS setting to the Domain Controllers private IP address. Restart the Client VM and log in with the original local admin account. In the settings go to Rename this PC (Advanced) > Change > Member Of and then type in the domain name. Afterwards you will have to enter the name of the domain and password to be joined.


