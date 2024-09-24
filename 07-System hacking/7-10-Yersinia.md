$\color{#b91646}{\textsf{Yersinia}}$
====================================

## $\color{#105652}{\textsf{Yersinina}}$

یک ابزاری است برای DHCP Starvation 

### $\color{#25678D}{\textsf{ِDHCP}}$


کار DHCP اینه که به شما IP میده و به عنوان getway اون شبکه می تونه عمل کنه.

برای گرفتن IP از DHCP توسط کامپیوترهای یکسری request و response رد و بدل می شه.

توی network هر کامپیوتری که روشن می شه از DHCP server می خواد IP بگیره -> جذاب برای هکرها؟؟؟

________________________
### $\color{#25678D}{\textsf{ِHack the DHCP}}$

یه هکر می تونه DHCP server رو از رده خارج کنه و خودش بشه DHCP server و هر کامپیوتری که توی شبکه روشن سیستم هکر بهش IP میده و getway می شه.

کامپیوتر قربانی همه ی اطلاعاتشو برای هکر به عنوان DHCP و getway می فرسته و در نهایت هکر خودش اطلاعات رو به getway اصلی ارسال می کنه.

تمام ترافیک توسط مهاجم کنترل می شه. => **تمام Passive Attacks (sniif) ها اتفاق می افته**

__________________
### $\color{#25678D}{\textsf{ِDHCP Starvation}}$

**Used for DHCP Starvation Attack. We send too many Discovers and ips are exhausted.**

با حمله ی DHCP Starvation می خوایم DHCP اصلی رو از کار بندازیم.

هر کامپیوتری که IP می خواست، DHCP بهش IP میداد.

مهاجم یه کامپیوتر میاره بالا که الکی broadcast می فرسته با MAC address های مختلف و بگه من IP می خوام.

در این حالت DHCP هم IP هایی که داره رو بهش پیشنهاد میده و در نهایت IP های DHCP تموم می شه.

______________________
### $\color{#25678D}{\textsf{ِRun yersinia}}$

`root@kali~:# yersinia -G` -> graphic mode

`root@kali~:# yersinia` -> command line mode

** Try the DHCP tab and Launch the Attack and go for Send Discover. Now no one can use this DHCP anymore and you can run your own DHCP.**

_________________
### $\color{#25678D}{\textsf{ِDefenses}}$

**Defenses? Say on layer two (switch) you can turn the Port Security on.**

