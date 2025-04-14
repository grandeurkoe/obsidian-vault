# Files, Directories and Paths

## Files

To open a file we use the in-built `open()` function. Default mode option in `open()` function is 'r' i.e., reading
```python
file = open("filename.txt")
```

To read the file we use the `read()` function.
```python
contents = file.read()
```

To close the file we use the in-build `close()` function.
```pyton
file.close()
```

If you don't want to deal with the hassle of having to close the file manually every damn time then you can use the 'with' keyword.
```python
with open("file.txt") as file:
	contents = file.read()
	print(contents)
```

To write a file we use the `write()` function. Before you write anything to the file, make sure that you opened the file in write mode.
```python
with open("file.txt", mode="w") as file:
	file.write("Hey, Meowya.")
```

If you try to open a file that doesn't exist then the compiler will create the file itself.

## Directories

A directory is a collection of files and subdirectories.

A directory inside another directory is called a subdirectory.

## Paths

### Absolute Path

Let's assume that we have a Coffee Machine project. The file path to main.py of this project is `C:\Users\mailm\PycharmProjects\The Coffee Machine\main.py`.

The above file path is called an Absolute File Path.

The root for Meowya's PC is `C:\Users\mailm`.

So to get to The Coffee Machine directory we open cmd prompt and type `cd  PycharmProjects\The Coffee Machine`.

### Relative Path

In a complex file structure with a huge number of directories and subdirectors, you can see how writing absolute file path can become tedious. Also, the root path might vary from computer to computer. So, if you were to transfer your project to a different computer and you used absolute file path then your project will not execute successfully. A good way to prevent this is to use Relative file path.

Let's assume that we are inside the Quiz Game Project. The absolute path for the main.py of this project is `C:\Users\mailm\PycharmProjects\The Quiz Game\main.py`.

You want to get to the main.py of Snake Game Project whose absolute path is `C:\Users\mailm\TemporaryProjects\Snake Game\main.py.`.

Since we are inside the Quiz Game Project. The relative file path for the main.py of this project is `./main.py OR main.py`.

So, the relative file path from the main.py of Quiz Game Project to main.py of Snake Game Project is `../TemporaryProjects\Snake Game\main.py.`.

Here `../` goes up one folder.