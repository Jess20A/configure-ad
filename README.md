<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

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

</p>
<p>
In Microsoft Azure create a client VM using Windows 10 and a Domain Controller using Windows Server 2022. For the Domain Controller you will need to set the Network Interface Card to static.
</p> 
<br />

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
<br />
