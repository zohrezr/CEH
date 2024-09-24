$\color{#b91646}{\textsf{Netbios}}$
=======================================

از پروتکل ها می تونیم اطلاعات زیادی بگیریم.

- **Very old and still present as netbios over tcp**

یک پروتکل قدیمی است و قبل از TCP بوده.

اگر میریم سراغ پروتکل NetBIOS در واقع باید بریم سراغ NetBIOS over TCP
______________________
- **Info like Computers, shares, services**

یه API بود که اجازه میداد برنامه هایی که توی کامپیوترهای مختلف هستن، باهم ارتباط برقرار کنن.

احتمالا اگه ازش بپرسی کیو می شناسی اطلاعاتی در مورد Computerها، shareها و serviceها بهمون میده.
_______________________
- **You can check with nmap for netbios**
  - 139/138 TCP
  - 137 UDP

___________________________
- **On windows you can test with “nbtstat”**
  - -a for netbios name -> با فلان ماشین کار دارم
  - -A for ip -> با فلان آی پی کار دارم
  - -c show cache

  `nbtstat -A 127.0.0.1`
_______________________
- **Suffix Codes are in netbios and netbios over tcp/ip on wiki**

خروجی یکسری کد میده. که هر کد یه معنی داره.

- For unique names:
  - 00: Workstation Service (workstation name)
  - 03: Windows Messenger service
  - 06: Remote Access Service
  - 20: File Service (also called Host Record)
  - 21: Remote Access Service client
  - 1B: Domain Master Browser – Primary Domain Controller for a domain
  - 1D: Master Browser

- For group names:
  - 00: Workstation Service (workgroup/domain name)
  - 1C: Domain Controllers for a domain (group record with up to 25 IP addresses)
  - 1E: Browser Service Elections
_______________________
- **On windows `net view \\192.168.1.13` will show shares. This will connect with a specific NULL session**

با این دستور می تونیم shareهای روی این سیستم رو ببینیم.
______________
- **GUIs like “netbios  enumeration” on sourceforge or “superscan”**
