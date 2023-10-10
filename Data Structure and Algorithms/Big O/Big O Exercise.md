# Big O Exercise

## Exercise 01

```python
def fun_challenge():
    a = 10    # O(1)
    a = 50 + 3    # O(1)
    for i in range(len(input)):    # O(n)
        another_function()    # O(n)
        stranger = True    # O(n)
        a += 1    # O(n)
    return a    # O(1)
# BIG O(3 + 4n) ->  BIG O(n)
```

## Exercise 02

```python
def another_fun_challenge(input):
  a = 5    # O(1)
  b = 10    # O(1)
  c = 50    # O(1)
  for i in input:    # O(n)
    x = i + 1    # O(n)
    y = i + 2    # O(n)
    z = i + 3    # O(n)
  for j in input:    # O(n)
    p = j * 2    # O(n)
    q = j * 2    # O(n)
  who_am_i = "I don't know"    # O(1)
# BIG O(4 + 7n) ->  BIG O(n)
```

## Exercise 03

```python
boxes = [1, 2, 3, 4, 5]
def log_all_pairs(boxes):
    for i in boxes:
        for j in boxes:
            print(f"({i},{j})")
log_all_pairs(boxes)
# BIG O(n*n) or O(n^2)
```