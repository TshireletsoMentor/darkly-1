# 04_Admin_cookie

Admin cookie session stored unsecurely  


## Method

Go to http://192.168.1.59/  
Next to the url bar click on the site information button  
Select cookies and then click the categories to find `I_am_admin` cookie


## Manipulation

The cookie content contains the hash
```bash
b326b5062b2f0e69046810717534cb09
```

We can use md5 decode to decrypt it and encode a new one
```bash
b326b5062b2f0e69046810717534cb09 -> md5 decode -> false
true -> md5 encrypt -> b326b5062b2f0e69046810717534cb09
```

In the browser Inspect element. Go the `Application` tab  
Under `Storage` open the `Cookies` section.  
Here we can double click the cookie value and change it to our new hash (`true`).  
Refresh the page and the flag will appear in an alert.

## Resolve

Never save sensitive session information on the browser. Store information such 
as is_admin on the database or the session variable on the backend where 
it cannot be accessed and use cookies to track if a user is logged in after they
have logged in,with no information about the user session itself,and 
should be signed or encrypted with something like JWT
be accessed

### Resources

https://www.hackers-arise.com/post/2017/04/24/database-hacking-part-4-extracting-data-with-sqlmap  
https://www.md5online.org/md5-decrypt.html  
https://passwordsgenerator.net/sha256-hash-generator/  
