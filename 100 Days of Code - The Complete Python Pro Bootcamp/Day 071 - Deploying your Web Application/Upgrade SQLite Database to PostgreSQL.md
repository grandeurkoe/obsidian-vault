# Upgrade SQLite Database to PostgreSQL

You might be wondering what else we might possibly need to do after all that. There's just one last thing. When we were coding and testing our Flask website, it was nice to use a simple database like SQLite. But SQLite is a file-based database.

This is its strength and weakness. It's a strength because while we're coding up our database and debugging, it's really useful to be able to open the SQLite file using DB Viewer and see how our data looks.

![[Pasted image 20231010123347.png|500]]

But it's also a weakness because once it's deployed with a hosting provider (like Heroku or Render) the file locations are shifted around every 24 hours or so. This means that your database might just get wiped every day. That will mean some very unhappy users. [(Heroku explainer here).](https://devcenter.heroku.com/articles/sqlite3)

So we've got to put on our big-boy/big-girl pants and upgrade our simple SQLite database to PosgreSQL, a database that can handle millions of data entries and reliably delivers data to users.

Luckily, because we used SQLAlchemy to create our Flask app, there's nothing we need to change in terms of code. We just need to set up the PostgreSQL database.

## Create a new Postgres Database

Create a new Postgres database from the website menu.

![[Pasted image 20231010123404.png|500]]

Next, you will see a form. All you need to do is pick a name for the database and create it.

![[Pasted image 20231010123428.png|500]]

## Copy the internal database URL

Once you've created your database, go and find the Internal Database URL in the Info section. You might have to wait a little while until your database is created.

![[Pasted image 20231010123442.png|500]]

Afterwards, simply copy this URL. You will shortly use this as an environment variable.

![[Pasted image 20231010123455.png|500]]

## Set your SQLALCHEMY_DATABASE_URI environment variable

Go back to your web service settings called "environment".  Create an environment variable that matches the name of the key you're using in the main.py.

![[Pasted image 20231010123507.png|500]]

Paste your internal database URL as the key value. It should look something like this:

postgres://example_ig2c_user:u0E_lots_of_Symbols_here@dpg-c_more_symbols3bj85d0-a/example_ig2c

You just need to make one small modification. Change the first part from postgres to postgresql. The URI has to start with "postgresql" because this is [required by SQLAlchemy](https://docs.sqlalchemy.org/en/20/core/engines.html#postgresql):

postgresql://example_ig2c_user:u0E_lots_of_Symbols_here@dpg-c_more_symbols3bj85d0-a/example_ig2c

![[Pasted image 20231010123521.png|500]]