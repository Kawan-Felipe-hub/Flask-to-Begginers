# Flask PAGE_WITH_NAME Example

This is a simple Flask application that demonstrates a simple dinamic route creation in a web framework .

---

## Table of Contents
1. [Description](#description)
2. [Usage](#usage)
4. [Code Explanation](#code-explanation)

---

## Description
The purpose of this example is to show how a web application can capture **dynamic parameters from the URL** and display them in a response.  

## Usage
Run the application from the terminal:
```bash
python app.py
```

The Flask development server will start. Open this URL in your browser to see:
<p align="center">
<img width="1149" height="209" alt="image" src="https://github.com/user-attachments/assets/38f6ef03-1807-4b59-8e7f-e2b5e825a90e" />  
</p>
That occurs in the / route, but if you access /Flask_for_beginners, you will see:
<p align="center">
<img width="223" height="41" alt="image" src="https://github.com/user-attachments/assets/7f2e4b00-182d-4fb5-b8ed-c76c0839d159" />
</p>

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
Using dynamic parameters via `<string:name>`, which has the structure `<type:variable_name>` (`<` and `>` indicate dynamic parameters in the URL). 
```python
@app.route("/<string:name>")
```
When a user accesses the dynamic route `/<string:name>`, the application captures the value from the URL and returns a personalized message.  
For example:  
- `/Johnn` → "Hello, John!"  
- `/James` → "Hello, James!"

```python
def show_name(name):
    return f"Hello,{name}"
```
Defines a function that returns the string "Hello, the_name_in_URL" to the browser.
This is the response that the user sees on the web page.

>**Note:**
>The f before the string is used to insert the variable name directly into the string.

```python
if __name__ == "__main__":
    app.run(debug=True)
```

Ensures the Flask server runs only if this script is executed directly, not if it is imported.
Starts the Flask development server:
debug=True enables automatic reload and detailed error messages.

