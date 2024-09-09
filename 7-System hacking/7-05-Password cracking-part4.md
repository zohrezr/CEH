$\color{#b91646}{\textsf{Password cracking}}$
=============================================

## $\color{#105652}{\textsf{Security Accounts Manager (SAM)}}$

- **File at system32\config\SAM**
- **Using LM/NTML hashing**
- **SYSKEY encrypts the SAM**
- **There is always a file lock on SAM while the windows is running**
- **Link:1010:624AAC413795CDC14E835F1CD90F4C76:6F585FF8FF6280B59CCE252FDB500EB8:::**
- **Check page 304**


ویندوزیه

مکانیزم SAM برای نگه داشتن اطلاعات و دسترسی کاربران در ویندوز استفاده می شه.

یه کاری که می کنن برای اینکه فایل رو حالت عادی بخونن -> همیشه یه دونه file lock می زنن.

در واقع file lock می گه وقتی می خوان یه فایلی رو باز کنن و توش یه چیزی بنویسن یه file lock می زنن یعنی فلانی داره با این فایل کار می کنه. در نتیجه کس دیگه ای اجازه نداره این فایل رو باز کنه که خراب نشه.

ویندوز در تمام مدتی که ویندوز در حالت اجراست یه file lock روی SAM می زنه در نتیجه کسی نمی تونه باهاش کار کنه.

## $\color{#105652}{\textsf{Kerberos}}$

- **Kerberos (after win 2000), page 305**

از یه جایی به بعد مایکروسافت اومده سراغ kerberos (توی کرنل لینوکس هم داریمش)

با 3 تا component داره:

- **Key distribution center (KDC)**
- **Authentication server (AS)**
- **Ticket-granting server (TGS)**

سبک کاری اصولا اینجوریه که یک یه ریکوست به یکی میده که می خوام این کارو بکنم و اون بهش یه تیکت میده که می تونه با اون تیکت کاری که می خوادو بکنه.

## $\color{#105652}{\textsf{Password Reset via physical access}}$

- **Password Reset via physical access (chntpw - bootable, mounting, …)**

با یه چیزی مثل SAM طرفیم که یه فایله یه جایی که یکسری اطلاعات توشه.

توی دنیای کامپیوتر اگر به چیزی به صورت فیزیکی دسترسی داشته باشی، اون چیز هک شده است.

ابزار chntpw -> برای حمله ی فیزیکی، یه فایل iso است.

یه کامپیوتری دارم که یه پسورد داره و نمیذاره برم توش. میام یه cd رایت می کنم و میذارم توی کامپیوتر و کامپیوتر boot می شه میاد بالا. حالا که اومده بالا این cd یه برنامه داره که می تونه بره فایل هایی مثل SAM رو ببینه و دستکاری کنه.

سناریو: با یک لایو لینوکسی که تخصصش شکستن SAM است boot کردم. یکسری منو بهت میده. بعد ازاینکه کارایی که می خواستیمو کردیم سیستم رو reboot می کنیم.


فایل ISO رو از توی strorage خارج می کنیم. و خوده ویندوز رو run می کنیم.

**حمله به ماشین خاموشه و به ماشین طبیعیه روشن نیست.**

## $\color{#105652}{\textsf{Non Electronic}}$

- **Recovery systems**
- **Social Engineering**
  - Gettings the password
  - Gaining access to reset, keylogger, …
- **Solution? EDUCATION**
