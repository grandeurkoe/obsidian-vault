# SMTP (smptlib)

Email SMTP(Simple Mail Transfer Protocol) is a built-in module in python that lets us send emails.

The `smtplib` module allows you to send emails.
```python
import smptlib
```

The SMTP connection can be implemented like this -
```python
# Create a smtp session object. Store the value of this object in the connection variable.
# The SMTP address for google is "smtp.google.com".
# Also use the port number 587.

with smtplib.SMTP("smtp.gmail.com", port=587) as connection:
	# starttls() function allows the creation of a secure connection channel.
	connection.starttls()
	# Login using the login() function.
	connection.login(user="again.meowya@gmail.com", password="iotmldmwjvxqvxgk")
	# Send Email using the sendmail() function.
	connection.sendmail(from_addr="again.meowya@gmail.com",    
	to_addrs="mailme.meowya@gmail.com", 
	msg=f"Subject:Happy Birthday!\n\nHappy Birthday!")
	# Anything after \n\n is considered as the body of the email.
```