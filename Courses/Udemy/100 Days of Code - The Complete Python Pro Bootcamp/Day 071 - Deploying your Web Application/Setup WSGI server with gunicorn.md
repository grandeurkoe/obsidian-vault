# Setup WSGI server with gunicorn

WSGI stands for Web Server Gateway Interface and it's described here: [https://www.python.org/dev/peps/pep-3333/](https://www.python.org/dev/peps/pep-3333)

In summary: normal web servers can't run Python applications, so a special type of server was created (WSGI) to run our Flask app.  Essentially, a WSGI server standardizes the language and protocols between our Python Flask application and the host server.

There are many WSGIs to choose from, but we'll use the most popular - [gunicorn](https://docs.gunicorn.org/en/stable/). That way our hosting provider will call gunicorn to run our code.

## Add gunicorn to the requirements.txt

Check if you have the gunicorn package included in your `requirements.txt`. If you are using the starting code for this section, you should see it listed. If you are using your own code, `add gunicorn==21.2.0` to your `requirements.txt`.

![[Pasted image 20231010122234.png|500]]

The format for all the packages in the `requirements.txt` is:

`gunicorn==<version number>`

Next, we need to tell our hosting provider about our gunicorn server, what our app is called, and how to run our Flask app. We do that using a config file called a Procfile.

## Create a Procfile

Create a new file in the project top-level folder called Procfile. When you create the new file, PyCharm will prompt you to track the new file under git version control. Agree by clicking add.

NOTE: make sure you spell the name of the file exactly as you see above, with a capital P and no file extension.

Type the following into the Procfile:

`1. web: gunicorn main:app`

This will tell our hosting provider to create a web worker that is able to receive HTTP requests. The Procfile also says to use gunicorn to serve your web app. And finally it specifies the Flask app object is the main.py file. That way the hosting provider knows about the entry point for the app and what our app is called.

![[Pasted image 20231010122253.png|500]]

NOTE: If your app is not inside a file called main.py then you should change main to your file name.

## Commit your changes

At this point you made some changes in the main.py with your environment variables and created a new file in the project. Go to the Commit Tool and save your changes under version control.

![[Pasted image 20231010122309.png|250]]