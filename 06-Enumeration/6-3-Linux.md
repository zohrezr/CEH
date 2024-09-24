$\color{#b91646}{\textsf{Linux}}$
=======================================

### $\color{#25678D}{\textsf{Users}}$

یکسری default username داریم و یکسری default file داریم که شامل اطلاعات userهاست.

- **/etc/passwd** -> username file
- **/etc/shadow** -> hash password file
________________________
### $\color{#25678D}{\textsf{Groups}}$

یکسری default group داریم و یکسری default file داریم که شامل اطلاعات groupهاست.

- **/etc/group** -> group file

_______________________
### $\color{#25678D}{\textsf{Services and Ports}}$

سرویس هایی هستن که در مورد enumeration می تونن به شما دیتا بدن.

- **TCP 21-FTP**
- **TCP 23-Telnet**
- **TCP 25-SMTP**
- **TCP 53-DNS**
- **TCP 80-HTTP**
- **TCP 135-RPC**
- **TCP 137-NetBIOS**
- **TCP 139-NetBIOS**
- **TCP 445-SMB over TCP**
- **UDP 161 and 162-SNMP**
- **TCP/UDP 389-LDAP**
- **TCP/UDP 3268-Global Catalog Service**

________________________
### $\color{#25678D}{\textsf{Everything is file}}$

هر چیزی توی دنیای لینوکس یا **file** است یا **process** -> هر دیتایی باشه باید بتونیم توی فایل توی سیستم پیدا کنیم.

______________________
### $\color{#25678D}{\textsf{Various commands like}}$

- **finger**
- **rcpinfo** 
- **showmount**
- **Enum4linux (uses samba)** -> is program
