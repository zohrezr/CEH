$\color{#b91646}{\textsf{ARP poisoning or spoofing}}$
======================================================

### $\color{#25678D}{\textsf{Address Resolution Protocol}}$


- Request will broadcast its MAC+IP toward 00MAC+IP. Everyone will check and if its their IP, they will respond with their MAC+IP
- Gratuitous ARP is like tipping or proxy arp. Just a packets saying “this is my MAC + IP”



First we need to understand the ARP
Attacker will send gratuitous to router with its MAC and target IP. And another one to the target, telling it its MAC as routers IP. 
Tools like Ettercap, Cain & Abel & arpspoof
We can also do a Mac Spoof! Become someone else
arpspoof -i eth0 -t target -r default_gw

Defence:
ARP inspection. Header to payload verification. Will check the IP and MAC with what it learned on Port from DHCP or ARP ACL (static list). This should run on untrusted ports.

	

