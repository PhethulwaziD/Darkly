# Traversal_Path_Attack
A path traversal attack (also known as directory traversal) aims to access files and directories that are stored outside the web root folder. By manipulating variables that reference files with “dot-dot-slash (../)” sequences and its variations or by using absolute file paths, it may be possible to access arbitrary files and directories stored on file system including application source code or configuration and critical system files.

## Example
By Appending "../" to http://192.168.43.251/index.php?page= we see that such an attack is possible.

## Exploit
* Being afforded to go through system can be quite bad. We can find information that we can use to exploit either the users of the page or the admin. We already know that the OS being used is linux and so we can go through some well known folders such as http://192.168.43.251/index.php?page=../../../../../../../etc/passwd Here we get our flag: b12c4b2cb8094750ae121a676269aa9e2872d07c06e429d25a63196ec1c8c1d0.


## Remedy
* Don’t store sensitive configuration files inside the web root
* Validate the user’s input by only accepting known good – do not sanitize the data, and many more.

# Resources
* https://owasp.org/www-community/attacks/Path_Traversal