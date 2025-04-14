# Bootstrap-Flask Supports WTForms

One of the main reasons why we're using [Bootstrap-Flask](https://bootstrap-flask.readthedocs.io/en/stable/) in this project is because it has one of the most convenient methods for generating forms with [WTForms](Flask%20WTForm.md).

Literally, in 1 line of code, you can create your form. It's as simple as:
```html
{‌{ render_form(form) }}
```

What this line of code will do is generate all the labels, inputs, buttons, styling for your form just by taking the WTForm object that was passed to the template (form).

You can simply delete the entire `<form>` element.

![[Pasted image 20231010105146.png|500]]

Then, add a line to import the [render_form()](https://bootstrap-flask.readthedocs.io/en/stable/macros/#render-form) function from bootstrap-flask.

![[Pasted image 20231010105203.png|500]]

Finally, use the `render_form()` to generate your form.

![[Pasted image 20231010105218.png|500]]

Run your code and see the entire form laid out for you with zero effort. Also, check out the error messages from validation!

Now you might wonder, why did I put you through all that hassle to learn how to create a WTForm from scratch when I knew all along that you can just use the Bootstrap-Flask `render_form()`? Because everything is dandy as long as it works. This render_form macro is a black box. It's magic. Which is great, but what happens if your form breaks? What if it's not doing what you expect it to? How would you debug magic?

That's why it's so important to understand how things work under the hood. Once you understand it, you can take all the shortcuts.

You can download the completed project from this lesson's resources.