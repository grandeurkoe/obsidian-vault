# CRUD Operations with SQLAlchemy

## Create a New Database

```python
1. from flask import Flask
2. from flask_sqlalchemy import SQLAlchemy
3. app = Flask(__name__)
4. app.config['SQLALCHEMY_DATABASE_URI'] = "sqlite:///<name of database>.db"
5. db = SQLAlchemy()
6. db.init_app(app)
```

## Create a New Table

```python
1. class Book(db.Model):
2.     id = db.Column(db.Integer, primary_key=True)
3.     title = db.Column(db.String(250), unique=True, nullable=False)
4.     author = db.Column(db.String(250), nullable=False)
5.     rating = db.Column(db.Float, nullable=False
6. 
7. with app.app_context():
8.     db.create_all()
```

In addition to these things, the most crucial thing to figure out when working with any new database technology is how to CRUD data records.

1. Create
2. Read
3. Update
4. Delete

So, let's go through each of these using SQLite and SQLAlchemy:

## Create A New Record

```python
1. with app.app_context():
2.     new_book = Book(id=1, title="Harry Potter", author="J. K. Rowling", rating=9.3)
3.     db.session.add(new_book)
4.     db.session.commit()
```

NOTE: When creating new records, the primary key fields is optional. you can also write:

```python
new_book = Book(title="Harry Potter", author="J. K. Rowling", rating=9.3)
```

The id field will be auto-generated.

## Read All Records

```python
1. with app.app_context():
2.     result = db.session.execute(db.select(Book).order_by(Book.title))
3.     all_books = result.scalars()
```

To read all the records we first need to create a "query" to select things from the database. When we execute a query during a database session we get back the rows in the database (a Result object). We then use `scalars()` to get the individual elements rather than entire rows.

## Read A Particular Record By Query

```python
1. with app.app_context():
2.     book = db.session.execute(db.select(Book).where(Book.title == "Harry
3. Potter")).scalar()
```

To get a single element we can use `scalar()` instead of `scalars()`.

## Update A Particular Record By Query

```python
1. with app.app_context():
2.     book_to_update = db.session.execute(db.select(Book).where(Book.title ==
3. "Harry Potter")).scalar()
4.     book_to_update.title = "Harry Potter and the Chamber of Secrets"
5.     db.session.commit()
```

## Update A Record By PRIMARY KEY

```python
1. book_id = 1
2. with app.app_context():
3.     book_to_update = db.session.execute(db.select(Book).where(Book.id == book_id)).scalar()
4.     # or book_to_update = db.get_or_404(Book, book_id) 
5.     book_to_update.title = "Harry Potter and the Goblet of Fire"
6.     db.session.commit() 
```

Flask-SQLAlchemy also has some handy [extra query methods](https://flask-sqlalchemy.palletsprojects.com/en/3.0.x/queries/#queries-for-views) like `get_or_404()` that we can use. Since Flask-SQLAlchemy version 3.0 the previous query methods like `Book.query.get()` have been deprecated

## Delete A Particular Record By PRIMARY KEY

```python
1. book_id = 1
2. with app.app_context():
3.     book_to_delete = db.session.execute(db.select(Book).where(Book.id == book_id)).scalar()
4.     # or book_to_delete = db.get_or_404(Book, book_id)
5.     db.session.delete(book_to_delete)
6.     db.session.commit()
```

You can also delete by querying for a particular value e.g. by title or one of the other properties. Again, the `get_or_404()` method is quite handy.