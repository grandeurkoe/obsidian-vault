# Random Module

## Import random module

To generate random numbers in Python, you need to first import the random module.

To import the random module type -
```python
import random
```

To import a certain function from the random module type -
```python
from random import randint
```

To import everything from the random module type -
```python
from random import *
```

## Get random integer

`randint(start, stop)` - Allows you to generate a random integer between start and stop(i.e., range), including both the upper and lower limit.
```python
import random
random.randint(0, 9)
```

## Get random floating-point number

`uniform(start, stop)` - Allows you to generate a random floating point number between start and stop(i.e., range), including both the upper and lower limit.
```python
import random
random.uniform(0, 9)
```

## Get random element from a list and dictionary

`choice(list_name)` - Allows you to pick a random item from `list_name`.

`choice(list(dict_name.items())` - Allows you to pick a random key from `dict_name`.
```python
import random
my_list = [1, 2, 3]
random.choice(list)
```

`choice(list(dict_name.values())` - Allows you to pick a random value from `dict_name`.