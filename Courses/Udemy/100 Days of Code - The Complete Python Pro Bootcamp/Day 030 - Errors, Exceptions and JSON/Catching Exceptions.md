# The try catch except finally Pattern

In programming, if something goes devastatingly wrong in your executable code then we can catch these exception.

The code for catching exceptions look something like this -

1. try: Something that might cause an exception.  
2. except: Do this if there was an exception.  
3. else: Do this if there were no exceptions.  
4. finally: Do this no matter what happens.

The final keyword 'raise' allows us to raise our own exceptions. 

For example -
```python
raise TypeError("There is no TypeError. This is a joke.")
```