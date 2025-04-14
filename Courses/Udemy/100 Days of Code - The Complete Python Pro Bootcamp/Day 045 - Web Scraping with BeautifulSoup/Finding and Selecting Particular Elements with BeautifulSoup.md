# Finding and Selecting Particular Elements with BeautifulSoup

To get the contents of the `<p></p>` element we type this -
```python
print(soup.p)
```

But the above code will only give me data about the first `<p>` element. 

To get all data of a particular element type this -
```python
print(soup.find_all(name="p")
```