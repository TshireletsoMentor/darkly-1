# 00_Unsecure_email_on_FE

Unsecure email address stored in the front end.
Where: http://192.168.1.59/?page=recover#

## Method

Go to http://192.168.1.59/?page=recover#
Inspect submit button element
Change email while respecting length contraints
Click submit

# Manipulation

This can be manipulated by changing the email to an exsiting user to gain login information.
A compromising script can we sent to this email

### Resource

Help: https://www.acunetix.com/blog/articles/exploiting-sql-injection-example/
