# Unescaping HTML Entities

HTML Entities are characters that are reserved in HTML so as to not be confused for HTML code.

For example, '<' symbol is part of the HTML code. If we want to print '<' we can write '&lt;' instead.

To unescape HTML entities we need to import the html module.
```python
import html
```

Now, we call the `unescape(argument)` function. This function unescapes the argument passed to this function.
```python
html.unescape(argument)
```