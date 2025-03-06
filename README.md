<p align="center">
<img src="https://github.com/user-attachments/assets/e0a11840-0c5b-4aee-800b-031bb0a48fd1" height="30%" width="30%"/>
</p>

<h1>Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we analyze various network traffic flows to and from Azure Virtual Machines using Wireshark.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Windows and Linux Command Line Tools
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2)
- Ubuntu Server 22.04

<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/user-attachments/assets/1feffac1-bcc7-40e8-bd70-7fe4d38baaae" height="80%" width="80%"/>

</p>
<p>
Create two VMs in the Azure portal: one using a Windows 10 Pro image and the other using a Linux image, each with 2 vCPUs. Ensure both VMs are attached to the same virtual network during setup. Use RDP to access the Windows machine.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/a4042b56-2199-40e3-8166-0fdbd810367e" height="50%" width="50%"/>
</p>
<p>
Download and install Wireshark from https://www.wireshark.org. This tool will be used to observe network traffic.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/5372007f-be0a-49e9-9a9a-478af9a44b83" height="80%" width="80%"/>
</p>
<p>
After installing Wireshark, open the application and double click on the word "Ethernet" to start the capture process. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/0b50f841-ecd1-4d76-807f-45590fd2c16f" height="80%" width="80%"/>
</p>
<p>
To filter for ICMP traffic, type icmp in the search bar. ICMP is used by network devices to send error messages and check connectivity.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/ae6b9757-cc93-478e-8a9e-7baedabe5227" height="80%" width="80%"/>
</p>
<p>
Open PowerShell and use the ping command to test the connectivity to the private IP address of the Linux machine(10.0.0.5), which is on the same network. You can find the Linux machine's private IP address in the Azure portal under the VM's network settings.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/77494b39-2ef7-4649-bbec-16d65d16f180" height="80%" width="80%"/>
</p>
<p>
You can view each packet sent while pinging the machine in Wireshark, displaying the ICMP traffic for analysis. 
</p>
<br />
Wireshark can also be used for analysing other Network Protocols such as SSH, RDH, DNS, and HTTP/S. This can be seen in [Network Security Groups (NSGs)](https://github.com/gustygreen/azure-network-protocols).
