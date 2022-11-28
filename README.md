VIRTUAL MACHINES NETWORKING IN AZURE CLOUD
Networking is a system that commits numerous computers in each other to share information. When devices connect to a network, it needs unique ID to be able to send and receive information. This unique id is an IP address. 
There are two types of IP address: Ip version 4 and Ip version 6. The IP address has four numbers separated by periods (.), e.g., 20.119.218.121. each number is called octet. Octet means groups of eight things.
The IP address consists of two parts: Network address and host address.
Common Network Tools
I.	Ping
II.	Remote desktop connections
III.	Intracert
IV.	nslookup
V.	Ip config 
Ports and Protocol
Ports is essentially where a network can start and end while protocols is a set of rules established by the network on how data is transmitted among devices. The protocols are:  
Tcp: Transmission control protocol
Udp: User datagram protocol
Protocols and their port numbers
HTTP: 80(TCP)
HTTPS: 443 (TCP)
DHCP: 67 AND 68 (UDP)
RDP: 3389 (TCP)
SSH: 22 (TCP) 
ICMP: no ports
Steps and demonstrations
 Create the Resources
1.	Create a Resource Group
2.	Create a Windows 10 Virtual Machine and a Linux (Ubuntu) VM
1.	While creating the VMs, select the previously created Resource Group
2.	While creating the VMs, allow it to create a new Virtual Network and Subnet
3.	Observe Your Virtual Network within Network Watcher
Observe ICMP Traffic
1.	Use Remote Desktop to connect to your Windows 10 Virtual Machine
 
2.	Within your Windows 10 Virtual Machine, Install Wireshark
3.	Open Wireshark and filter for ICMP traffic only
 
4.	Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM
a.	Observe ping requests and replies within Wireshark

Observe SSH Traffic
1.	Back in Wireshark, filter for SSH traffic only
2.	From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
3.	Type commands (ls, pwd, etc.) into the Linux SSH connection and observe SSH traffic spam in Wireshark
 
4.	Exit the SSH connection by typing ‘exit’ and pressing [Enter
Observe DHCP Traffic
1.	Back in Wireshark, filter for DHCP traffic only
2.	From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew)
3.	Observe the DHCP traffic appearing in Wireshark
Observe DNS Traffic
1.	Back in Wireshark, filter for DNS traffic only
2.	From your Windows 10 VM within a command line, use nslookup to see what google.com IP address
 
3.	Observe the DNS traffic being show in Wireshark
Observe RDP Traffic
1.	Back in Wireshark, filter for RDP traffic only (udp.port == 53)
 

2.	 the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
3.	Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted

Cleanup 
1.	Close your Remote Desktop connection
2.	Delete the Resource Group(s) created at the beginning of this lab
3.	Verify Resource Group Deletion

Resources I used: Coursecareers



