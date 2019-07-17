Vulnerability Title: **Response Code 405 discovered on a subdirectory**\
Reported to: **Snapchat**\
State: **Informative (Closed)**

---

*(Neither me, nor the Snapchat security engineering team could find a malicious way to exploit this in some way, but I thought it'd be interesting to share this little "design bug")*

## Description
I was curious to see where subdirectories of https://accounts.snapchat.com/ on /accounts/ would get me. I tried a couple of things and ended up spotting something 'unusual'.

## Details
Navigating over to: https://accounts.snapchat.com/accounts/login \
Response Code: `200`\
Would get you here: https://i.gyazo.com/0f6ad7c9cd052864bec7527a25d35119.png

Navigating over to: https://accounts.snapchat.com/accounts/xxx (where `xxx` can be any random string)\
Response Code: `404`\
Would get you here: https://i.gyazo.com/5faa10f3f8357de2774b3bfda3dc9aca.png

*However,*\
Navigating over to: https://accounts.snapchat.com/accounts/logout \
Response Code: `405`\
Would get you here: https://i.gyazo.com/4627fe63737f5869f0ee4c311f25cd41.png \
**"Error: HTTP method GET is not supported by this URL"**

Snapchat may want to take a look at this little ~~security flaw~~ "design bug" and take care of it.
