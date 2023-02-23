<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- PowerShell
- Remote Desktop
- Active Directory Domain Services
- Microsoft Azure (Virtual Machines/Compute)


<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Windows Server 2022

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Create resources
- Step 2: Establish connectivity to between Domain Controller and Client
- Step 3: Install Active Directory
- Step 4: Create an administrator and regular account in Active Directory
- Step 5: Join Client to the Domain Controller 
- Step 6: Setup Remote Desktop for non-administrative users to Client
- Step 7: Create users in Active Directory using Powershell script

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://imgur.com/z1I0JEH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1.) First step is to create to two Azure virtual machines.

The first virtual machine is the domain controller (DC-1) which will have Windows Server 2022. A domain controller is the main server computer network that gives access to its domain resources and authenticates users that are connected to it. 

The second virtual machine is the client (Client-1) which will have Windows 10. The client is just any computer connected to the domain controller. 

Keep in mind: Ensure that Client-1 is on the same virutal network as DC-1. This is normally automatically done under the "Networking" tab but double check.
</p>
</p>
<br />

<p>
<img src="https://imgur.com/vaAbOOA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
2.) Next is to ensure DC-1's private IP address is changed from dynamic to static. DC-1's private IP address needs to be static so it does not change during the course of this exercise.
To do this, go to DC-1's "Networking" section and click on the virtual Network Interface Card (NIC). (IP Config.. click private IP address.. assignment button and switch from dynamic to static..

Second step is establish connectivity between Client-1 and DC-1. Use Microsoft Remote Desktop to connect to both virtual machines. 
Open Client-1 and open the Command line. Type in the command "ping -t" + the private IP address of DC-1. In this case, it is 10.0.0.4. The "ping -t" command will continously ping DC-1.Next is to ensure DC-1's private IP address is changed from dynamic to static. DC-1's private IP address needs to be static so it does not change during the course of this exercise.
To do this, go to DC-1's "Networking" section and click on the virtual Network Interface Card (NIC). (IP Config.. click private IP address.. assignment button and switch from dynamic to static..

Second step is establish connectivity between Client-1 and DC-1. Use Microsoft Remote Desktop to connect to both virtual machines. 
Open Client-1 and open the Command line. Type in the command "ping -t" + the private IP address of DC-1. In this case, it is 10.0.0.4. The "ping -t" command will continously ping DC-1.
<br />

<p>
<img src="https://imgur.com/e9sOsYV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3.
</p>
<br />

<p>
<img src="https://imgur.com/aYJepmI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
4.) Due to the firewall blocking incoming Internet Control Message Protocol (ICMP) traffic, the request is timing out. To fix this, login into DC-1 and open the application Windows Defender Firewall with Advanced Security from the Start menu.


</p>
<br />

<p>
<img src="https://imgur.com/ycJc1wK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
5.
</p>
<br />

<p>
<img src="https://imgur.com/C0dlvC7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
6.
</p>
<br />

<p>
<img src="https://imgur.com/HmjKnIL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
7.
</p>
<br />

<p>
<img src="https://imgur.com/2CcVqOp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
8.
</p>
<br />

<p>
<img src="https://imgur.com/LU21u5Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
9.
</p>
<br />

<p>
<img src="https://imgur.com/Xklu4PJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
10.
</p>
<br />


<p>
<img src="https://imgur.com/Ou2hw8A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
11.
</p>
<br />

<p>
<img src="https://imgur.com/yfvmKXl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
12.
</p>
<br />

<p>
<img src="https://imgur.com/hV38MqF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
13.
</p>
<br />

<p>
<img src="https://imgur.com/5CPghKW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
14.
</p>
<br />


