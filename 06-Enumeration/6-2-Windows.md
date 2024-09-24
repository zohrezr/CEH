$\color{#b91646}{\textsf{Windows}}$
=======================================

توی windows چه enumeration ای می تونیم انجام بدیم.

### $\color{#25678D}{\textsf{Users}}$

- **Default User in windows**
  - Guest
  - Administrator

با دونستن اسم user ها می تونیم brute force انجام بدیم.

- **Process in windows**
  - Local Service
  - Network Service
  - System
  - Current User

هر process ای که توی ویندوز اجرا می شه یکی از این حالت هاست.
________________
### $\color{#25678D}{\textsf{Groups}}$

- **Default groupes in windows**
  - Anonymous Logon
  - Batch
  - Creator Group
  - Creator Owner
  - Everyone -> all interactive, network, dial-up and authenticated users
  - Intractive
  - Network
  - Restricted
  - Self
  - Service
  - System
  - Terminal Server User

________________________
### $\color{#25678D}{\textsf{Security Identifiers (SID)}}$

  - Concept
  - Decoding
  - Location

سطح دسترسی یوزرها و گروه ها رو مشخص می کنه. -> یک اولی از امنیت رو داریم که در دنیای ویندوز با SID ایجاد می شه.

یکسری SID با عدد تعریف شده که سطح دسترسی رو مشخص می کنه.

یوزرها قبل از اینکه login کنن در سطح `S-1-15-18` هستن.

`S-1-0-0 (Null SID)`

`S-1-1-0 (World)`

`S-1-2-0 (Local)`
_________________________
### $\color{#25678D}{\textsf{Security Accounts Manager (SAM)}}$

فایلی است (دیتابیس) در ویندوز که دیتای SID ها رو نگه میداره و می فهمه یوزرها چه دسترسی دارن.

الزاما SAM به صورت encrypt شده نیست.

برای encrypt شدن SAM یه دونه Lan Manager (LM) داره.
_________________
### $\color{#25678D}{\textsf{PsTools command}}$

- PsExec (execute remotely)
- PsFile (display opened files remotely)
- PsInfo (get info from remote server)
- PsKill
- PsLoggedOn
- PsPasswd
- ...

در واقع PsTools command یک مجموعه اس که microsoft داده و یکسری ابزار داره.
