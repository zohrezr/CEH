$\color{#b91646}{\textsf{TCPdump wireshark}}$
=============================================

### $\color{#25678D}{\textsf{ُSniffing tools}}$

- **wireshark**
- **tcpdump**
- **windump**
- **omnipeek**
- **dsniff**
- **etherape**
- **msn sniffer**
- **…**

_____________________________________________
filters:

- ==, eq, !=, ne, contains
- ip.addr, tcp.port, ip.src, http contains

دو مدل فیلتر مختلف داریم: -> cpature filter و display filter

وقتی می گیم capture filter فقط اون packet هایی که می خوایم رو capture می کنه ولی وقتی می گیم display filter، مواردی که می خوایم رو نمایش میده.


______________

`root@kali:~# tcpdump`

هرچی dump ببینه نشون میده. (هرچی از شبکه رد بشه)

`root@kali:~# tcpdump dst 4.2.2.4`

هرچیزی که 4.2.2.4 مقصدش بود نشون بده.

`root@kali:~#tcpdump -w output.pcap`

معمولا خروجی رو توی یه فایل ذخیره می کنن.

_________________
CLI Tools
- tshark (cli version)
- dumpcap (capturing)
- capinfos (stats about a capture)
- editcap (edit or translate format of capture)
- mergecap (combines captures)
- text2cap (cap from hex dump of packets)

