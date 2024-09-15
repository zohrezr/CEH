$\color{#b91646}{\textsf{CAM table and Port security}}$
========================================================

### $\color{#25678D}{\textsf{MAC Table}}$
سوئیچ لازم داره که یه جایی نگهداره که هر MAC address کجاست. -> در MAC table نگهداری می شه.

طبق اون جدول کامپیوترها باهم ارتباط برقرار می کنن. -> این جدول سایزش محدوده.

____________________
### $\color{#25678D}{\textsf{macof}}$

**macof utility from dsniff**

`#root@kali:~# macof -i eth0` **-> will overflow the mac and the next packets would be sent to all ports to work!**

ابزار macof می تونه mac table رو flood کنه.

اندازه ی cam table محدوده. مهاجم چند هزار ریکوئست الکی می زنه بهش و یکسری mac رو به یکسری port و سوئیچ اختصاص بدم. در نتیجه cam table پر می شه. و موارد اصلی از جدول خارج می شن.

وقتی cam table پر بشه، یکی از mac ها بگه با یه mac دیگه کار دارم ->  بعضی از سوئیچ های قدیمی مثل hub کار می کنن. به تمام port ها می فرستن به امید اینکه به اونی که باید برسه. 


___________________
### $\color{#25678D}{\textsf{port security}}$

راه حل جلوگیری از flood

- **If we turn on port security on a port, this will be resolved. There are some steps when we get MAC address beyond our limit (say 5):**
  - **P: protect**
  - **R: protect + sending alerts and messages (syslog, counter, snmp, ..)**
  - **S [ default] : shutdown the port** 
  - **S: shutdown the whole vlan**

در سوئیچ ها port ها می تونن trusted باشن می تونن untrusted باشن.

انتظار میره port security رو روشن کرده باشم که به 4 روش می تونه به اتفاقات unsecure جواب بده. -> PRSS

حالت **Protect** یعنی مثلا port:1 که port security روشن است، بیشتر از 5 تا MAC address قبول نمی کنم که بیاد. MAC ششم که اومد protect می کنه و قبول نمی کنه.

حالت **Protect+sending alerts and messages** -> یعنی اگر MAC ششم از سمت port:1 معرفی شد یه alert توی لاگ سوئیچ ذخیره می شه که port:1 شش تا MAC فرستاده.

حالت **default** -> به صورت پیش فرض روی این حالت تنظیمه و port رو کلا shutdown می کنه. (جالب نیست)

حالت **shutdown the whole vlan** -> در این حالت کل vlan رو shutdown می کنه. (جالب نیست، وحشیانه اس)

___________________
### $\color{#25678D}{\textsf{config port security}}$

**To turn on port security you will go to the switch and in config mode, will do a `switchport port-security maximum 5` on that port and `switchport port-security violation restrict` and enable the feature `switchport port-security`  and check with `show port-security`**
