$\color{#b91646}{\textsf{Privilege escalation}}$
================================================

بالا بردن سطح دسترسی

### $\color{#25678D}{\textsf{Horizontal}}$

**Horizontal -> another user**

افقی -> شما از یک یوزر تبدیل می شین به یه یوزر دیگه

مثلا با یوزر jadi حق لاگین دارم و سعی می کنم برسم به یوزر apache -> چون یوزر apache می تونه به وب سرور دسترسی داشته باشه در نتیجه می تونم وب سرور رو هک کنم.

_________________
### $\color{#25678D}{\textsf{Vertical}}$

**Vertical -> gain more access**

عمودی -> یک یوزر هستین که در لینوکس دسترسی root و در ویندوز دسترسی administrator می گیریم.

__________________
### $\color{#25678D}{\textsf{Password change}}$

معمولا بالا بردن سطح دسترسی از طریق عوض کردن پسورد اتفاق می افته.

توی ویندوز برنامه های زیر رو برای این کار داریم.

پسورد یکی رو reset می کنی و باهاش login می کنی.

- **Active@ Password changer**
- **Trinity Rescue Kit (TRK)**
- **ERD Commander**
- **Windows Recovery Env (WinRE)**
- **Password Resetter**

در دنیای ویندوزی پسورد reset کردن سخت تر است.

قبلا password ها در فایل etc/passwd/ بودن که توسط همه قابل خوندن بود ولی الان پسورد ها در etc/shadow/ هستن که نیازمند permision بالاتر است و کارابرای عادی بهش دسترسی ندارن.
