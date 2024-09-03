$\color{#b91646}{\textsf{nmap}}$
=============================================

**توی شبکه ایم و می خوایم ببینیم چه کامپیوترهایی توی اون شبکه هستن.**

### $\color{#25678D}{\textsf{sweep network (-sn)}}$

همه ی نتورک رو بررسی می کنه و فقط می گه چه host هایی بالاست.
_____________
### $\color{#25678D}{\textsf{Full Open Scan (-sT)}}$

دقیقا 3way hand shake رو انجام میده و می بینه بازه یا نه.
__________________
### $\color{#25678D}{\textsf{Stealth, Syn or half Open scan (-sS)}}$

می تونه یه جور scan ای باشه که خیلی خوب دیده نمی شه.

درخواست SYN رو بدیم، اون که جواب داد دیگه وصل نشیم. -> چون اگر جواب داد یعنی port بازه.
________________
### $\color{#25678D}{\textsf{Xmas Scan (-sX, FIN + URG + PSH)}}$

- **Older systems: No response means port is open**
- **RST shows close**

همه ی بیت هارو روشن می کنه. -> پکت غیرعادی

توی سیستم های مختلف فرق می کنه و خیلی چیز مطمئنی نیست.
_______________
### $\color{#25678D}{\textsf{Fin scan (-sF, like Xmas, passes firewalls)}}$

پکت FIN می فرسته فقط. -> پکت غیرعادی

معمولا از firewall رد می شه ولی stateful firewall ها ممکنه بگیرنشون.

وابسته به عملکرد firewall ها.
____________________
### $\color{#25678D}{\textsf{Fin scan (Null Scan (-sN, like Fin but no flag is set))}}$

هیچ کدوم از بیت هارو روشن (1) نمی کنه. -> پکت های غیرعادی هستن.

اگر نباشن ممکنه RST بگیرن.

وابسته به عملکرد firewall است.
_____________________
### $\color{#25678D}{\textsf{Fin scan (ACK scan (sends ACK, this wont pass stateful firewalls))}}$

فقط یه دونه ACK می فرستیم. -> پکت غیرعادی

وابسته به عملکرد firewall است.
___________________
### $\color{#25678D}{\textsf{UDP is different}}$

- **if the port is open you wont get any response, if closed ICMP “Port Unreachable” message returned**

توی UDP، پکت ها خیلی ساده ترن -> مثلا توی ارسال ویدیو که به صورت stream است کاربرد دارن.

در UDP مفهوم response وجود نداره.

مثلا توی اسکن می تونیم یه پکت بفرستیم به این صورت که اگر open باشه هیچ جوابی نمی گیریم ولی اگر close باشه یه ICMP مثل ping واستون می فرسته که می زنه port is unreacheable. یعنی UDP بسته بود.

__________________
### $\color{#25678D}{\textsf{Idle scan (lets see this one in depth!)}}$

پارت بعدی.
