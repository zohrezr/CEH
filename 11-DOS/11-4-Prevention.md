$\color{#b91646}{\textsf{Prevention}}$
======================================

## $\color{#105652}{\textsf{Tools}}$

### $\color{#25678D}{\textsf{Reduce Attack Surface}}$


مساحت حمله رو کم کنید.

اگر روی سرور نیاز نیست پورت NTP باز باشه و به بقیه گوش بده، حذفش کنید.

هر سرویسی روش هست که مورد استفاده نیست حذفش کنید.

وب سایت روی CDN نگهداری بشه بهتره.
__________________
### $\color{#25678D}{\textsf{Search for DDoS runbook checklist}}$


می تونیم در مورد DDoS runbook checklist ها جستجو کنیم.

بهمون می گه در برابر حمله های DoS و DDoS چه کارهایی انجام بدیم. -> در برابر چه چیزهایی باید مقاوم باشیم.


___________
### $\color{#25678D}{\textsf{NOP is 0x90}}$


کد هگز No Operation در برنامه نویسی هگز 0x90 است.

_______________
### $\color{#25678D}{\textsf{UTM/IPS}}$

**UTM/IPS can have reputation based filtering**

اابزارهایی هستن به اسم ***UTM(Unify Threat Management)*** -> یه device است که می خری میذاری سر راه شبکه و خیلی چیزا رو بلده.

مثلا می دونه که اگر پکت FIN داره میاد و شما به سرور وصل نیستین پس پکت چرتیه اصلا به سرور تحویلش نمیده.

یا مثلا اگر string ای داره رد می شه و انگا داره sql injection می کنه پس نمیذاره رد شه.

وقتی لایسنس UTM هم می خری خودشون update هم می شن.

همچنین ***IPS (Intrusion Prevention System)*** هم به همین صورت هستن. 

حتی reputation based filtering دارن. 

حتی IP هایی رو می شناسن که spammer هستن، یا IP ها یه کار ضایعی می کنن در نتیجه از این IP ها که request میاد جوابشو نمیده.


___________________
### $\color{#25678D}{\textsf{Rate limiting / Throttling}}$

مثلا اگر یک apache web server دارم بهش می گم به هر IP بیشتر از 10 تا connection اجازه نده باز کنه -> مقداری جوابی که سرور میده محدود می شه.

____________________
### $\color{#25678D}{\textsf{Reverse Proxy}}$

مثلا اگر یه apche server داریم قبلش یه nginx بذاریم و بگیم همه ی connection ها بیان به nginx و بعد ngnix از apache بپرسه و جواب بده.

تنظیماتی که می گیم از یه IP بیشتر از 10 تا request نیاد، اگر connection بیشتر از 10 ثانیه باز موند قطعش کنه، cache کنه و ... رو به ngnix میدیم.

در این حالت ngnix نقش revese proxy رو بازی می کنه.

فشاری هم بیاد روی ngnix است.

______________________
### $\color{#25678D}{\textsf{TCP Intercept}}$
**TCP Intercept. Firewall can reply to SYN and forward to server when there is a valid connection**

گوش کردن به TCP ها.

فایروال ها خیلی وقتا می تونن نگاه کنن که توی TCP داره چه اتفاقی می افته و مشکل رو حل کنن.

مثلا اگر پکت FIN اومد که بی ربط بود بدون جواب بذاره.

نگاه کنه که connection ها valid باشن.

______________
### $\color{#25678D}{\textsf{Web Application Filtering (WAF)}}$
**Web Application Filtering (WAF). Will check if the request is valid and not fishy! WAF can do the HTTPS termination**


یک ابزاره که تخصصش اینه که وقتی یک وب سرور پشتشه، ارتباط با سرور رو نگاه کنه و اگر یه چیزی مشکوکی داره رد می شه رو drop کنه.

_________________
## $\color{#105652}{\textsf{Network}}$

### $\color{#25678D}{\textsf{Load Balancing / Application Delivery Controller (like BigIP F5)}}$

می تونیم ابزاری مثل BigIP F5 بذاریم. در واقع F5 یک device است از شرکت BigIP

به این صورت استفاده می شه که میذاریمش پشت چندتا سرور و می تونه Load balance کنه. request رو می گیره و به صورت Load balance به سرورها می فرسته.
______________
## $\color{#105652}{\textsf{Progaramming}}$

### $\color{#25678D}{\textsf{Sandboxing on application}}$

**Sandboxing on application. Will prevent one DoS from Downing everything**

استفاده از sandboxing. -> به جای اینکه یه سرور داشته باشیم که apache، mysql و ... روش run شده باشه و اگر apache دچار مشکل شد و انقدر cpu مصرف کنه که همه چیز دچار مشکل بشه می تونیم سرویس هارو جدا جدا کنیم.

مثلا برای هر کدوم یه حد max در مصرف منابع تعریف کنیم.

سیستم هارو از هم جدا می کنیم.

___________________
### $\color{#25678D}{\textsf{Having challenges }}$

**Having challenges (Captcha, Validate browser with JS)**

چالش بذاریم مثل کپچا گذاشتن.

یا با مرورگر validate انجام بشه. -> مثل عکس هایی که می گه چراغ راهنماییارو پیدا کن توی عکس

______________
### $\color{#25678D}{\textsf{cloud services}}$

**There are cloud services for preventing and attacking (sold as IP Stressers/DDoSer/Booter/ dark web)**

می تونیم از cload service ها مثل cloadflare یا ابرآروان استفاده کرد.

خودش می گه من DNS شمام، DNS رو بذار پشت من و هر request ای اومد اول بیاد به من و من خودم می فرستم برات.

می تونه خودش https رو انجام بده دیگه سرور اصلی نیاز نیست tls حساب کنه.

اگر ریکوئستی اومد که خیلی زیاد بود من drop می کنم.

اگر سرور اصلی down شد، صفحه ای که cache کرده رو نشون میده.

جلوی DDoS رو می گیره.
_____________________
