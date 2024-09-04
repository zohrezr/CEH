$\color{#b91646}{\textsf{LDAP}}$
=======================================

- **Lightweight Directory Access Protocol (LDAP) is used to interact with and organize databases**

همونطور که می دونید Active Directory یک مجموعه سرویس در ویندوز است که authentication, authorization و ... هندل می کنه.

یه جور دیتابیس است برای اینکه کی به کجا دسترسی دارد.

پروتکلی که Active Directory رو می تونیم بخونیم LDAP است.

پروتکل LDAP اجازه میده با organize databaseها حرف بزنیم.

____________
- **Most of the time windows server is running LDAP alongside Active Directory but can work with Novell eDirectory, OpenLDAP, Open Directory, Oracle iPlanet too.**


معمولا ویندوزها وقتی Active Directory دارن LDAP هم دارن که بتونن به بقیه اجزای اون domain حرف بزنن و ببینن دسترسی دارن یا نه.
____________________
- **TCP 389 is unencrypted and you will be able to see the user / pass if its plain text**
- **Port 636 is encrypted**

389 قدیمی است و امروزه روی 636 است.
_____________________
- **Jxplorer.org** -> LDAP client

یه برنامه اس -> ویندوزی و لینوکسی است.

به صورت open source است.

به شما اجازه میده LDAP request بزنید.
___________________
- **To prevent enumeration, you should define correct permissions and security settings**

در دنیای ویندوز خیلی ها اشتباهات متنوعی در Active Directory می کنن.

چون یه چیزیو راه می اندازن و کار نمی کنه شروع می کنه دسترسی بیشتر بهش دادن.

______________
- **OpenLDAP**

در دنیای لینوکس ها OpenLDAP رو داریم.
