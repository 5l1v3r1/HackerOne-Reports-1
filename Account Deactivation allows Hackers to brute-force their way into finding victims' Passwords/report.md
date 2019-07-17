Vulnerability Title: **Account Deactivation allows Hackers to brute-force their way into finding victims' Passwords**\
Reported to: **Twitter**

## Steps of reproduction (PoC)
When logged in, I visited: https://twitter.com/settings/accounts/confirm_deactivation

I then clicked on `Deactivate @xxxxx` and it popped up a window named `Deactivate account` (Title), and it displayed `Re-enter your Twitter password to deactivate @xxxxx`.

Screenshot: http://i.imgur.com/e6IVxLC.png

So, in order to deactivate your account, you'd just have to type your Password to confirm you wanted to deactivate. Why type your Password? Obviously to protect it, from malicious Users (Hackers), who somehow got Access to your Account and wanted to deactivate it. Therefore, you prompt them with another barrier, which is to type the Password of the Account, in case they found the User logged in to Twitter already. So, if they don't have the Password they won't be able to deactivate the victim's Account, right? Well, the answer is they can.

After constantly trying random (incorrect) Passwords, and in the end typing the correct Password, I realized it let me logged in, after typing the correct Password after so many failed attempts. This means that if the Hacker finds the Account logged into Twitter, and tries to deactivate the Account of the victim, whether he knows the victim's Password or not, he'll be **able to brute-force his way into finding his Password**. Not blocking the Hacker's IP Address after X failed attempts, can result into him finding the User's Password.

Also, Twitter lets you re-activate your Account if you've logged back in within 30 days of deactivation. So, the Hacker can't only deactivate your Account, but he can also just find your Password, *without deactivating your Account*, meaning he can log into the Account, use and take it over without the User ever even noticing.

## Example scenario
A celebrity's Digital Device (e.g. Phone/Laptop) is stolen. The malicious user takes the device to his "lab", where they're going to attempt to find the victim's Twitter password. They visit www.twitter.com, and they see that he's already logged in using the victim's account\*. All that is left for them to do is to find the victim's Password. So they visit https://twitter.com/settings/accounts/confirm_deactivation and click on `Deactivate @xxxxx`. They then brute-force their way into the victim's password, Twitter "deactivates" the Account (after 30 days...) and they then log back in (of course within 30 days of his brute-force execution), and without the account being deactivated, he's just got the celebrity's password.

\*Too unlikely? It already happened to @Jessewelle (https://twitter.com/Jessewelle): http://prankvsprank.shoutwiki.com/wiki/Jesse_Wellens#Twitter_hack

This security flaw can result into tons of Account Passwords being brute-forced and found as long as they're logged in. All this needs to be fixed, is a simple block-after-X-attempts barrier measure, like the security implemented into http://twitter.com/login and https://mobile.twitter.com/session/new where it blocks the Hacker from brute-forcing, blocking his IP Address for about an hour from retrying to login.

**Tl;dr**: the password-input "barrier" is pointless without the block-after-X-attempts security measure.
