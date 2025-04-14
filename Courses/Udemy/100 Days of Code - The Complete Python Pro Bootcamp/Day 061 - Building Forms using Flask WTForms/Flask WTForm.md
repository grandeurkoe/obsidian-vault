# Flask WTForm

[Flask WTForm](https://wtforms.readthedocs.io/en/3.0.x/) has the follows advantage over using HTML forms -

- Easy Form Validation - Makes sure the user is entering data in the required format in all the required fields. e.g. checking that the user's email entry has a "@" and a "." at the end. All without having to write your own validation code.
- Less Code - If you have a number of forms in your website, using WTForm can dramatically reduce the amount of code you have to write (or copy & paste).
- Built in CSRF Protection - CSRF stands for [Cross Site Request Forgery](https://owasp.org/www-community/attacks/csrf), it's an attack that can be made on website forms which forces your users to do unintended actions (e.g. transfer money to a stranger) or compromise your website's security if it's an admin.