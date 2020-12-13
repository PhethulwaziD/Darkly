# Spoofing
Spoofing is the act of disguising a communication from an unknown source as being from a known. Referer spoofing (based on a canonised misspelling of "referrer") sends incorrect referer information in an HTTP request in order to prevent a website from obtaining accurate data on the identity of the web page previously visited by the user. This is done so that an an attacker is served “premium content”.


## Example
In the footer of each page there is a link to © BornToSec, on clicking that, we are redirected to <a href="http://192.168.43.251/?page=e43ad1fdc54babe674da7c7b8f0127bde61de3fbe01def7d00f151c2fcca6d1c">this page</a>. On inspection we realise that we have been given some clues as to how we can go about getting our next flag. We are given the following comments as clues.
#### Clues
* You must cumming from : "https://www.nsa.gov/" to go to the next step
* Let's use this browser : "ft_bornToSec". It will help you a lot.

## Exploit
By using curl we can set a referer head to link our web page we can get our using grep to grab our our flag
> curl --referer "https://www.nsa.gov/" --user-agent "ft_bornToSec" http://192.168.43.251/?page=e43ad1fdc54babe674da7c7b8f0127bde61de3fbe01def7d00f151c2fcca6d1c | grep "flag"

## Remedy
*  There's no definitive way of determing the URL Referrer.
* HTTP_REFERER is optional. Some firewall packages strip these out by default, some clients don't send the referer value, and and there are numerous ways (like the one you showed in the question) to modify this value.

## Resources
* https://en.wikipedia.org/wiki/Referer_spoofing
* https://stackoverflow.com/questions/3104647/how-to-spoof-http-referer
* https://www.youtube.com/watch?v=SHmQ3sQFeLE
* https://stackoverflow.com/questions/21807604/preventing-curl-referrer-spoofing