# Scope

Python doesn't have block scope.

In Python, the term "scope" refers to the region of a program where a particular variable can be accessed or modified. It determines the visibility and lifetime of variables. Python has two main types of scope: global scope and local scope.

1. **Global Scope:**
   - Variables defined outside any function or class have global scope.
   - They can be accessed from anywhere in the code, both inside and outside functions.
   - To create a global variable inside a function, you can use the `global` keyword.

    ```python
    global_variable = 10

    def my_function():
        global global_variable
        print(global_variable)

    my_function()  # Output: 10
    ```

2. **Local Scope:**
   - Variables defined inside a function have local scope.
   - They are only accessible within that function.
   - Each function creates its own local scope, and variables in one function do not interfere with variables in another function.

    ```python
    def my_function():
        local_variable = 5
        print(local_variable)

    my_function()  # Output: 5

    # This would result in an error because local_variable is not accessible outside the function
    # print(local_variable)
    ```

3. **Enclosing (or Nonlocal) Scope:**
   - This scope is applicable when you have a nested function.
   - Variables defined in the enclosing function of the nested function can be accessed in the nested function, provided you use the `nonlocal` keyword.

    ```python
    def outer_function():
        outer_variable = 20

        def inner_function():
            nonlocal outer_variable
            print(outer_variable)

        inner_function()  # Output: 20

    outer_function()
    ```

4. **Built-in Scope:**
   - Variables or names defined in the Python built-in module have a built-in scope.
   - These include functions like `print()` and constants like `True` and `False`.

    ```python
    print(max([1, 2, 3]))  # Output: 3
    ```

Understanding scope is crucial to avoid naming conflicts and to properly organize your code. When you use a variable, Python looks for it in the local scope first, then in enclosing scopes, and finally in the global scope. If the variable is not found in any of these scopes, Python raises a `NameError`.
## Global Variable

In Python, a global variable is a variable that is defined outside of any function and is accessible throughout the entire code, both inside and outside functions. When a variable is declared as global within a function using the `global` keyword, it means that the function can modify the global variable.

Here's an example to illustrate global variables in functions:

```python
# Global variable
global_variable = 10

def my_function():
    # Accessing the global variable
    print("Inside the function:", global_variable)

    # Modifying the global variable
    global global_variable
    global_variable = 20

# Calling the function
my_function()

# Accessing the global variable outside the function
print("Outside the function:", global_variable)
```

Output:

```
Inside the function: 10
Outside the function: 20
```

In this example:

1. `global_variable` is declared outside any function, making it a global variable.

2. Inside `my_function()`, the global variable is accessed and printed. It is then modified using the `global` keyword.

3. After calling the function, the value of the global variable has changed, and this change is visible outside the function as well.

Keep in mind that modifying global variables within functions can lead to unexpected behavior and make code harder to understand, especially in larger programs. It's often considered good practice to avoid excessive use of global variables and, instead, use function parameters and return values to manage data flow. Global variables should be used sparingly and with care.

## Global Constants

Global constants are variables whose value you don't want to change throughout the program.

Declaring a global constants look something like this -
```python
# Write PI in uppercase.
PI = 3.14159 
```

Declare the global constant with capital letters.