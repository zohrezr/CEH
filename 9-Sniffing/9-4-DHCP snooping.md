$\color{#b91646}{\textsf{DHCP snooping}}$
=========================================

یک روش برای sniffing است.

### $\color{#25678D}{\textsf{DHCP}}$

- **Discover**
- **Offer**
- **Request**
- **Acknowledge**

همون لحظه ای که یه کامپیوتر وصل می شه به یه شبکه، نیاز به یک IP داره. -> باید IP بگیره

از یکی از port های کامپیوتر یه کابل به port سوئیچ وصل می کنیم. یا اینکه با wifi وصل می شم به شبکه.

برای اینکه بتونه IP بگیره باید یه **Discover packet** بفرسته به همه و اعلام کنه IP می خواد.

توی شبکه DHCP پاسخ میده و یک IP رو به کامپیوتر **offer** میده.

کامپیوتر **request** میده که من این IP ای که پیشنهاد دادی رو برمیدارم.

و بعد DHCP درخواست رو **Acknowledge** می کنه که باشه تو بردار.

______________________
### $\color{#25678D}{\textsf{mistake}}$

**This can happen by mistake or by a plan!**

یه اشتباهی که ممکنه پیش بیاد اینه که من یه DHCP server روی کامپیوتر خودم اجرا می کنم و بعد خودمو وصل می کنم به شبکه.

حالا ممکنه یکی دیگه که توی همین شبکه است به من به عنوان DHCP server وصل بشه و از من IP بگیره.

در نتیجه شبکه بهم میریزه.

_______________
### $\color{#25678D}{\textsf{Attack}}$


- **First we will do DHCP starvation attack**
- **Then our DHCP server can also work as a router**
- **Sniffing, MITM, …**

شبکه خودش یه DHCP server داره.

هکر هم با لپ تاپش وصل شده به شبکه و یه DHCP خودش run می کنه. در نتیجه DHCP اصلی و DHCP هکر دچار اختلال می شن.

هکر یک (starvation)DHCP flood اجرا می کنه.

توی شبکه فرض کنید DHCP اصلی کلا می تونه 255 تا IP بده، هکر 255 تا ریکوست سمتش می فرسته. یعنی 255 تا Discover packet می فرسته.

و DHCP اصلی هم 255 تا Offer میده ولی دیگه هکر ادامه ی مراحل رو نمیره تا همینجا نگه میداره و DHCP خودشو اجرا می کنه.

توی این لحظه اگر یکی درخواست IP بده، DHCP اصلی نمی تونه بهش جواب بده (چون IP نداره)

درخواست Discover توسط یه کامپیوتری توی شبکه فرستاده شده، هکر به عنوان DHCP بهش جواب میده. و یه subnet توی رنج خودش میده و بعد خودشو به عنوان getway معرفی می کنه که اون کامپیوتره هر routای داشت بفرسته واسه هکر.

در نتیجه تمام دیتا از هکر رد می شه و می تونه sniff کنه

On wireshark you can see this by filtering for “bootp”
Defence? Switch untrusted ports can have DHCP server type messages on NO, just like a firewall. 

	
![Uploading image.png…]()
