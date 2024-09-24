$\color{#b91646}{\textsf{Session Hijacking inroduction}}$
=========================================================

- **It is like hijacking ATM after you provided your password**
- **Hijack the session just after Authentication**
- **Can happen on network Level or Application level**
- **People do not want to re-authenticate on every single HTTP / TCP request. So applications do have Persistence methods. Say Cookies, Specific URLs, Hidden form fields, session ID, token,**

اگر بتونی session یه نفر رو بدزدی می شه Session Hijacking

در دنیای network وقتی طرف وارد شد (authenticate می کنه) و session گرفت مهاجم باید به یه طریقی session رو به دست بیاره و خودش ادامه ی کارو بده.

در لایه ی application بسیار مرسوم تر است.

می تونیم session رو از طریق coockie یا url یا ... به دست بیاریم.
