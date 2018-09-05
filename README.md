# python_website

### introduction to website development with python

- setup your python environment
- build a simple website using python and flask
- use database
- rsync your code to your server
- setup the website to be served under nginx

---

### setup your python environment
From Ubuntu ver 16 check that you have Python 3.5
```
$ python3 -V
```
### Setting Up a Virtual Environment
Virtual environments enable you to have an isolated space on your computer for Python projects, ensuring that each of your projects can have its own set of dependencies that won’t disrupt any of your other projects.

Create a folder for your python environments:
```bash
$ mkdir environments
$ cd environments
```

Now install python3 pip
```bash
$ sudo apt-get update

$ python3 -m venv my_env --without-pip
$ cd my_env
$ source bin/activate
$ curl https://bootstrap.pypa.io/get-pip.py | python3
```
By using source bin/activate you have activated your virtual environment and can work on your python project.


### build a simple website using python and flask

Start by installing Flask
```bash
$ pip install Flask
```
Now create the app.py file
```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"

if __name__ == "__main__":
    app.run(host='0.0.0.0')
```
Now, let us extend the code with some links
```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def index():
    return "Index!"

@app.route("/hello")
def hello():
    return "Hello World!"

@app.route("/members")
def members():
    return "Members"

@app.route("/members/<string:name>/")
def getMember(name):
    return name

if __name__ == "__main__":
    app.run(host='0.0.0.0')
```
Follow the guide [here](https://pythonspot.com/flask-web-app-with-python/)
to learn more about python and Flask development


### use database
Start by installing Sqlite
```bash
$ sudo apt-get update.
$ sudo apt-get install sqlite3 libsqlite3-dev
```
---

Next session we will deploy the website to the server and setup an nginx server hosting our python web application

### rsync your code to your server

### setup the website to be served under nginx

---
### First website
In the folder "First website" you will be able to find the structure for a flask website project.
