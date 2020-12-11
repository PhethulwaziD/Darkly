# Cookie_Poisoning
The cookie problem is a really bad one; cookies can be hijacked and poisoned. Cookie poisoning is when a hacker manipulates or forges session cookies for the purpose of bypassing security measures, impersonate and breach privacy. By forging these cookies, an attacker can impersonate a valid client(Cookie Hijacking)

## Example
When inspecting <a href="http://192.168.43.251/">recover</a>. and checking storage cookies, we are presented with a cookie session that can be obviously manipulated.
<img src="https://github.com/PhethulwaziD/Darkly/blob/master/Cookie_Poisoning/Resources/cookie.png" />

## Exploit
Through a number of attempts we realise that the encrytion for this cookie is md5 whih when decrypted is false for I_am_admin, if we create an md5 true encryption, we are presented with our flag:df2eb4ba34ed059a1e3e89ff4dfc13445f104a1a52295214def1c4fb1693a5c3

## Remedy
* Validate cookie values with ones that have been set and sent by the server.
* Do not give cookies intuitive names.

## Resources
* https://www.youtube.com/watch?v=QE7gNcICAek
