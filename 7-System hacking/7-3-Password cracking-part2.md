$\color{#b91646}{\textsf{Password cracking}}$
=============================================

## $\color{#105652}{\textsf{Passive Online Attacks}}$


### $\color{#25678D}{\textsf{Packet sniffing (Sniffer, packet analyzer)}}$

- **Happens in one collision domain, unless you do spoofing (later)**
- **Telnet, FTP, SMTP, rlogin, SNMPv1**

توی packet sniffing وسط یک ارتباط قرار می گیرم و به چیزایی که رد و بدل می شه گوش میدم و دیتایی که می خوام رو برمیدارم.

**رنج IP**

منطقا باید توی یک collision domain باشی. -> باید توی یک رنج IP باشیم. Network IP و Network mask باید مشابه باشه که بتونید دیتارو ببینید.

تکنیک هایی مثل spoofing، مشکل لزوم توی یک شبکه بودن رو تا حدودی حل می کنه.

**ابزارها**

در sniffing ابزارهای معروف tcpdump و wireshark هستن.

عملا wireshark یه رابط گرافیکی روی tcpdump است.

ابزار tcpdump پکت هارو جمع می کنه و wireshark نشون میده.

در محیط های گرافیکی چون خوده wireshark ابزار tcpdump رو داره ما فقط wireshark رو استفاده می کنیم.

توی سرور چون معمولا رابط گرافیکی نداری tcpdump اجرا می کنی و خروجی رو میبری توی wireshark نشون میدی.

نرم افزارهای packet analyzer رو هم داریم مثل همون wireshark.

**پروتکل ها**

یکسری پروتکل ها برای sniffing خیلی راه دست هستن -> Telnet, FTP, SMTP, rlogin, SNMPv1 => دیتارو به صورت **clear text** رد می کنه.
___________________

### $\color{#25678D}{\textsf{Man In the Middle Attack}}$

- **Burp Suite**
- **Browser Exploitation Framework (BeEF)**
- **SSL Strip, mitmproxy**

________________________
### $\color{#25678D}{\textsf{Replay Attack}}$
