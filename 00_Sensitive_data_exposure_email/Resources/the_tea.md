# 00_Sensitive_data_exposure_email

Unsecure email address stored in the front end.  

## Method

Go to http://192.168.1.59/?page=recover#  
Inspect submit button element  
Change email value to anything 
Click submit

## Manipulation

- This can be manipulated by changing the email to gain login information.

## Resolve

- Store admin email in a variable on the backend securely.
- Add email validation to backend.
