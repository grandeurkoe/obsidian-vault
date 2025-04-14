# Templating with Jinja

[Jinja](https://jinja.palletsprojects.com/en/2.11.x/templates/) is a templating language build for python.

Jinja allows us to load the contents of our website dynamically.

Jinja allows us to add python code into out [html template](Rendering%20HTML%20and%20Static%20Files.md) files.

Anything between two curly braces is evaluated as python code.

These `{{ }}` are called as Jinja markers.

For multiline Python code, we encompass the code within `{% %}`.

Use the `url_for()` function for building url in an HTML file.