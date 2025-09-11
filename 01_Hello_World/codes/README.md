# Flask Hello World Example

This is a simple Flask application that demonstrates a basic "Hello World" web server in Python. It shows how to create a route, define a function, and run the Flask development server.

---

## Table of Contents
1. [Description](#description)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Code Explanation](#code-explanation)

---

## Description
This project is a minimal example of a Flask web application. When you run the code and open your browser at `http://localhost:5000/`, it will display the text:
<p align="center">
  <img width="128" height="49" alt="image" src="https://github.com/user-attachments/assets/de32c321-20bf-481c-9de9-72656119a18e" />
</p>

## Installation

1. Make sure you have **Python 3** installed.  
2. Install Flask using pip:

```bash
pip install Flask
```

## Usage
Run the application from the terminal:
```bash
python app.py
```

The Flask development server will start. Open this URL in your browser to see the message "HelloWorld".

## Code Explanation
```python
from flask import Flask
# Imports the Flask class from the flask package.
```
Flask is the core class used to create a web application in Python.

```python
app = Flask(__name__)
# Creates an instance of the Flask application and stores it in the variable app
```
`__name__` tells Flask which module is running so it can find templates and static files correctly.

>**Note:**  
>### Decorators in Flask
>
>In Flask, a **decorator** is a way to **add extra behavior to a function**, usually to connect it to a specific URL route, **without changing the original function**.
>In Flask, decorators like @app.route() are used to “link” a function to a URL, so when someone visits that URL, the function runs.
>If you use @app.route("/Hello_World"), it links the function right below to the URL http://localhost:5000/Hello_World. In other words, the function runs whenever you access that URL.
```python
@app.route("/")
```
This is a decorator that connects the URL / to the function below.
You can use /Hello_World or any other name in the URL. For example, if you choose /Hello_World, the address will be http://localhost:5000/Hello_World. You can replace it with any name you like.

```python
def hello_world():
    return "HelloWorld"
```
Defines a function that returns the string "HelloWorld" to the browser.
This is the response that the user sees on the web page.
>**Note**
>Instead of returning plain text like return "HelloWorld", it's better to use jsonify("HelloWorld") in web applications. This way, the function returns JSON, which is the standard format for data on the web.
>You need to import jsonify from Flask like this: from flask import Flask, jsonify.

```python
if __name__ == "__main__":
    app.run(debug=True)
```

Ensures the Flask server runs only if this script is executed directly, not if it is imported.
Starts the Flask development server:
debug=True enables automatic reload and detailed error messages.

The server runs at http://127.0.0.1:5000/.


