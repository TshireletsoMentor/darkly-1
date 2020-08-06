# 05_XSS_injection

nsecure processing of input, can be script injected  


## Method & Manipulation

Go to http://192.168.1.59/?page=feedback  
In the 'Name' field type `script`  
Press Enter

## Resolve

Attackers can easily inject harmful scripts.  
Sanitize all returns & inputs.

