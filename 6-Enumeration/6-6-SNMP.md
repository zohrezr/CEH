$\color{#b91646}{\textsf{SNMP}}$
=======================================

- **Cocept**
  - Simple Network Management
  - Port 161 UDP
  - Community string is like password
  - Versions 1, 2, 3

پروتکل SNMP مثل یک درخت می مونه.

مثلا حرارت cpu رو به صورت 1.3.4.7.2.76.2.45 نشون میده. -> OID

مفهوم Community string در واقع همون password است. اگر من یه network device دارم یه Community string به صورت public میذارم که هرکی گف public بهش جواب بدم.

خیلی از network deviceها پروتکل SNMP رو می فهمن در نتیجه می تونی یه برنامه نصب کنی روی سیستمت و به deviceها وصل بشه و دیتای snmp رو بخونه

______________________
- **On windows `snmputil.exe`**
  - get -> یه دونه ای که بهش میدی رو می خونه
  - getnext
  - Walk -> زیرشاخه رو کامل می خونه

_______________
- **SNScan (from McAfee, also checks network)**

یه برنامه اس اگر نصبش کنی کل شبکه رو چک می کنه اونایی که snmp هست رو درمیاره و walk می کنه.

___________________
- **IP Network Browser (Solarwinds)**

یه برنامه اس
______________
- **metaspolit also has SNMP**
  - search snmp & we will use snmp_enum
  - use auxiliary/scanner/snmp/snmp_enum
  - show options
  - set RHOSTS 192.168.1.13
  - run

یک ابزار در کالی

`msf5 > search snmp`

می خوایم enumeration کنیم پس snmp enum رو انتخاب می کنیم. -> auxiliary/scanner/snmp/snmp_enum

`msf5 > use auxiliary/scanner/snmp/snmp_enum`

`msf5 auxiliary(scanner/snmp/snmp_enum) > help`

`msf5 auxiliary(scanner/snmp/snmp_enum) > show options`

`msf5 auxiliary(scanner/snmp/snmp_enum) > set RHOSTS demo.snmplabs.com`

`msf5 auxiliary(scanner/snmp/snmp_enum) > run`
________________
- **snmpwalk**

یک ابزار لینوکسی

`snmpwalk -v 1 -c public demo.snmplabs.com`

کلشو walk می کنه.

`snmpwalk -v 1 -c public demo.snmplabs.com .1.3.6.1.4.1.2021.10.1.3.1`

در یک دقیقه ی گذشته cpu load رو می گیره.

`snmpwalk -v 1 -c public demo.snmplabs.com .1.3.6.1.4.1.2021.10.1.3`

می گیم cpu load زیر 3 هرچی داری بده.


