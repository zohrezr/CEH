$\color{#b91646}{\textsf{Network scanning intro}}$
==================================================

## $\color{#105652}{\textsf{Find hosts}}$

- **Wardialing (ToneLoc, Phonesweep, THC-SCAN)**

برنامه هایی که می اومدن تمام شماره هارو می گرفتن شاید به یه مودم وصل می شدن (قبلا استفاده می شد)

- **Wardriving**

به یه لپ تاپی که داره wireless رو چک می کنه یا ابزارهایی که می بینن چندتا wireless هست و passowrd ندارن تو خیابون یه مسیری رو میری و در نتیجه یه نقشه ای داری از تمام wireless هایی که توی راه بوده.

- **ping / hping3**
    - concept
    - nmap –sP –v

با ping یه سرور رو پیدا می کنیم. می تونیم دونه دونه ping کنیم یا یه رنج رو با دستوراتی مثل nmap پینگ کنیم. (subnetting)

با سویئچ های sP- می بینیم چه هاست هایی وصلن و v- جزدیات بیشتری رو نشون میده.
  
- **Ping Sweep tools**
- **nmap -sn  (sweep network)**

## $\color{#105652}{\textsf{Find ports}}$

- **Banner Grabbing (Identify OS / Service / Version / …)**

با nmap می تونیم port هارو هم بررسی کنیم.

می تونیم از دستورات ssh و telnet روی portهای مختلف باز و بسته بودن portها رو بررسی کنیم

می تونیم بررسی کنیم توی hostهایی که توی شبکه پیدا کردیم چه portهایی بازه، چه OS ای داره، چه سرویس و چه ورژنی روش run است.

## $\color{#105652}{\textsf{Vulnerability Scanning}}$

بعد از پیدا کردن host ها و port های باز مشکلات امنیتی رو بررسی می کنیم.

یکسری از مشکلات امنیتی شناخته شده است مثلا فلان برنامه فلان ورژن این مشکل رو داره.

یکسری ابزارها هست که می تونه بررسی کنه روی این host و port مشکل امنیتی هست یا نه.

## $\color{#105652}{\textsf{Document / Network Diagram / Report}}$

در تمام مدت نتایج رو داکیومنت می کنیم.

## $\color{#105652}{\textsf{And… Evade IDS}}$

- **Change source**
- **Packet fragmentation** -> تیکه تیکه کردن پکت
- **Spoofing IP**
- **Proxy / Daisy chaining** -> همه چیزو از یه جا تست نمی کنی

این یه قدم نیست -> توی همه ی مراحل هست.

مواظبیم که از IDS ها رد بشیم.

اگه یه برنامه اجرا کنی که همه ی portها رو روی همه ی IP ها اجرا کنه، معلومه که فایروال جلوشو می گیره -> باید با روش های ذکر شده evade کنید.
