# Sensitive_Data_Exposure
Sensitive user data should be protected at all times. Failure to do this presents a danger for users. Hackers can retrieve such data to exploit users.

## Example
In <a href="http://192.168.43.251/index.php?page=recover">recover</a> we are presented with a password recovery page. Seeing the button you're pushed to inspect and see what data is being sent.
<img src="https://github.com/PhethulwaziD/Darkly/blob/master/Sensitive_Data_Exposure/Resources/email.png" />

## Exploit
On inspection we see an email. When we manipulate the value of the emaila and change to whatever value we so please, when we do that get our flag.

## Remedy
* Do not expose sensitive data such as user email or password to the client side, if you do, which you should not, encrypt the  data and sanitize on receipt.

## Resources
* https://portswigger.net/support/using-burp-to-test-for-sensitive-data-exposure-issues