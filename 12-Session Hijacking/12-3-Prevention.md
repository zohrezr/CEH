$\color{#b91646}{\textsf{Prevention}}$
======================================

### $\color{#25678D}{\textsf{On WASP}}$

On WASP session management is always there

همیشه در OWASP خطر session hijacking خیلی بالا بوده.


### $\color{#25678D}{\textsf{Physical}}$

Physical to prevent sniffing, Port security, ..

برای جلوگیری از seesion hijacking اولین راه جلوگیری راه های فیزیکی است.

### $\color{#25678D}{\textsf{Application layer}}$

- **Good session IDs. Not predictable & no calculatable**

از sessionID های خوب استفاده کنید. قابل پیش بینی و قابل محاسبه نباشه.

- **Never use URLs with session IDs**

نباید session ID در url باشه.

- **Do not reuse session IDs**

- **Flag cookies as HTTP only (no access to JS)**

کوکی ها به صورت httponly تنظیم بشن. در نتیجه از طریق JS در دسترس نیست.

- **Flag cookies as SECURE (only https)**

تنظیم کنیم که کوکی secure باشه یعنی کوکی فقط از طریق https منتقل بشه.

- **TLS**

از TLS استفاده کنیم. https داشته باشیم.

- **Re-Auth**

هرچند وقت از یوزر بخوایم لاگین کنه. می تونیم براساس activity و زمان استفاده انجام بدیم.

- **Invalidate tokens based on inactivity and time**
- **OAUTH**
- **forced logouts**
