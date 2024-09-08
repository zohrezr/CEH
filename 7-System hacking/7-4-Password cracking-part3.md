$\color{#b91646}{\textsf{Password cracking}}$
=============================================

## $\color{#105652}{\textsf{Active Online Attacks}}$

### $\color{#25678D}{\textsf{Guessing}}$
Guessing (create potential parts, rank them and test)

آسون ترین و مرسوم ترین شیوه حدس زدن است.

کافیه آدمارو بشناسی و شروع کنی به حدس زدن.

برای سامان دهی می تونیم از potential parts استفاده کنیم -> اطلاعاتی که از فرد داریمو کنارهم بذاریم (سن، سال تولد، علاقمندیا و ...) و بعد بهشون رنک بدیم.
________________________________
### $\color{#25678D}{\textsf{Trojan, spyware, keylogger}}$

یه برنامه ای توی کامپیوتر خودتون یا قربانی نصب می کنی که پسورد هارو می کشه بیرون.

چندتا تکنیک می تونه داشته باشه:

- واقعا Hash پسوردهارو نشون بده
- می تونیم keylogger داشته باشیم
__________________________________
### $\color{#25678D}{\textsf{Hash Injection}}$

**On windows pwdump7.exe will dump hashes**

اصطلاح hash injection یعنی hash ای رو بردارین و در جایی که لازم نیست استفاده کنید.

برنامه ی pwdump برنامه ای است مخصوص خوندن hash ها 

این برنامه میره توی فایل sam و دیتاهای مربوط به hash یوزنیم ها رو درمیاره


## $\color{#105652}{\textsf{Offline Attacks}}$


فرض می کنیم با یه روشی hash پسوردها رو به دست آوردیم حالا چطوری می تونیم به پسورد اصلی برسیم؟


### $\color{#25678D}{\textsf{Precomputed hashes / rainbow (winrtgen + rcrack_gui.exe)}}$

هش هایی که قبلا حساب شدن.

حمله ی rainbow -> توی یه سیستمی که خیلی قدرت داره hash چیزای مختلف رو با الگوریتم های مختلف حساب می کنن و می ریزن توی دیتابیس هاشون.

بعد که یه Hash داری و می خوای بشکنیش میری query می زنی توی این دیتابیسه ببینی هست یا نه

ار سایت ها یا برنامه های مختلفی می تونیم به عنوان rainbow cracker استفاده کنیم. -> rainbow cracker، crack station
____________________________________
### $\color{#25678D}{\textsf{Brute force (John the ripper)}}$

ایده های کلاسیک brute force کردن.

یکسری Hash رو تست می کنی ببینی همونی میشه که می خوای یا نه.

برنامه هایی مثل john the ripper داریم که میان از GPU استفاده می کنن (بهینه می کنه)

Distributed Network Attacks (DNA)
Simply, using distributed machines. Like SETI@Home
Default Passwords
USB Automated Password Theft (autorunning pspv.exe on windows)

