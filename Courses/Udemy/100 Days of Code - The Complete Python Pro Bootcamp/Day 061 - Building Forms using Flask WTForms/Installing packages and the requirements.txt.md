# Installing packages and the requirements.txt

The requirements.txt file is a file where you can specify all the dependencies (the installed packages that your project depends on) and their versions. This means that you can share your project without all the installed packages, making it a lot more lightweight. When someone downloads your project (like you have done here), the requirements.txt file tells their code editor which packages need to be installed.

To install a particular package you can use the Terminal. To install Flask-WTF you would use the pip install command.
```cmd
pip3 install Flask-WTF
```

You can install all the required packages listed in the requirements.txt file for the project at the same time: 

On Windows type:
```cmd
python -m pip install -r requirements.txt
```

To create a requirements.txt file automatically type - 
```cmd
pip3 freeze > requirements.txt
```