# OWASP Juice Shop<br>

## Score Board<br>
Firefox > Debugger > Search score > found: /score-board<br>

## Bully Chatbot<br>
Menu > Support Chat > Keep spamming coupong <br>

## DOM XSS<br>
search bar > <iframe src="javascript:alert(`xss`)"><br>

## Bonus Payload<br>
Search bar > <iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/771984076&color=%23ff5500&auto_play=true&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><br>

## Confidential Document<br>
http://localhost:3000/ftp > acquisitions.md<br>

## Error Handling<br>
Account Login > put ' in email and password fields<br>

## Exposed Metrics<br>
http://localhost:3000/metrics<br>
