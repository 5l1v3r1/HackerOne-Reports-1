Vulnerability Title: **Punycode Phishing Attack using Tweets**\
Reported to: **Twitter**

## Description
I'm sure we've all heard of the famous Punycode social engineering/phishing attack which has seemed to get the attention of several people in the field of information security: https://www.xudongz.com/blog/2017/idn-phishing/

## Punycode Vulnerability
I looked around Twitter and noticed that if I tweeted a Cyrillic-containing URL it will not be converted to Punycode. This can very easily trick a lot of people into falling victims to social engineering attacks, considering there is no apparent difference between many Cyrillic and ASCII characters.

## Proof of Concept (PoC):
https://twitter.com/0xCoto/status/1151512166362730498

As you can see, the difference between the characters is visually indistinguishable, making unsuspecting Twitter users vulnerable to this social engineering attack.

## Suggested solution implementation
Every time a Cyrillic URL is tweeted, Twitter should automatically replace that URL with Punycode characters. In this case, `соdу.com` should automatically be replaced with `xn--d-0tbik.com`.
