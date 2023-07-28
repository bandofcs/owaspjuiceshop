# OWASP Juice Shop<br>
## 1 STAR
### Score Board<br>
Firefox > Debugger > Search score > found: /score-board<br>

### Bully Chatbot<br>
Menu > Support Chat > Keep spamming coupong <br>

### DOM XSS<br>
search bar > <iframe src="javascript:alert(`xss`)"><br>

### Bonus Payload<br>
Search bar > <iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/771984076&color=%23ff5500&auto_play=true&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><br>

### Confidential Document<br>
http://localhost:3000/ftp > acquisitions.md<br>

### Error Handling<br>
Account Login > put ' in email and password fields<br>

### Exposed Metrics<br>
http://localhost:3000/metrics<br>

### Outdated Allowlist<br>
gospider -v -s http://127.0.0.1:3000/ -o gospider_output<br>
cd gospider_output
cat 127_0_0_1 | grep code-200<br>

### Missing Encoding<br>
change # to %23<br>
http://localhost:3000/assets/public/images/uploads/%F0%9F%98%BC-%23zatschi-%23whoneedsfourlegs-1572600969477.jpg<br>

### Zero Stars<br>
http://localhost:3000/#/contact<br>
burp proxy > repeater > rating:0<br>

### Repetitive Registration<br>
http://localhost:3000/#/register<br>
burp proxy > repeater > passwordRepeat:""<br>
