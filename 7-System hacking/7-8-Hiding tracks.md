$\color{#b91646}{\textsf{Hiding tracks / Covering tracks}}$
===========================================================

در حین کاری که داریم انجام میدیم ردپاهایی از ما می مونه که باید اینارو پاک کنیم.

خیلی جاهای مختلفی بسته به سیستم های مختلف ردپا می مونه. (موراد زیر خیلی ساده ها هستن)

### $\color{#25678D}{\textsf{Most Recent Used (MRUs)}}$

جاهای مختلفیه مثلا word هم که باز می کنی most resent used هارو نشون میده -> مثلا می تونید 200 تا فایل الکی باز کنید که اون دیده نشه.

_________________
### $\color{#25678D}{\textsf{On windows you can Disable auditing}}$

- **auditpol \\ip /clear**
- **And many tools like Dump Event Log, ELSave, Winzapper, CCleaner, Wipe, MRU-BLaster, Tracks Eraser Pro, Clear My History**

توی سیستم های ویندوز عموما این قابلیت هست که auditing رو disable کنید. -> با استفاده از auditpool و ابزارهای دیگه ی نامبرده شده.

__________________
### $\color{#25678D}{\textsf{On Linux}}$

- **unset HISTFILE, delete .bash_history**
- **/var/log/**
- **Space, …**

توی لینکوس یه history داریم که هر اتفاقی که می افته رو ذخیره می کنه -> با دستور history می تونیم دستوراتی که زدیم رو ببینیم.

اگر بخوایم history لینوکس رو پاک کنیم توی یه فایلی به اسم HISTFILE ذخیره می شه. با دستور unset دیگه هرچی دستور بزنی توی history نمی افته.

در مسیر var/log/ همه ی برنامه ها برای خودشون log میذارن.

______________
### $\color{#25678D}{\textsf{specific log files related to your activities and softwares}}$

**And you have be aware of specific log files related to your activities and softwares you are attacking to**

خیلی وقتا activity های شما توسط برنامه های خاص log می شه.

لینوکس این امکان رو داره که log هاشو بفرسته برای یه سرور دیگه در نتیجه به راحتی پاک نمی شه
