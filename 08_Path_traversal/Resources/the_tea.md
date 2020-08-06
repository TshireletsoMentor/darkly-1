# 08_Path_traversal

Able to read arbitrary files on the server running the application.  
This might include application code and data, credentials for back-end systems, and sensitive operating system files. In some cases, an attacker might be able to write to arbitrary files on the server, allowing them to modify application data or behavior, and ultimately take full control of the server.

## Method & Manipulation

Go to http://192.168.1.59/?page=../../../../../../../etc/passwd  
And voila! a flag

## Resolve

Enfore proper access control throughout the webpage

## Resources

https://portswigger.net/web-security/file-path-traversal
