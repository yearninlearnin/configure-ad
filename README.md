<p align="center">
<img src="https://i.imgur.com/x1ky7pf.png" alt="osTicket logo"/>
</p>


<h1>On-prem Active Directory Deployed in the Cloud using Microsoft Azure *DOCUMENTATION UPDATED AND COMPLETED*</h1> 
This lab outlines the implementation of on premises Active Directory within Azure.<br />
---------------------------------------------------------------------------------------------

<p>
Our end goal of this lab is to use utilize AzureVM to create a couple of environments. One needed for the ActiveDirectory Environment including the domain, and the other to simulate a normal user.
</p>
<p>
<img src="https://i.imgur.com/ziHTBY0.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
I need to use 2 Virtual Machines. One will act as the Domain Controller, and the other will be the client as seen below.
</p>
<p>
<img src="https://i.imgur.com/W8XllC5.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
The Domain Controller requires a little tweaking initially. Within AzureVM, I need to configure it to have a static IP instead of dynamic as it will act as a server to house our Active Directory.
</p>
<p>
<img src="https://i.imgur.com/dZeUwXD.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
To ensure connection between both the Domain controller and my client vm, I had to enable ICMPv4 in the local Windows firewall.
</p>
<p>
<img src="https://i.imgur.com/Vl4oh7K.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
The installation process of Active Direct begins as well as promoting promoting the server to a domain controller.
</p>
<p>
<img src="https://i.imgur.com/H1s7H6s.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
</p>
<p>
<img src="https://i.imgur.com/J5ydr6C.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
</p>
<p>
<img src="https://i.imgur.com/npKbIFg.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
Active Directory is now fully installed.
</p>
<p>
<img src="https://i.imgur.com/yqCuSbr.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
I created some organizational units for the purpose of this lab. One group consists of Admins, and the other Employees. I add my domain admin "Boba Fett" to the admin and later on I will run a script to create a batch of employee accounts.
</p>
<p>
<img src="https://i.imgur.com/BnNoume.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
</p>
<p>
<img src="https://i.imgur.com/FDnbqh7.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
</p>
<p>
<img src="https://i.imgur.com/JAqLUML.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>

</p>
<p>
<img src="https://i.imgur.com/ZG1BOJq.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>

</p>
<p>
<img src="https://i.imgur.com/eSNsFc1.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
These are the current users with remote access, noting that Boba Fett is an admin now.
</p>
<p>
<img src="https://i.imgur.com/yG4KN49.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
This is a script that was built to be used in powershell to generate generic endusers based on a few perameters such name count, name length etc.
</p>
<p>
<img src="https://i.imgur.com/8t2clhq.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
I'll pick a couple of random user account out of the employee pool to simulate the logon process. User nunis.giho will be able to log in successfully but the other user "renin.lofo" will have issues with their password,causes them to get locked out of their account. We will then use Active Directory to unlock their account and send a prompt for them to update their password upon logging in.
</p>
<p>
<img src="https://i.imgur.com/lx6p6hH.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>

</p>
<p>
<img src="https://i.imgur.com/cSCpLfp.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>

</p>
<p>
<img src="https://i.imgur.com/XdHpqJn.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>

</p>
<p>
<img src="https://i.imgur.com/FMTDE1v.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
This slide simulates user renin.lofo failing to log into their account and after about 5 attempts, this will prompt Active Directory to automatically lock their user account.
</p>
<p>
<img src="https://i.imgur.com/6X6GrBm.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>

</p>
<p>
<img src="https://i.imgur.com/SZICSPL.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />
<p>
Now Im preparing to unlock user renin.lofo's account. Once they log back in, they will be prompted to reset their password.
  This concludes the lab on configuring Active Directory for user account management.
</p>
<p>
<img src="https://i.imgur.com/v2IU266.png" height="80%" width="80%" alt="Installation Steps"/>
</p>
<br />

