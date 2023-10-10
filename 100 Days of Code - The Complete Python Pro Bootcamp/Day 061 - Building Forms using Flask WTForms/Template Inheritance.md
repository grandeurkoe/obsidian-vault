# Template Inheritance

However, often you'll find that you actually want to use the same design template for your entire website, but you might need to change some code in your header or footer. In these cases, it's better to use Template Inheritance instead.

Template inheritance is similar to Class inheritance, you can take a parent template and extend its styling in your child web pages.

For example, if we create a base.html file that has the following code:

```html
1. <!DOCTYPE html>
2. <html lang="en">
3. <head>
4.     <meta charset="UTF-8">
5.     <title>{% block title %}{% endblock %}</title>
6. </head>
7. <body>
8.     {% block content %}{% endblock %}
9. </body>
10. </html>
```

It has predefined areas (or blocks) where new content can be inserted by a child webpage inheriting from this template.

We could re-write the success.html page to inherit from this base.html template:

```html
1. <!-- #1. This line of code tells the templating engine (Jinja) to use "base.html" as the template for this page. -->
2. 
3. {% extends "base.html" %}
4. 
5. <!-- #2. This block inserts a custom title into the header of the template. -->
6. {% block title %}Success{% endblock %}
7. 
8. <!-- #3.This block provides the content of the website. The part that is going to vary between webpages. -->
9. {% block content %}
10.    <div class="container">
11.       <h1>Top Secret </h1>
12.       <iframe src="https://giphy.com/embed/Ju7l5y9osyymQ" width="480" height="360" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
13.       <p><a href="https://giphy.com/gifs/rick-astley-Ju7l5y9osyymQ">via GIPHY</a></p>
14.    </div>
15. {% endblock %}
```