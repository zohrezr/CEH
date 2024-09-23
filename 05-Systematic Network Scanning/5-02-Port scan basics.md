$\color{#b91646}{\textsf{Port scan basics}}$
=============================================

ماجرا -> یه host دارم یه جایی، می خوام ببینم چه port هایی روش بازه.


![Uploading image.png…]()

- **Remind the TCP flow**

مفهوم TCP flow که شامل 3way handshake و ارسال data و 4way handshake می شه رو باید بدونیم.
______________

- **Services should be accessible, so you will see them**

سرویس هایی که مدنظر باید روی یه port خاص در دسترس باشن.
___________________
- **We will get / send RST packet to close. So we can have**

- **There are also URG (process immediately) & PSH (send all buffered data immediately) flags**

 پکت هایی که می فرستیم یکسری flag دارن -> مثل SYN, URG,PSH,RST,FIN (مقدارشون 0 و 1 است)
_____________________
- **Open wireshark, run nmap -sX ip & check in wireshark with ip.addr == ip**

سوئیچ X -> یعنی Xmas Scan پس تا جایی که می شه همه ی flag هارو 1 کن.

پکت Xmas -> یک پکتی است که FIN=1, URG=1, PSH=1 است. چنین پکتی غیر طبیعی است و خیلی از سیستم ها گیج می شن.

می توتنیم همچین پکتی بفرستیم و توی **wireshark** نگاه کنیم.
_____________________________
- **Or we can send only ACK packets! If there is a stateful firewall, it will drop these packets**

به جای اینکه 3way handshake انجام بدیم که تابلوعه دارم به یه port ای وصل می شم -> الکی یه دونه پکت ACK بفرستم به اون port.

اگر توی شبکه ای stateful firewall باشه یعنی firewall ای که می فهمه وضعیت چیه؟ چی به کجا وصل شده؟ اگر فقط یه پکت ACK بفرستی حذفش می کنه چون می فهمه قبلا وصل نبودی و SYN نزده بودی => می فهمی بین شما و شبکه یه satetful firewall هست.
___________________
- **-f will fragment packets in nmap**

پکت رو تیکه تیکه می کنیم که firewall یه جا نبینتش.
