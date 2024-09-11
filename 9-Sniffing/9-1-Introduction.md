$\color{#b91646}{\textsf{Introduction}}$
=============================================

- **Wiretapping on network**
- **How**
  - Passive
  - Active
  - we have to be in Promiscuous mode to read all FRAMES (layer 2) and won't filter only for our own MAC. “ifconfig -a” will show if we are in promiscuous mode
  - MAC flooding (send too many to overflow the CAM)
  - DHCP attacks
  - ARP Poisoning 
  - DNS Poisoning
  - Spanning on switch



- **HTTP, Telnet, email, ftp, rlogin, POP, IMAP, …** 
- **Software (snort, winpcap, wireshark, tcpdump,...) vs Hardware (protocol analyzer)**

- **Detection**
  - Finding promiscuous interfaces using a ping to unknown IP & MAC and seeing answers or using NMAP
