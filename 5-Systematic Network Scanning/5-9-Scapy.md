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
 ____________________________
 ### $\color{#25678D}{\textsf{Run scapy}}$

**توی کالی از قبل نصب شده**

`#scapy`

________________________________

### $\color{#25678D}{\textsf{help}}$

`>>> help()`
________________________________________
### $\color{#25678D}{\textsf{Send packet}}$
`>>> send(IP(src="Source IP", dst="Destination IP")/ICMP()/"Happy there")`

یه بسته ای رو از Source IP به Destination IP با پروتکل ICMP با payload=Happy there ارسال کن.

**توی لایه ی 2, 3, 4 می تونیم تنظیمات انجام بدیم و دیتا بفرستیم.**

- 2->Ehternet
- 3->IP
- 4->TCP
_______________________________
### $\color{#25678D}{\textsf{Variable}}$
معمولا وقتی می خوان استفاده کنن از تعریف متغییرها استفاده می کنن.

`>>> L2=Ether()`

`>>>L2.show()`

لایه ی 2 برابره با یه پکت ethernet

`>>> L3=IP()`

`>>> L4=TCP()`

می تونیم آیتم هایی که با دستور show برای هر متغییر نشون میده رو عوض کنیم.

`>>> L2.src="08:35:HF:89:c4:d2"`

`>>> L2.show()`

می تونیم بسته ای که ساختیم رو ارسال کنیم.

`>>> sendp(L2/L3/L4)`

همزمان که packet هارو می فرستیم می تونیم **sniff** هم بکنیم -> استفاده از wireshark
_____________________
### $\color{#25678D}{\textsf{sniff}}$

`>>> sniff(iface="eth0", prn=lambda x:x.show())`

روی interface = eth0 گوش بده.

- **lambda** -> فانکشنی که همینجا مستقیما می نویسیسمش

حالا هر پکتی سمت eth0 بیاد نشون داده میشه.


می تونیم فیلتر بهش بدیم.

`>>> a=sniff(filter="src 192.168.0.113", count=10`)

`>>> a.nsummary()`

وقتی source=192.168.0113 است و فقط 10 تا packet بگیر.



و بعد خروجی رو هرچی بود نشون بده.
