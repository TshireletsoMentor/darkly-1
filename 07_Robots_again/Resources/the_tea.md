# 07_Robots_again

Robots.txt files give information to web robots, these can be used an exploit

## What is robots.txt

A robots.txt file tells search engine crawlers which pages or files the crawler can or can't request from your site. This is used mainly to avoid overloading your site with requests.  
  
The presence of the robots.txt does not in itself present any kind of security vulnerability. However, it is often used to identify restricted or private areas of a site's contents. The information in the file may therefore help an attacker to map out the site's contents, especially if some of the locations identified are not linked from elsewhere in the site. If the application relies on robots.txt to protect access to these areas, and does not enforce proper access control over them, then this presents a serious vulnerability.


## Method 

Go to http://192.168.1.59/robots.txt  
We get the following information:
```bash
User-agent: *
Disallow: /whatever
Disallow: /.hidden
```

## Manipulation

In this part we will find the flag in the `/.hidden` folder.  
Go to http://192.168.1.59/.hidden  
We can download a file called `htpasswd`  
Which contains:
```bash
root:8621ffdbc5698829397d97767ac13db3
```
We can try exploit by using this as the user login & hashed password
```bash
8621ffdbc5698829397d97767ac13db3 -> md5 decode -> dragon
```

We can now go to http://192.168.1.59/admin/  
and log in with 
```bash
username: root
password: dragon
```

## Resolve

Enfore proper access control throughout the webpage

## Resources

https://support.google.com/webmasters/answer/6062608?hl=en
https://portswigger.net/kb/issues/00600600_robots-txt-file
