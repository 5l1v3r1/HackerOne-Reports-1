Vulnerability title: **Reflected Xss - Cross Site Scripting + Html Injection in Imgur image uploader error message**
Reported to: Imgur
State: **Duplicate** &rarr; **Resolved (Closed)**

## PoC
I created a file on my computer, named: `new.html`.
The content of the file is:
```html
<img src=x onerror=alert('test')>
```

I opened it in my browser, and opened a second window on https://imgur.com/.

I dragged my "image" (from the 1st browser window) and dropped it over to my 2nd window (imgur).

I could then confirm the presence of an XSS security vulnerability on the site:
![alt text](https://i.imgur.com/EEeGYNr.png "PoC Screenshot")
