$\color{#b91646}{\textsf{TCPdump wireshark}}$
=============================================

### $\color{#25678D}{\textsf{ُSniffing tools}}$

- **wireshark**
- **tcpdump**
- **windump**
- **omnipeek**
- **Dsniff**
- **etherape**
- **msn sniffer**
- **…**

_____________________________________________
### $\color{#25678D}{\textsf{Filters}}$

- **==, eq, !=, ne, contains**
- **ip.addr, tcp.port, ip.src, http contains** 

دو مدل فیلتر مختلف داریم: -> **cpature filter** و **display filter**

وقتی می گیم capture filter فقط اون packet هایی که می خوایم رو capture می کنه ولی وقتی می گیم display filter، مواردی که می خوایم رو نمایش میده.

در **wireshark** هم استفاده می شود.
______________
### $\color{#25678D}{\textsf{TCPdump command}}$

`root@kali:~# man tcpdump`

راهنمای tcpdump

`root@kali:~# tcpdump`

هرچی dump ببینه نشون میده. (هرچی از شبکه رد بشه) -> display

`root@kali:~# tcpdump dst 4.2.2.4`

هرچیزی که 4.2.2.4 مقصدش بود نشون بده. -> display

`root@kali:~#tcpdump -w output.pcap`

معمولا خروجی رو توی یه فایل ذخیره می کنن.-> capture

_________________
### $\color{#25678D}{\textsf{CLI Tools}}$

یکسری مجموعه ابزار داریم در Dsniff
- **tshark (cli version)**
- **dumpcap (capturing)**
- **capinfos (stats about a capture)** -> `root@kali:~# capinfos output.pcap`
- **editcap (edit or translate format of capture)**
- **mergecap (combines captures)**
- **text2cap (cap from hex dump of packets)**

_______________________
### $\color{#25678D}{\textsf{wireshark command}}$

`root@kali:~# wireshark output.pcap`

می تونیم اول tcpdump بگیریم خروجی رو توی wireshark نشون بدیم.

می تونیم مستقیم از توی wireshark بسته هارو بگیریم و بعد بررسی کنیم.
