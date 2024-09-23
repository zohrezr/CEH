$\color{#b91646}{\textsf{Footprinting}}$
========================================

### $\color{#25678D}{\textsf{Concept}}$

مثلا یه پیامی برای یکی می فرستی یه مدل خاصی جواب میده -> بسته به OS یا program version ها و ...

در نتیجه اگر همه ی اینارو بریزیم توی یه database و بررسی کنم می تونم بفهمم سیستمم چیه؟

می تونیم با nmap این کارو انجام بدیم.
_______________________
### $\color{#25678D}{\textsf{telnet, nc}}$
- **telnet**

می تونیم با telnet از طریق TCP connection به یه چیزی وصل شیم.

  `#telnet <Target IP or Target domain> <Traget port>`

- **nc** -> ncat-Concatenate and redirect sockets

  *Arbitary TCP and UDP connections and listens.*

می تونه روی socket ها کارهای متنوعی انجام بده. -> سرچ کنیم.

`#nc -l <Target IP or Target doamin> <Traget port>` 

یه تونل TCP برای یه ماشین درست می کنیم برای اینکه گوش بدیم. و با اون ماشین می تونیم telnet بزنیم.

`#nc <Target IP or Target doamin> <Traget port> < filename.in`

  Transmit contents of file "filename.in"

`#nc <Target IP or Target doamin> <Traget port> > filename.out`

  Sending incoming data to "filename.out"
__________________________________________
### $\color{#25678D}{\textsf{nmap, zenmap}}$

- **nmap**
- **zenmap**

در واقع همون nmap است ولی به صورت گرافیکی
______________________
### $\color{#25678D}{\textsf{Intense Scan}}$

- **Note that “Intense Scan” will try to identify the IP ID Sequence generation type (incremental is good for IDLE scan)**

توی idle خوبه که IP ID Sequence رو چک می کنه.
____________________
### $\color{#25678D}{\textsf{On windows try ID Serve Banner Grabbing (GRC)}}$

یه برنامه ی ویندوزی است.

مثلا ممکنه یه FTP server هر ورژنش وقتی بهش وصل می شی یه پیغام بده => می تونی بفهمی ورژن FTP server چیه.

این برنامه، اینارو می شناسه و بهتون می گه این برای کیه.
