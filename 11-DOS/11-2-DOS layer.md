$\color{#b91646}{\textsf{DOS layer}}$
======================================

- **Fragmentation (server can not rebuild packets). L4**
- **TCP-STATE exhausting (just sending SYN!)**
- **UDP flooding (forcing a lot of destination unreachable ansewrs). L4**
- **DNS, NTP, SSDP, SNMP, …**
- **ICMP (hping flood, ping of death (large))**
- **SMURF (reverse ICMP flood)**
- **Fraggle (SMURF with UDP)**
- **LAND (send traffic to traget with its own source! :) )**
- **PDoS (permanent DoS). Phlashing (updating firmwares -> bricking)**
- **Using Social media and ask people to attack using LOIC or JS LOIC**
- **Application layer (say requesting large searches)**
- **Volumetric (too much request)**
- **Buffer Overflow**

یعنی یه کاری بکنی که سرویس قطع بشه (می تونی هر کاری بکنی که سرویس قطع بشه، توی 7 لایه ی شبکه ای)

مجموعه ی زیادی از حمله ها در لایه ی 4 (UDP, TCP) اتفاق می افتن.

مثلا در fragmentation -> پکت های TCP با شماره سریال ارسال می شدن. مهاجم پکت شماره 104,105,106 رو می فرسته و بعد 121,122 رو می فرسته.

سرور که داره پکت هارو می گیره، پکت هارو می چینه کنار هم که فایل رو کامل کنه -> سرورپکت های 121 و 122 رو نگه میداره و منتظر پکت های 107 تا 120 می مونه. در نهایت فکر می کنه این پکت ها گم شدن.

در نتیجه سرور مشغول نگه داشته می شه.
