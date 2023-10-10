# Parsing HTML and Making Soup

Start by importing the BeautifulSoup class from the bs4 package by typing -
```python
from bs4 import BeautifulSoup
```

To open an HTML file type -
```python
# Set the encoding argument to 'utf8' to prevent the UnicodeDecodeError.
with open("website.html", encoding='utf8') as website:
	contents = website.read()
	print(contents)
```

Create an object of object of BeautifulSoup like this -
```python
soup = BeautifulSoup(contents, "html.parser")
```

To get data from a certain html element you can type this -
```python
print(soup.title)
```

To get the name of the title element type this -
```python
print(soup.title.name)
```

To get the contents of the title element type this -
```python
print(soup.title.string)
```

To prettify the contents of the html file on the console type this -
```python
print(soup.prettify())
```