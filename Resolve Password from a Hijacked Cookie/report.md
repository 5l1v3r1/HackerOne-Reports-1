Vulnerability Title: **Resolve Password from a Hijacked Cookie**\
Reported to: **Twitter**

---
I have discovered a security flaw that allows a Password to be resolved from a Hijacked Cookie.

## Description
If the attacker has gotten hold of the victim's Twitter Cookie (`auth_token`) Value, he/she has got hold of his/her Account. But he/she can't do many things, such as change Password, change various (security) settings etc., so he/she can't completely takeover the victim's Account.
However, with this security vulnerability, the Attacker can **freely resolve the victim's Account Password by brute-forcing** his/her way into resolving it.

## Steps to reproduce
1. After being logged in (i.e. from a stolen Cookie), visit: https://twitter.com/settings/your_twitter_data 
2. Input an incorrect password multiple times\
3. Compose an algorithm or use a pre-made one that will help you brute-force this exploitable web-form\
4. After countless incorrect password attempts, Twitter will not block you from retrying another Password, and you can easily brute-force your way to finding the victim's Account Password and you are able to completely takeover the Account, which is now exposed to sensitive information that the Attacker should have never gotten access to.

## Method #2
Another way the Attacker could crack the User's Password, is by physically getting hold of the User's device which is already logged on to Twitter. The attacked could then completely takeover the account, leaving the victim no chance to reclaim his account.
An incident like this, recently happened to https://twitter.com/Jessewelle - where his Phone got stolen and the attacker could easily brute-force his way into finding his Password and completely taking over his account, without the victim being able to do anything about it.

## Script PoC screenshot
![alt text](https://i.imgur.com/v3MbpbS.png "Script PoC")
