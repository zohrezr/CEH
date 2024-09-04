$\color{#b91646}{\textsf{DNS}}$
=======================================

توی یه سازمان اگر DNS پیدا کنیم می تونیم از طریق zone transfer دیتای مربوط به domain و subdomain هارو به دست بیاریم.

- **Port 53**
_____________
- **“DNS Zone transfer” sends DNS info from one server to another server; to have HA**



شما وقتی dns server داری نیاز دارین برای اینکه HA داشته باشین یه کپی از DNS داشته باشین -> دوتا سرور داریم که یه دیتا دارن و هرکدوم از سرورها بودن جواب میدن.

برای اینکه بتونیم دیتای یک DNS server رو به یه سرور دیگه منتقل کنیم نیاز به یه query داریم -> `axfr` که به شما اجازه میده که کل دیتای یک zone رو بگیرین و zone transfer کنیم.

مثلا کل DNS info سایت jadi.net رو درخواست کنی و بگی می خوام اینو کپی کنم روی ماشین خودم.

تاثیر در هک -> اگر بتونی DNS server یک سازمان رو پیدا کنی، تمام subdomain های سازمان رو می تونی از این روش پیدا کنی.
___________________
- **Win & Linux: nslookup**

  `\> server ns.server.com`
  
  `\> type=any`
  
  `\> ls -d server.com` -> سروری که می خوام دیتاشو بگیرم

________________________________
- **Linux: dig**

  `dig server.com axfr`

  `dig jadi.net`

  `dig ns zonetransfer.me`

  `dig axfr zonetransfer.me @<name server>`

در اینجا name server می شه خروجی دستور dig ns

