<h1>Home Lab Running Active Directory (Oracle VirtualBox) Add Users w/PowerShell</h1>


<h2>Description</h2>
This project documents the step-by-step process of setting up an Active Directory (AD) home lab using Oracle VirtualBox and the bulk addition of users using PowerShell. It provides a comprehensive guide to recreate the environment and perform user management tasks efficiently.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Windows Server 2019</b> 

<h2>Walk-Through:</h2>

<p align="left">
<strong>Step 1: Download and Install Software</strong>

Download and install Oracle VirtualBox along with the Extension Pack.

Download the Windows 10 and Windows Server 2019 ISO files.

- [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Windows 10](https://www.microsoft.com/en-us/software-download/windows10)
- [Windows Server 2019](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)

<strong>Step 2: Create the Domain Controller</strong>

Create a new virtual machine in VirtualBox for the Domain Controller (DC).

Configure two network adapters for the DC VM: one for internet access and one for the private VirtualBox network for clients.

<img src="https://i.imgur.com/D2XiGSt.png" height="80%" width="80%" alt="Network Adapter 1"/>
<img src="https://i.imgur.com/Qf8yHqK.png" height="80%" width="80%" alt="Network Adapter 2"/>

<strong>Step 3: Install and Configure Windows Server 2019</strong>

Install Windows Server 2019 on the DC VM.

Assign an IP address for the internal network adapter.

Name the server and configure basic settings.

<img src="https://i.imgur.com/h1st7oY.png" height="80%" width="80%" alt="Server 2019"/>
<img src="https://i.imgur.com/3DcMOwZ.png" height="80%" width="80%" alt="IP"/>
<img src="https://i.imgur.com/JZTeHiS.png" height="80%" width="80%" alt="Name"/>

<strong>Step 4: Install and Configure Active Directory</strong>

Install the Active Directory Domain Services role.

Promote the server to a domain controller.

Configure DNS settings.

Create the domain.

<img src="https://i.imgur.com/P5Hdeqp.png" height="80%" width="80%" alt="AD"/>
<img src="https://i.imgur.com/ZoZx5Z7.png" height="80%" width="80%" alt="Promote"/>
<img src="https://i.imgur.com/Znxeuuw.png" height="80%" width="80%" alt="Domian"/>

<strong>Step 5: Configure NAT and Routing</strong>

Configure Network Address Translation (NAT) and routing on the DC VM to allow private network clients to access the internet through the domain controller.

<img src="https://i.imgur.com/Jqz9M8g.png" height="80%" width="80%" alt="NAT"/>

<strong>Step 6: Setup DHCP</strong>

Configure DHCP on the domain controller so that Windows 10 clients can automatically obtain IP addresses.

<img src="https://i.imgur.com/3GlmYQB.png" height="80%" width="80%" alt="DHCP"/>
<img src="https://i.imgur.com/sEH6g2H.png" height="80%" width="80%" alt="AddressRange"/>
<img src="https://i.imgur.com/cY3T9X3.png" height="80%" width="80%" alt="Gateway"/>

<strong>Step 7: Bulk User Addition with PowerShell</strong>

Run a PowerShell script to automatically create a thousand users in the Active Directory.

<img src="https://i.imgur.com/j5ipaTM.png" height="80%" width="80%" alt="PowerShell"/>

<strong>Step 8: Create a Windows 10 Client</strong>

Create another VM named CLIENT1 in VirtualBox.

Install Windows 10 on CLIENT1.

Connect CLIENT1 to the private VirtualBox network.

<img src="https://i.imgur.com/LfwcVV2.png" height="80%" width="80%" alt="CLIENT1"/>
<img src="https://i.imgur.com/V8dGlWQ.png" height="80%" width="80%" alt="Windows"/>

<strong>Step 9: Join the Client to the Domain</strong>

Join CLIENT1 to the domain you created in Active Directory.

Log into CLIENT1 using one of the domain accounts.

<img src="https://i.imgur.com/enmijPP.png" height="80%" width="80%" alt="JoinDomain"/>
<img src="https://i.imgur.com/2pJxqaH.png" height="80%" width="80%" alt="LogIn"/>




















