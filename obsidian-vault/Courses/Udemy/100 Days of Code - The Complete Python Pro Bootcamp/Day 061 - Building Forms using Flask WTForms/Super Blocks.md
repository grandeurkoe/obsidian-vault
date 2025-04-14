# Super Blocks

When we inherit from Python classes, you often see `super.init()`

The super keyword refers to the parent that the child is inheriting from. e.g If Simba inherits from Mufasa, then Mufasa is the super.

![[Pasted image 20231009155019.png|200]]

When we are inheriting templates. Sometimes, there's some part of the [template](Templating%20with%20Jinja.md) that we want to keep, but we also want to add to it. So we can use super blocks in this case.

Add the following code to your base.html:
```html
1. <style>
2. {% block styling %}
3. body{
4.     background: purple;
5. }
6. {% endblock %}
7. </style>
```

![[Pasted image 20231010105939.png|500]]

I named this block "styling" but you can call it anything you want.

Just make sure that you close all blocks with `{% endblock %}`

Now if you reload your website, you should see that both the success page and the denied page will have a purple background. (We covered inline, internal and external styling in the CSS section of this course - Day 43).

![[Pasted image 20231010105957.png|500]]

So now you can see how easy it is to modify all web pages in your website if you use the same template. But what if on the denied page we also wanted to make the `<h1>` red? We would need to modify the internal styling in the `<style>` tag. But that code is in the base.html template. Luckily we have super blocks.

On the denied.html page, add a super block using `{‌{ super() }}`, this will inject all the code in the styling block to this child page. Then afterwards before the `{% endblock %}`, we can add some more styling to change the color of the `<h1>`.

```html
1. {% block styling %}
2.    {‌{ super() }}
3.    h1 {
4.       color:red;
5.    }
6. {% endblock %}
```

![[Pasted image 20231010110016.png|500]]