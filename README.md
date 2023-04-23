<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Sharing Files and Permissions with Our Active Directory Setup</h1>
This tutorial outlines sharing files and permissions within our Active Directory created using virtual machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Version 21H2

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Sample File Shares with Various Permissions
- Attempt to Access Those Files as a Normal User
- Create a Security Group, Assign Permissions, and Test Access

<h2>Deployment and Configuration Steps</h2>

<p>
First we will create four new folders on the C:\ Drive in DC-1: "Read-access", "Write-access", "No-access", and "Accounting".  We will set the permissions to each folder as follows: "Read-access" - Group: "Domain Users", Permission: "Read"; "Write-access" - Group: "Domain Users", Permission: "Read/Write"; "No-access" - Group: "Domain Admins, Permissions: "Read/Write".  We will use the "Accounting" folder later.
</p>
<p>
<img src="https://i.imgur.com/pdhQXby.jpg" height="80%" width="80%" alt="Create Four New Folders"/>
</p>
<p>
<img src="https://i.imgur.com/XR7FPQJ.jpg" height="80%" width="80%" alt="Add Permissions to Domain Users"/>
</p>
<p>
<img src="https://i.imgur.com/ATb3t9d.jpg" height="80%" width="80%" alt="Add Permissions to Admin Users"/>
</p>
<br />
<hr>
<p>
Now we will select a randomly generated name and log into Client-1 as that user.
</p>
<p>
<img src="https://i.imgur.com/9h8dJQZ.jpg" height="80%" width="80%" alt="Select Random User"/>
</p>
<p>
<img src="https://i.imgur.com/MaPbxrT.jpg" height="80%" width="80%" alt="Random User Loggin In"/>
</p>
<br />
<hr>
<p>
Now we will test that user attempting to access the new folders we created.  As you can see we are able to open the "Read-access" folder but we are unable to modify it.  We can open and modify the "Write-access" folder.  And finally we can see that we are unable to open the "No-access" folder.
</p>
<p>
<img src="https://i.imgur.com/tCtzHaC.jpg" height="80%" width="80%" alt="Read Access Allow"/>
</p>
<p>
<img src="https://i.imgur.com/9OnnRlN.jpg" height="80%" width="80%" alt="Read Access Modify Deny"/>
</p>
<p>
<img src="https://i.imgur.com/cMu6Spk.jpg" height="80%" width="80%" alt="Write Access Allow"/>
</p>
<p>
<img src="https://i.imgur.com/Cwd7Pxu.jpg" height="80%" width="80%" alt="No Access Deny"/>
</p>
<br />
<hr>
<p>
Now we will switch back to our DC-1 and create a new Security Group named "Accountants".  We will then set the permissions for the "Accounting" folder to only allow members of the "Accounting" Security Group to read/write files.  We will then try to access the "Accounting" folder as our user on Client-1.
</p>
<p>
<img src="https://i.imgur.com/LbHaEyU.jpg" height="80%" width="80%" alt="Share Accounting Folder"/>
</p>
<p>
<img src="https://i.imgur.com/OIypu64.jpg" height="80%" width="80%" alt="Create Accountants Security Group"/>
</p>
<p>
<img src="https://i.imgur.com/t6AltyH.jpg" height="80%" width="80%" alt="Accounting Folder Denied"/>
</p>
<hr>
<p>
No we will switch back to our DC-1 and add our user to the "Accountants" Security Group and see that our user now has access to the "Accounting" folder.
</p>
<p>
<img src="https://i.imgur.com/JNxeaFo.jpg" height="80%" width="80%" alt="Add User to Security Group"/>
</p>
<p>
<img src="https://i.imgur.com/08qGIO5.jpg" height="80%" width="80%" alt="Account Folder Access"/>
</p>
<br />
<hr>
<p>
That's it for this project. We have shown how to share files and permissions.  We've also shown how to add users to security groups.
