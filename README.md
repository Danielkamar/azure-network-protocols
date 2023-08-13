<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDP, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic
  
<h2>Actions and Observations</h2>
<br />
<br />
<br />
Download and install Wireshark on a Windows 10 Virtual Machine. Open Wireshark and Powershell; In wireshark, filter for ICMP traffic only, and ping the Ubuntu Server VM in Powershell. Also try to ping a website, for example - google.com. 
<br />
<br />
<img src="https://i.imgur.com/HEYD27W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Go to azure and stop ICMP traffic by creating a rule in Network Security groups. Then after seeing it works, delete the rule or change "deny" all ICMP traffic to "Allow" all ICMP traffic. 
<br />
<br />
<img src="https://i.imgur.com/t4fgcAP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Go back to the windows VM and filter traffic for SSH in Wireshark. Then connect to the Ubuntu Server VM on Powershell. After connecting, type some commands and observe traffic on Wireshark.
<br />
<br />
<img src="https://i.imgur.com/5RsULcq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/7VXZfTG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Filter for DHCP traffic, and type ipconfig /renew on Powershell to reissue your ip address. 
<br />
<br />
<img src="https://i.imgur.com/4dgY4IJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Filter for DNS traffic on wireshark, and use nslookup to see what famous website ip addresses are. 
<br />
<br />
<img src="https://i.imgur.com/ZCUpqsG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/vNx4SYE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Filter for RDP traffic, and you will see that there is a non stop flow of traffic. That is because RDP(protocol) is constantly showing you a live stream from one computer to another, therefore traffic is always being transmitted
<br />
<br />
<img src="https://i.imgur.com/kANKqtP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
