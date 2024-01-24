## Topics 

- [What is Flask](#what-is-flask)
- [Install Virtual Environment](#Install-Virtual-Environment)
- [How to Install Flask](#install-flask)
- [How check Flask  Version](#Pip-version)
- [A mini_Flask application](#a-minimal-app)
- [Flask Project Structure](#flask-project-structure) - a few options
- (WIP) [Flask Bootstrap Sample](#flask-bootstrap-sample) - a simple project built with Bootstrap
- (WIP) [Jinja Template](#jinja-template) - how to render HTML pages efficiently

<br />

## What is Flask

*Flask is a lightweight web application framework. It is designed to make getting started quick and easy, with the ability to scale up to complex applications.
Compared to [Django](https://www.djangoproject.com/), Flask provides a lightweight codebase and more freedom to the developer.*

## Virtual Environment
*-We use a module named virtualenv which is a tool to create isolated Python environments. virtualenv creates a folder that contains all the necessary executables to use the packages that a Python project would need.*

*-A Python Virtual Environment is an isolated space where you can work on your Python projects, separately from your system-installed Python.*

*-You can set up your own libraries and dependencies without affecting the system Python.*

*-We will use virtualenv to create a virtual environment in Python.*

## Why do we need a virtual environment?

*-Imagine a scenario where you are working on two web-based Python projects one of them uses Django 4.0 and the other uses Django 4.1 (check for the latest Django versions and so on). In such situations, we need to create a virtual environment in Python that can be really useful to maintain the dependencies of both projects.*

### Installing Virtula environment
```python
#Installing Virtula environment
pip install virtualenv
```
### Call Virutal Environment
```python
#Call Virutal Environment and it's  local directory Name  Like--- Venv or Guru or Data etc....
virtualenv venv
```
### Activate a virtual environment
```python
#Activate a virtual environment based on your OS
For windows > venv\Scripts\activate
For linux > source ./venv/bin/activate
```

## Install Flask

*The easiest way to install [Flask](https://palletsprojects.com/p/flask/) is to use [PIP](https://pip.pypa.io/en/stable/quickstart/) the official package-management tool.*

### Install Flask Command
```python
pip install Flask
```

<br />

## How to check Flask version

*Open a Python console or platoform (type python in terminal) and check the installed version as below:*

```python 

import flask
flask_version = flask.__version__
print(f"Installed Flask version: {flask_version}")

       Or
flask --version

```
# Mini App

[Code Here ⚙️](/minimal_app)

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"

if __name__=="__main__":
    app.run()

```

#### So what did that code do?

*1. First we imported the Flask class. An instance of this class will be our WSGI application.*

*2. Next we create an instance of this class. The first argument is the name of the application’s module or package. __name__ is a convenient shortcut for this that is appropriate   for most cases. This is needed so that Flask knows where to look for resources such as templates and static files.*

*3. We then use the route() decorator to tell Flask what URL should trigger our function.*

*4. The function returns the message we want to display in the user’s browser. The default content type is HTML, so HTML in the string will be rendered by the browser.*

<hr>

# Debug Mode

[Code Here ⚙️](/debug_mode)

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"

# debug mode running on 8000 port
if __name__=="__main__":
    app.run(debug=True, port=8000)
 ```
*> The flask run command can do more than just start the development server. By enabling debug mode, the server will automatically reload if code changes, and will show an          interactive debugger in the browser if an error occurs during a request.*

*> Warning ⚠️*
*> The debugger allows executing arbitrary Python code from the browser. It is protected by a pin, but still represents a major security risk. Do not run the development server or   debugger in a production environment.*

<hr>
