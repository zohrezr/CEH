$\color{#b91646}{\textsf{Introduction}}$
=============================================

- **Wiretapping on network**

شنود گذاشتن روی شبکه

- **How**
  - Passive
  - Active
  - we have to be in Promiscuous mode to read all FRAMES (layer 2) and won't filter only for our own MAC. “ifconfig -a” will show if we are in promiscuous mode
  - MAC flooding (send too many to overflow the CAM)
  - DHCP attacks
  - ARP Poisoning 
  - DNS Poisoning
  - Spanning on switch

در حالت **passive** -> یعنی فقط می شینی و گوش میدی (شنود می کنی)

در حالت **active** -> شبیه سانسور کردن است. DPI داریم. هر packet ای رو می تونه نگاه کنه و اگر خوشش نیومد می تونه تغییرش بده یا حذفش کنه و ...

اصطلاح **promiscuous** -> یعنی بی بند و بار. کارت شبکه می تونه بره توی این وضع

در مکانیزم های قدیمی تر که hub داشتیم و هر یکسری port داشتیم برای هر PC. هر PC که می خواست با یکی صحبت کنه packet رو توی کل شبکه می فرستاد و به دست همه می رسید.

امروزه با استفاده از سوئیچ بسته ها طبق MAC و IP بین کامپیوترها رد و بدل می شه و هر PC فقط بسته های مربوط به خودشو می گیره.

اگر کارت شبکه توی promiscuous mode باشه، تمام packet ها مستقل از اینکه واسه کیه رو می بینه -> معمولا کسایی که می خوان hack کنن کارت شبکه ای رو می خرن که توی این mode کار کنه. -> تمام فریم های لایه 2 ای رو می خونه -> نگاه نمی کنه هر چی مربوط به خودشه رو بخونه، هرچی از کارت شبکه رد می شه رو نگاه می کنه.

توی سوئیچ ها بسته ها با توجه به mac فقط به مقصد می رسن و بقیه نمی تونن بسته رو ببینن در نتیجه sniff کردن در شبکه به مشکل می خوره. -> برای حل این مشکل حمله ی **MAC flooding** استفاده می شه. -> یه عالمه ریکوست MAC به سوئیچ می زنید در نتیجه MAC table قطع می شه و مشکل عدم sniff حل می شه. -> مجبوره همه چیزو به همه بفرسته تا مقصد اصلی دریافت کنه.

حمله ی **spanning on switch** -> یعنی روی روتر به هر دلیلی Port:14 آینه (mirror/span) port:12 باشه 

- **HTTP, Telnet, email, ftp, rlogin, POP, IMAP, …**

هر packet که رمزنگاری شده باشه خیلی وضعش بهتره -> می تونی ببینیش ولی نمی دونی توش چیه.

پروتکل ها اگر رمزنگاری نشده باشن در برابر sniffing بسیار ضعیفن.

- **Software (snort, winpcap, wireshark, tcpdump,...) vs Hardware (protocol analyzer)**

- **Detection**
  - Finding promiscuous interfaces using a ping to unknown IP & MAC and seeing answers or using NMAP
