# Broken_Access_Control
Access control (or authorization) is the application of constraints on who (or what) can perform attempted actions or access resources that they have requested. In the context of web applications, access control is dependent on authentication and session management


## Example
For this section we are going to use nikto; nikto is a programme that searches for known vulnerabilities of a website, much like sqlmap. When we use nikto to scan the web application we've given, we see a number of contents. These include and most interestingly a file called robots.txt. Now if we were to go to <a href="http://192.168.43.251/robots.txt">robots.txt</a> we are presented with a page that has routes that we can visit. One of those route is "whatever", when visting that route, we see a file called htpasswd that we can download. htpasswd has the following information root:8621ffdbc5698829397d97767ac13db3, which most probably is the admin login details.
<img src="https://github.com/PhethulwaziD/Darkly/blob/master/Broken_Access_Control/Resources/access.png"/>

## Exploit
Such in itself is useless unless your access control is broken, we can test that for this website by going to <a href="http://192.168.43.251/robots.txt">admin</a> which is the login page for the admin. As a normal user am not suppose to have acces to this page, but I do and I have the login credentials of the admin which we got from htpasswd which are root:dragron(decrypted md5 password). If we login we get our flag:d19b4823e0d5600ceed56d5e896ef328d7a2b9e7ac7e80f4fcdb9b10bcb3e7ff. 


## Remedy  
* Do not store super user data on the server
* Restrict access for normal users

## Resources
* https://www.youtube.com/watch?v=P38at6Tp8Ms