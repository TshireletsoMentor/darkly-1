# 10_HTTP_Headers

Manipulation of HTTP headers

## Method 

Go to any footer, click on the copywrite BornToSec  
Inspect the image, which is a link.  
In the comments we see a story in French, and further down the following lines
```bash
You must cumming from : "https://www.nsa.gov/" to go to the next step
...
Let's use this browser : "ft_bornToSec". It will help you a lot.
```

## Manipulation

We can use the attached script to changed the headers:
```bash
User-Agent="ft_bornToSec"
referer="https://www.nsa.gov/"
```

Run the script:
```bash
sh script.sh | grep "flag"
```
The flag will appear, as rendered in `answer.html`

## Resolve

Do not store information inside comments on the frontend. These
comments can be read and used by anyone.

