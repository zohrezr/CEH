$\color{#b91646}{\textsf{ARP poisoning or spoofing}}$
======================================================

### $\color{#25678D}{\textsf{Address Resolution Protocol}}$


- **Request will broadcast its MAC+IP toward 00MAC+IP. Everyone will check and if its their IP, they will respond with their MAC+IP**


فرض کنید به سادگی یه جدولی است که می گه هر IP چه MAC ای رو داره.

با دستور `arp` می تونیم جدول arp رو ببینیم.

یه کامپیوتر یه packet رو می فرسته توی شبکه و broadcast می شه و می گه کی این IP رو داره و یه MACای اعلام می کنه این دست منه.

کامپیوترها از arp استفاده می کنن که بتونن توی شبکه هاشون MAC رو به IP وصل کنن.

توی wirshark می تونیم arp رو فیلتر کنیم و packetهاشو ببینیم. -> با یه دستور ساده مثل ping هم می شه دید.

- **Gratuitous ARP is like tipping or proxy arp. Just a packets saying “this is my MAC + IP”**

توی یه حالت خاصی یه مشکلی داریم -> فرض کنید یه IP رو به یه MAC وصل کردیم.

حالا فرض کنید این سیستم یه سرور بوده که می خوایم ببریمش روی یه ماشین دیگه -> یعنی IP رو بردیم روی یه ماشین دیگه در نتیجه MAC عوض می شه ولی همه  توی arp دارن که این IP برای این MAC (آدرس MAC قبلی)

این مشکل رو با ***Gratuitous ARP***  حل می کنن که یه ARP packet خاص است که اطلاع میده IP من اومده روی MAC آدرس جدید در نتیجه arp table ها عوض می شن.


____________________
### $\color{#25678D}{\textsf{Tools}}$

- **Tools like Ettercap, Cain & Abel & arpspoof**

__________________________
### $\color{#25678D}{\textsf{Attack}}$

- **Attacker will send gratuitous to router with its MAC and target IP. And another one to the target, telling it its MAC as routers IP.**
- **We can also do a Mac Spoof! Become someone else**
- **arpspoof -i eth0 -t target -r default_gw**


با ابزار arpspoof حمله رو انجام میدیم.

هر packet ای که می خواد توی هر شبکه بره توی شبکه ی دیگه (مثلا اینترنت) از getway رد می شه.

مهاجم با arpsoof می خواد به کامپیوتر خودش بگه یه packet بفرسته برای بقیه که mac خودشو به عنوان getway معرفی کنه (یعنی بگیم getway MAC عوض شده).

در واقع یه دونه gratuitous به کامپیوترهای توی شبکه ی خودمون می فرستیم و می گیم getway MAC عوض شده. (MAC مهاجم به عنوان getway در نظر گرفته می شه)

تا الان packet هایی که میان سمت مهاجم هیچ اتفاقی نمی افته -> کافیه routing هم انجام بدن (یعنی به OS بگیم هر packet ای که اومد سمتت و مال خودت نبود رو بده به defaultgetway (همون getway اصلی).

مهاجم خودشو میذاره بین ارتباط کامپیوترها با getway اصلی.

با این دستور IP route کل شبکه رو داریم.

`root@kali:~# ip route` -> 192.168.0.254

می خوایم getway MAC رو به عنوان Attacker MAC معرفی کنیم.

- عملیات routing 

در حالت عادی لینوکس به دلایل امنیتی به عنوان router کار نمی کنه.

برای اینکه لینوکس به عنوان router کار کنه از دستور زیر استفاده می کنیم.

اگر محتوای فایل 0 باشه یعنی لینوکس به عنوان router کار نمی کنه ولی اگر 1 باشه یعنی لینوکس به عنوان router است.

`root@kali:~# echo 1 > /proc/sys/net/ipv4/ip_forward`

`arpspoof -i eth0 -t 192.168.0.116 -r 192.168.0.254`

می گیم روی کارت شبکه eth0 سیستم من spoof کن.

با سوئیج t- هدف (target) رو مشخص می کنیم و می گیم packet رو بفرست به 192.168.0.116 

با سوئیچ **r-** باید getway رو معرفی کنیم.


__________________________________________
### $\color{#25678D}{\textsf{Defence}}$

**ARP inspection. Header to payload verification. Will check the IP and MAC with what it learned on Port from DHCP or ARP ACL (static list). This should run on untrusted ports.**


برای جلوگیری از این حمله از **ARP inspection** استفاده می کنیم. -> یعنی چک کنیم آیا header یا payload ای که داره توی اون packet میره درسته یا نه.

اگر کامپیوتری مدعی شده این IP با این MAC عوض شده. آیا واقعا همون IP است یا دارم از یه IP دیگه خبر میدم.

یه جاهایی **ARP ACL** داریم. یعنی access list هایی هست که ارتباطات رو ازش می پرسین. مثلا خودشو با DHCP هماهنگ کرده.

می تونیم توی سوئیچ untrusted port هارو هم مشخص کنیم که یعنی از این port ها اجازه نداریم packet رد کنیم.
