$\color{#b91646}{\textsf{Password cracking}}$
=============================================

## $\color{#105652}{\textsf{Paswword}}$
- **Some that one person can remember to prove herself to the system**

پسوردها علاوه بر اینکه به شما می گن اجازه دارین login کنید یا نه دسترسی های user رو هم به شما میدن.

- **Numbers, letters, upper/lower, names, words, short passwords**


فضای password باید بزرگ باشه.

## $\color{#105652}{\textsf{Cracking Techniques-category1}}$

### $\color{#25678D}{\textsf{Dictionary Attacks}}$

دیکشنری بذاری جلوت و همه ی کلمانشو تست کنی -> خیلی کنده
___________________________
### $\color{#25678D}{\textsf{Brute Force}}$

تمام حالت های ممکن رو امتحان کنی
__________________
### $\color{#25678D}{\textsf{Hybrid (Dict + other steps)}}$

بری سراغ dictionary attack و حالت های مختلفشو تست کنید.

مثلا در dictionary attack فقط کلمه ی password بررسی می شه ولی در حالت Hybrid عبارات p@ssword, passw0rd, p@ssw0rd و ... هم تست می شه.
_________________
### $\color{#25678D}{\textsf{Syllable Attack (Dict + brute force)}}$

دیکشنری رو برداریم و باهم کلماتشو ترکیب کنیم.
___________________
### $\color{#25678D}{\textsf{Rule based attack (favorite numbers, names)}}$

چیزی که واقعا اتفاق می افته.

می خوای پسورد jadi@gmail.com رو هک کنی.

یکسری اطلاعات از jadi داری مثلا -> linux دوس داره، CEH دوس داره، از farzane خوشش میاد، dog دوس داره، متولد 1356 و ...

در نهایت dictionary attack می کنی روی ترکیب اینا مثلا -> jadi1356
_____________________

## $\color{#105652}{\textsf{Cracking Techniques-category2}}$

### $\color{#25678D}{\textsf{Passive Online Attack (Wireshark, MITM)}}$

می خوای به یه box حمله کنی -> Passive یعنی به خوده box حمله نکنی، به حواشیش حمله کنی. (منفعل)

یکی داره به یه جایی با یه پروتکل ناامن مثل telnet لاگین می کنه.

مهاجم وسط connection یوزر و مقصدش یه شنود میذاره -> پسورد کاربر رو میبینه و برمیداره
______________________
### $\color{#25678D}{\textsf{Active Online Attack}}$

می خوای به یه box حمله کنی -> Active یعنی به خوده box حمله کنی.

در حالت Active Onilne Attack یعنی در حالی که online هستی حمله می کنی
- **Guessing**

آسون ترین کار -> سعی می کنی پسورد رو حدس بزنی.

- **malware**

یه بدافزار نصب می کنی روی قربانی نصب می کنی. به یه شیوه ای یه ویروس میذاری توش که بره پسوردهارو بخونه و روی همون usb که ویروس رو روش گذاشتی بخونه و کپی کنه.

یه ایمیل می فرستی که پسوردهارو بخونه و بفرسته.

- **keylogger**

یه دستگاه کوچولوعه در حد یه usb ریز، بعضی وقتا اصلا usbشم دیده نمی شه -> یعنی یه دستگاه دیگه اس که می خوره به usb کیبورد و آدم عادی فکر می کنه یه usb معمولیه

تمام ضرب کلیدهایی که تایپ می شه رو توی memory ذخیره می کنه.

- **hash injection**

اون hash ای که یه بار فرستاده شده به سرور رو شما دوباره می فرستی.

- **phishing**

یه صفحه درست می کنم شبیه صفحه ی بانک

بعد قربانی دقت نمی کنه این صفحه همون صفحه نیست و پول رو واریز می کنه و میره به حساب مهاجم
______________________
### $\color{#25678D}{\textsf{Offline Attacks (Weak storing)}}$

پسورد کاربرا خیلی خوب نگهداری نشده

یه دیتابیسی هست که توش یه مجموعه پسورد است و مهاجم این رو می دزده.

کاربر یه جایی پسورد رو hash کرده و اون hash رو توی دیتابیس دارم -> سعی می کنم hash رو به شیوه های مختلف بشکنم.
__________________
## $\color{#105652}{\textsf{Cracking Techniques-category3}}$

### $\color{#25678D}{\textsf{Offline Attacks (Non technical)}}$

تا الان تمام  روش هایی که گفتیم تکنیکی بود.

مثلا زنگ می زنی به کاربر می گی من رئیستم پسوردتو به ما بده.
