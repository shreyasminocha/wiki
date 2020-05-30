# Flask

Flask is a web framework for python. If Django is the Express of the python world, Flask is the Koa \(these analogies aren't perfectly accurate, but analogies never are\).

## Hello world

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello world!'
```

-   Set `FLASK_APP` to the name of the file containing the app.
-   Set `FLASK_ENV` to `development` if in dev environment.

Run `flask run` to run the app.

## Path parameters

```python
@app.route('/user/<username>')
def user_profile(username):
    return 'User profile for {}'.format(username)
```

```python
@app.route('/user/<string:username>')
def user_profile(username):
    return 'User profile for {}'.format(username)
```

Converters:

-   `string`
-   `int`
-   `float`
-   `path`
-   `uuid`

## Checking HTTP method

```python
from flask import request

@app.route('/resource/<id>', methods=['GET', 'PUT'])
def resource(id):
    return resource.method
```

## Trailing slash vs no trailing slash

In the following example, the canonical URL is `/path/`. `/path` will redirect to `/path/`

```python
app.route('/path/')
```

The opposite is true in the following example.

```python
app.route('/path/')
```

## URL building

```python
from flask import url_for
```

```python
@app.route('/')
def index():
    ...

@app.route('/dashboard')
def dashboard():
    ...

@app.route('/user/<username>')
def profile():
    ...

url_for('index') # '/'
url_for('dashboard', page='2') # '/dashboard?page=2'
url_for('profile', username='ansh') # '/user/ansh'
```

## Static files

In production, web server software should serve static files. In development, flask is configured to automatically serve files in `static` under `/static`.
