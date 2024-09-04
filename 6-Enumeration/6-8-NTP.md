$\color{#b91646}{\textsf{NTP}}$
=======================================

- **Network Time Protocol (NTP)**

یک کامپیوتر بتونه از شبکه یه ساعت خیلی دقیق رو بخونه و روی خودش set کنه.
________________
- **UDP 123**
_______________
- **Works like a chain of clocks and gives all machines same time**

می تونه مثل یک chain عمل کنه -> یک NTP server توی شبکه داشته باشی و کامپیوترها تایمشونو با اون set کن و خود NTP server با یه NTP server بزرگتری set شده باشه.

____________________
- **Time is important for DBs, logs, certs, …**


در TLS بکسری certificate داریم که زمان واسشون مهمه.

خیلی از database ها و log ها زمان واسشون مهمه.

دوتا سروری که دارن باهم snik می شن زمان واسشون مهمه.
____________________
- **Older versions of NTP will provide you the IP of its clients**

در ورژن های قدیمی تر NTP server یک function داشت به اسم **monlist** که می تونست لیست گلاینت هایی که دارن با این سرور زمان خودشونو set می کنن، مانیتور کنه. -> خیلی جاها کار نمی کنه.

_________________
- **ntpdc (cli, help, monlist)**

می تونیم با ntpdc کار کنیم که cli برای NTP است.

دستور help داره.

مستقیما دستور monolist داره.
_______________
- **ntpdate**

دستور ntpdate وصل می شه به یه NTP server 

  `ntpdate pool.ntp.org`
  
ساعت رو set می کنه.

  `ntpdate -q pool.ntp.org`

ساعت رو set نمی کنه فقط query می کنه و می گه ساعت چند است.
______________
- **nmap**

همون ریکوستی که با ntpdate زدیم می تونیم با nmap بزنیم.

`nmap -sU -pU:123 --script=ntp-monlist 192.168.1.13` 

بگرد دنبال port های UDP باز و UDP port:123 رو پیدا کن و این script رو براش run کن.

- -sU -> check UDP packet
- -pU -> check UDP port (default port 123)
- --script=ntp-monlist

خوده nmap یکسری script هم می تونه run کنه.

(check on nmap manual site)
