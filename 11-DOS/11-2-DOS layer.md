$\color{#b91646}{\textsf{DOS layer}}$
======================================

### $\color{#25678D}{\textsf{Fragmentation}}$

- **Fragmentation (server can not rebuild packets). L4**

***لایه 4***

یعنی یه کاری بکنی که سرویس قطع بشه (می تونی هر کاری بکنی که سرویس قطع بشه، توی 7 لایه ی شبکه ای)

مجموعه ی زیادی از حمله ها در لایه ی 4 (UDP, TCP) اتفاق می افتن.

مثلا در fragmentation -> پکت های TCP با شماره سریال ارسال می شدن. مهاجم پکت شماره 104,105,106 رو می فرسته و بعد 121,122 رو می فرسته.

سرور که داره پکت هارو می گیره، پکت هارو می چینه کنار هم که فایل رو کامل کنه -> سرورپکت های 121 و 122 رو نگه میداره و منتظر پکت های 107 تا 120 می مونه. در نهایت فکر می کنه این پکت ها گم شدن.

در نتیجه سرور مشغول نگه داشته می شه.

______________________________
### $\color{#25678D}{\textsf{TCP-STATE exhausting}}$
- **TCP-STATE exhausting (just sending SYN!)**

***لایه 4***

خسته اش کنم. -> یه کاری کنم connection مشکل داشته باشه.

با توجه به TCP 3way handshake می تونیم کارهای غیرعادی کرد. 

مثلا مهاجم SYN بفرسته و سرور ACK جواب بده ولی دیگه مهاجم چیزی نفرسته. در نتیجه سرور یه مدتی connection رو باز نگه میداره تا مهاجم جواب بده.

یا الکی به سروری که اصلا وصل نشدم، یه دونه FIN بفرستم و بگم connection رو ببند، سرور هم RST می فرسته چون اصلا همچین connection ای نداشته.

اگر این کارهارو پشت سرهم توی مدت زمان کم انجام بدیم، سرور به مشکل می خوره.

_____________________
### $\color{#25678D}{\textsf{UDP flooding}}$
- **UDP flooding (forcing a lot of destination unreachable ansewrs). L4**

***لایه 4***

در UDP مهاجم دیتا می فرسته به یه Port، سرور دیتارو روی port دریافت می کنه و میده به برنامه ای که نیازش داره و مهاجم هیچ جوابی نمی گیره مپر اینکه به یه port بسته بفرسته  چون سرور جواب میده که این UDP port بسته است.

اگر تعداد پکت های زیادی رو در مدت زمان کمی به یه port بسته در UDP بفرستیم، سرور به مشکل می خوره.

_________________________
### $\color{#25678D}{\textsf{DNS, NTP, SSDP, SNMP, …}}$
- **DNS, NTP, SSDP, SNMP, …**

***لایه 7***

در لایه های دیگه هم می شه حمله انجام بدیم -> هر پروتکلی که داره اجرا می شه روی اون ها حمله انجام بدیم.

مثلا سوال های ساده بپرسیم -> به یک وب سرور بارها در مدت زمان کم بگیم صفحه ی اولتو به من بده.
__________________________
### $\color{#25678D}{\textsf{ICMP}}$
- **ICMP (hping flood, ping of death (large))**

پکت ICMP پکت ping است. -> یک پکت مخصوصی است که برای ping کردن سرورها استفاده می شه. -> port نداره (TCP و UDP هستن که port دارن)


حالت عادی پکت ICMP که میاد یک ICMP request است که یه جواب می گیره به اسم ICMP reply -> می گیم ping کار کرد. (هر یه دونه ping ای که می فرستیم این اتفاق می افته)

مهاجم می تونه پکت های ICMP چرت و پرت بفرسته.

ساده ترین کار اینه که در زمان کم پشت سرهم ICMP بفرستیم. (تا جایی که cpu توان داره) -> ***hping flood***


پکت ping در حالت عادی 56 بایت است ولی می تونه تا 65535 بایت هم بزرگ بشه. 

به صورت عادی همه ی سیستم عامل ها برنامه ای که نوشتن به صورت پیش فرض یه بافر درست می کنه، ping رو می ریزه اونجا و بهش جواب میده. ظرفیت بافر همیشه 64k در نظر گرفته شده.

اگر یه ping بزرگ درست کنیم که ظرفیتش بیشتر از 64k باشه می شه ***ping of death*** در نتیجه سیستم crash می کنه.

الان جلوشو گرفتن.
_______________
### $\color{#25678D}{\textsf{SMURF}}$
- **SMURF (reverse ICMP flood)**

فرض کنید یه سرور داریم که خودمون بهش ping می فرستیم و خسته اش می کنیم. -> می تونه مارو block کنه یا کارهای دیگه.

اگر botnet داشته باشیم و به همون سرور از جاهای مختلف ping بفرستیم و خسته اش کنیم، خیلی کار سرور سخت تر است.


می تونیم حمله ی SMURF کنیم.

وقتی ping می کنیم یه پکت request میره که src و dst مشخصه. و سرور طبق همین reply رو می فرسته به src

فرض کنید سرور هدذف 17 است، مهاجم 16 و یه سیستم دیگه داریم که 15 است.

مهاجم(16) یه پکت ICMP request درست می کنه که src=17 و dst=15 باشه.

این پکت می رسه به 15 و سیستم 15 طبق بسته فکر می کنه 17 بهش ping فرستاده، در نتیجه reply رو برای 17 می فرسته. (ممکنه 17 هم rst بفرسته)


حالا می تونیم به جای اینکه dst=15 بذاریم dst رو برابر broadcast IP بذاریم. هر کی به broadcast یه packet بفرسته، تمام کامپیوترهای شبکه می گیرنش.

پس مهاجم یه پکت ISMP request می فرست src=17 و dst=255(broadcast) در نتیجه همه ی کامپیوترهای شبکه می گیرنش پس همشون به 17 یه ICMP reply می فرستن.
_______________________
### $\color{#25678D}{\textsf{Fraggle}}$
- **Fraggle (SMURF with UDP)**

شبیه SMURF است ولی در واقع با UDP اتفاق می افته.

________________________
### $\color{#25678D}{\textsf{LAND}}$
- **LAND (send traffic to traget with its own source! :) )**

قدیمیه روی ویندوز xpsp2 و 2003 هنوز کار می کنه.

مهاجم (16) یه پکت میذاره توی شبکه که src=17 و dst=17 باشه و بخواد ازش که یه کار شبکه ای بکنه.

قربانی (17) پکت رو می گیره، بعد به خودش جواب میده و ... در نهایت می افته توی یه loop و سیستم عامل crash می کنه.

________________________
### $\color{#25678D}{\textsf{PDoS}}$
- **PDoS (permanent DoS). Phlashing (updating firmwares -> bricking)**

مثلا لگد به کامپیوتر بزنید و کامپیوتر بشکنه و backup هم نداشته باشن، چند روز طول می کشه سرویس بیاد بالا. -> ***PDoS***

یه روشی پیدا کنید که از راه دور بتونید firewar یه device رو update کنید یا عوض کنید و یه firewar چرتی روش بنویسید -> ***phlashing***

مثلا روتر یک شبکه ای رو از راه دور flash کنید.

___________________
### $\color{#25678D}{\textsf{Social media}}$
- **Using Social media and ask people to attack using LOIC or JS LOIC**

مثلا آدم ها از صدا و سیما شاکی هستن و همشون باهم می گن کامپیوترتونو باز کنید و همتون باهم صفحه ی صدا و سیما رو refersh کنید در نتیجه به سرور فشار میاد و اگر یکی واقعا بخواد صفحه ی صدا و سیما رو ببینه نمی تونه. -> ***refersh***

می تونیم از ***LOIC*** استفاده کنیم که یک برنامه اس که می تونه یک آدرسی بگیره و بهش حمله کنه. می تونیم توی social media به همه بگیم این کارو کنن (توی سایت sourceforge است)
_______________
### $\color{#25678D}{\textsf{Application layer}}$
- **Application layer (say requesting large searches)**

توی لایه ی 7 می تونیم انجام بدیم

مثلا ISP شما اجاره میده request بدین history کارتون مثلا مصرف پهنای باند در 6 ماه گذشته رو به صورت ریز نشون بده -> این خیلی کار بیشتری میبره از refersh کردن صفحه ی اول سایت.

اگر افراد این رو request بدن بهتره تا صفحه ی اول سایت.

یا مثلا یه جاهایی اجازه میده regex بزنیم توی سایت ها، اگر یه regex های چرتی مثل +[+a] بزنید، regex engin گیج می شه و چون سنگینه خیلی وقتا باعث می شه crash کنه.
______________________
### $\color{#25678D}{\textsf{Volumetric}}$
- **Volumetric (too much request)**


__________________
### $\color{#25678D}{\textsf{Buffer Overflow}}$
- **Buffer Overflow**


________________
