# Sign up to a hosting provider and create your web service

## Create an account e.g., on render.com

Heroku discontinued their free plan, but other providers are still offering one. You can create an account on render.com simply by signing up via Github.

![[Pasted image 20231010122723.png|500]]

Click "authorize" and confirm your email address. Job done.

![[Pasted image 20231010122739.png|350]]

## Create a new Web Service

![[Pasted image 20231010122814.png|500]]

Choose your blog app that you've uploaded to GitHub and connect your repo

![[Pasted image 20231010122829.png|500]]

## Edit the Start Command

Most of render.com's defaults are fine. All you need to do is pick a name for your project and then change the Start Command to:

`gunicorn main:app`

![[Pasted image 20231010122850.png|500]]

## Add your first environment variable

Before you create your web service, click "Advanced" and add your environment variable your Flask app.

![[Pasted image 20231010122920.png|500]]

Scroll to the bottom and create your web service.

![[Pasted image 20231010122935.png|500]]

Your web app won't work yet, however. We first need to set up our database and set the environment variable for SQLAlchemy.