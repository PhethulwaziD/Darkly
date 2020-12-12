# XSS
Javascript Injection or rather, for lack of a better term Cross Site Scripting(XSS). This a sort of attack where a user can inject some javascript code into the page and make perform a potentially malicious action like stealing a session cookie.


## Example
One of the most vulnerable pages that is prone to this attack is <a href="http://192.168.43.251/?page=feedback">feedback</a> page, mainly because it carries persistent data that is stored in the database and at will be viewed by all.

## Exploit
Though the page has regex against such an  attack, it is still flawed, all we have to do is to submit either a < or > or even script, this will allow us to get our flag:0fbb54bbf7d099713ca4be297e1bc7da0173d8b3c21c1811b916a3a86652724e.

## Remedy
* Use htmlspecialcharacters, this will make sure that a tag is not views as anything but just text.

## Resources
* https://www.youtube.com/watch?v=SHmQ3sQFeLE