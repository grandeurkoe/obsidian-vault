# SQLAlchemy

Writing SQL commands are complicated and error-prone. It would be much better if we could just write Python code and get the compiler to help us spot typos and errors in our code. That's why [SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/3.1.x/quickstart/) was created.

SQLAlchemy is defined as an ORM (Object Relational Mapping) library. This means that it's able to map the relationships in the database into Objects. Fields become Object properties. Tables can be defined as separate Classes and each row of data is a new Object.

Install the required packages flask and flask_sqlalchemy. Note, you'll need to install the flask_sqlalchemy package (not the SQLAlchemy package). Instead of using PyCharm’s red lightbulb fix to install the required package I recommend you run:

```cmd
pip install -U Flask-SQLAlchemy
```

Import the Flask and SQLAlchemy classes from each.
```python
from flask import Flask
from flask_sqlalchemy import SQLAlchemy
```