<p align="center">
<img src="https://imgur.com/RfN1vvw.png" alt="Windows Server"/>
</p>

<h1>Windows Server Updates</h1>
In this tutorial, we observe how to install Windows Server Updates in Server Manager. This tutorial is an excellent way to explore Active Directory and understand how and why Windows Updates are important to users to have scheduled updates to protect their information. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Server Manager
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022

<h2>High-Level Steps</h2>

- Step 1: Remotely Login to Virtual Machine
- Step 2: Direct DNS Server to Domain Controller
- Step 3: Configure Windows Server Updates Services in Server Manager
- Step 4: Approve All Updates in Update Services

<h2>Actions and Observations</h2>

<h2>Navigate to Updates and Security</h2>
<p>
<img src="https://imgur.com/NfsAACS.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assuming that we are manually setting up a new computer, navigate to updates and security to check for updates under Settings. If you receive an "Error Encountered" message it means that there is no DHCP Server and will need to add a static IP address
</p>
<br />
<h2>Navigate to Network and Security (cont.)</h2>
<p>
<img src="https://imgur.com/vwdPYL8.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, navigate to Network and Internet --> "Network and Sharing Center" --> Select "Change Adapter Settings" --> Click on "Turn on or off Windows Settings" --> right-click on Ethernet and select "Properties". Next, select IPv4 to direct the DNS Server back to itself, the set IP for the domain controller (computer with Active Directory installed on the virtual machine).
</p>
<br />
<h2>Configure and Add Windows Server Update Services in Server Manager</h2>
<p>
<img src="https://imgur.com/cBNWihb.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, open Server Manager and select "Add roles and features". Under Server Roles, select "Windows Server Update Services" and continue the steps for the configuration wizard. In the configuration wizard, you will have different features that can be added or removed such as adding a SQL database and where to place installation files. After clicking through the next few slides, click on Install.
</p>
<br />
<h2>Windows Server Configuration Wizard</h2>
<p>
<img src="https://imgur.com/Pl3R09W.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once installed, click on the Notifications Flag in Server Manager and select "Launch Post Installation Tasks" to open the Windows Server Update Services Configuration Wizard.
</p>
<br />
<h2>Windows Server Configuration Wizard (cont.)</h2>
<p>
<img src="https://imgur.com/j3UYBru.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
You'll have the option to synchronize (or download) from another Windows server update if you have one available. In this case, we can choose and synchronize from Microsoft update. Click next on the next few selects and choose configurations as needed.
</p>
<br />
<h2>Windows Server Configuration Wizard (cont.)</h2>
<p>
<img src="https://imgur.com/QJzCb2c.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select Start Connecting and choose the appropriate language. The more languages that are chosen, the more storage space that is required. Please note that this can take at least 30 minutes to complete.
</p>
<br />
<h2>Windows Server Configuration Wizard (cont.)</h2>
<p>
<img src="https://imgur.com/tfWL2lD.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Under Products, choose the products that are required. You can see by default that Windows is selected. In this case, we can unselect Windows and only choose systems needed, such as Windows 11.
</p>
<br />
<h2>Windows Server Configuration Wizard (cont.)</h2>
<p>
<img src="https://imgur.com/4VUAXv6.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Under Classifications, Critical, Definition and Security updates are automatically installed for antimalware. For demo purposes, we can just choose "critical updates". Next, we can choose to manually or automatically synchronize and the updates will be sent to the updates folder that was created earlier.
</p>
<br />
<h2>Update Services</h2>
<p>
<img src="https://imgur.com/qxCe9Bu.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Expand Server Updates, select All Updates, and choose any for approval and status. (Set up a group policy for all clients on where to look for updates, create specific groups for all unassigned computer, and have specific groups).
</p>
<br />
<h2>Update Services (cont.)</h2>
<p>
<img src="https://imgur.com/wOoiVT4.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, you can explore the different options and features in the "Update Services" In this demo, we can take a look at "Options" - go to products and classifications to add additional operating systems and apps that you may have missed, in case things change.
</p>
<br />
