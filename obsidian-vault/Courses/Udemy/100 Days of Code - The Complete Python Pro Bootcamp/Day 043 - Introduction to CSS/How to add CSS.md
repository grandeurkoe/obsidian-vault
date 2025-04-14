# How to add CSS?

There are three ways to add CSS on your website -

![[Pasted image 20231010101112.png|500]]

Inline CSS goes in the same line as the HTML element. Here style is a global attribute available to all tags. All CSS is added to this style attribute.

![[Pasted image 20231010101135.png|300]]

Inline CSS is useful when you want to add CSS to a single element in an HTML file.

Internal CSS is implemented using the style element. The style element is encompassed inside the head element. Here html is the selector, background is the property and red is the value.

![[Pasted image 20231010101226.png|300]]

Internal CSS is useful when you want to add CSS to a single document.

External CSS are a completely separate file than the HTML file. External CSS files have a .css extension.

![[Pasted image 20231010101309.png|300]]

To connect an external CSS file to our HTML file we use the link element inside the head element. The link element is a void element.

In the link element there are two important attributes -

1. rel - This defines the relationship between the linked file and HTML file.
2. href - Where is the CSS file located.