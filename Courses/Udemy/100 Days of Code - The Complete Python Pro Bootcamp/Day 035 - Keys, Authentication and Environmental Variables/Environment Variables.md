# Environment Variables

Environment Variables are the variables set in the environment in which you code runs.

Environment variables have two use cases -

1. Convenience - When you deploy a large application the process is quite complicated and you don't want to mess with the codebase. Instead you can change the environment variables. The variables that are likely to keep changing can be said as environment variables. You can modify environment variables without changing the code base.
2. Security - If you want to publish your codebase online but you don't want your authentication keys to be exposed, then you can separate these authentication keys from the codebase and state them as environment variables.

You can create environment variables by typing this in terminal -
```cmd
export OWM_API_KEY = 95dfsf4df8s46fs
```

For Pycharm, go to Edit configuration and the add Environment variables there.

To get the environment variables, first import the os library and then type -
```python
api_key = os.environ.get("OWM_API_KEY")
# OR
api_key = os.environ["OWM_API_KEY"]
```