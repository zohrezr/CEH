$\color{#b91646}{\textsf{Scapy}}$
==================================

**ساخت پکت های شخصی**

- **Scapy. Packet manipulation tool. Capture, create, play, replay, scan and discover**

برنامه ی دستکاری پکت ها

- **Written in python**
- **Usage in testing rules**

خیلی وقتا برای چک کردن rule های firewall استفاده می کنن.

- **scapy, run and check with wireshark**
  - send(IP(src="192.168.1.55", dst="192.168.1.1")/ICMP()/"HappyPayload")
  - You can manipulate layer 2, 3, 4
  - L2 = Ether(); L3=IP(); L4=TCP()
  - L2.show()
  - del(L3.src)
  - L4 = TCP(sport=564, dport=21, flags=”A”)
  - Send = sendp(L2/L3/L4)
  - sniff(iface=”eth0”, prn=lambda x: x.show())
  - a=sniff(filter=”host 192.168.1.1”, count=5)
  - a.nsummary()
  - Finish with Ctrl + D
