## Flask project
- In your flask project, you will need
1. An `app.py` file where all of your python code goes
2. A folder called `templates` where all your HTML templates go
3. A folder called `static` for static files like CSS, JS and images
4. A `requirements.txt` to indicate what third party libraries you would like to use
## Flask template
```Python
# app.py
from flask import Flask
app = Flask(__name__) # convention, tells flask to turn this file into a flask server

@app.route('/')# tells if a visitor goes to our main webpage, run the function
def index():
	return "hello world!" # displays the text hello world

#tells flask if this file is the file that is being run, fire up the web server
if __name__ == '__main__':
	app.run() 
```
## Routing
- We can give different routes after the domain url to lead to different web pages
```Python
#...
@app.route('/')# tells if a visitor goes to our main webpage, run the function
def index():
	return "welcome to my website!" # displays the text hello world

@app.route('/hello')
def hello():
	return "hello world!"
#...
```
- Each route has to be distinct, with distinct function names
## render_template()
- We can return a HTML file using `render_template()`
```html
<!--static/index.html-->
<!DOCTYPE HTML>
<html lang="en-gb">
	<head>
        <meta charset="utf-8">
		<title>hello</title>
	</head>
	<body>
		<h1>Hello, world!</h1>
	</body>
</html>
```
```Python
# app.py
from flask import Flask, render_template
app = Flask(__name__)

@app.route('/')
def index():
	return render_template("index.html") #render the html page


if __name__ == '__main__':
	app.run() 
```
- We can also pass python values and into the template
```html
<!--static/index.html-->
<!DOCTYPE HTML>
<html lang="en-gb">
	<head>
        <meta charset="utf-8">
		<title>hello</title>
	</head>
	<body>
		<h1>Hello, {{ placeholder }}!</h1>
	</body>
</html>
```
```Python
# app.py
from flask import Flask, render_template
app = Flask(__name__)

@app.route('/')
def index():
	name = "neud"
	return render_template("index.html",placeholder = name) #render the html page


if __name__ == '__main__':
	app.run() 
```
- `placeholder` does not have to be called placeholder, the name can be whatever you want
- But, in python, we have to use the name we specified in the html template
- Usually, developers use the same name in the template and the python script to simplify
## requests
### Get
- `GET` requests show up in the url of the website
```HTML
<!--static/index.html-->
<!DOCTYPE HTML>
<html lang="en-gb">
	<head>
        <meta charset="utf-8">
		<title>hello</title>
	</head>
	<body>
		<h1>Hello, {{ placeholder }}!</h1>
	</body>
</html>
```
```python
# app.py
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route('/')
def index():
	name = request.args["name"] #gets the name specified from the request, and stores it as name
	return render_template("index.html", name = name) #render the html page

if __name__ == '__main__':
	app.run()
```
- `request.args` is like a python dictionary
- Now, when people visit `https://yourcoolflaskwebsitehere.com/?name=yournamehere`, they will see their name in the template
- However, if a name is not specified, the program will run into an error
- We can fix this by specifying a default value using `request.args.get()`
- The first parameter is the key of the value, while the second argument is the default value
```python
# app.py
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route('/')
def index():
	name = request.args.get("name", "world") # gets the name specified from the request, if not specified it defaults to world, and stores it as name
	return render_template("index.html", name = name) #render the html page

if __name__ == '__main__':
	app.run() 
```
### Post
- A `POST` request is like a `GET` request, but now it is not appended to the URL
- We need to use a HTML form to make a post request
```html
<!--index.html-->
<!DOCTYPE html>
<html lang="en-gb">
	<head>
        <meta charset="utf-8">
		<title>hello</title>
	</head>
	<body>
		<h1>Please enter your name</h1>
        <form action="greet.html" method="post"> 
            <label>Name:</label>
            <input type="text" name="name">
            <button type="submit">Submit</button>
        </form>
	</body>
</html>
```
- Make a new file called `greet.html` under `templates`
```html
<!--greet.html-->
<!DOCTYPE html>
<html lang="en-gb">
    <head>
        <title>hello</title>
        <meta charset="utf-8">
    </head>
    <body>
        <h1>Hello, {{ name }}!</h1>
    </body>
</html>
```
- Finally, in `app.py`
```python
# app.py
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route('/')
def index():
	return render_template("index.html")

@app.route('/greet', methods = ['POST'])# tell it to only accept post requests
def greet():
    name  = request.form.get("name", "world") # use request.form for post requests
    return render_template('greet.html', name = name)

if __name__ == '__main__':
	app.run() 
```
- We can actually make both go to the same route, and return different web pages for each request method to make the program more streamlined
```html
<!DOCTYPE html>
<html lang="en-gb">
	<head>
        <meta charset="utf-8">
		<title>hello</title>
	</head>
	<body>
		<h1>Please enter your name</h1>
		<!-- update the route to submit the request-->
        <form action="/" method="post"> 
            <label>Name:</label>
            <input type="text" name="name">
            <button type="submit">Submit</button>
        </form>
	</body>
</html>
```
```python
# app.py
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route('/', methods = ["GET", "POST"])
def index():
    if request.method == "GET": # if the request method is get
        return render_template("index.html")
    if request.method == "POST": # if the request method is post
        name = request.form.get("name", "world")
        return render_template("greet.html", name = name)
		

if __name__ == '__main__':
	app.run() 
```
### Differences between get and post
- `GET` is primarily used for fetching data in the server, and the data is transmitted in the URL
- `GET` requests can be bookmarked or shared with others, as the URL contains all the parameters needed to retrieve the data
- Because it is in the URL, there is a limit on the data that can be transmitted
- `POST` requests are used to submit data to the server to perform some action
- The data is transmitted in the request body rather than the URL, making it more secure than `GET` for sensitive information (such as passwords)
- There is no limit on the amount of data that can be transmitted, making it suitable for large data sets
- `POST` requests cannot be bookmarked or shared as the data is not part of the URL however
## Jinja syntax
- Jinja is used with flask to make templates

|Type |Syntax |Examples|
|-|-|-|
|Variables|`{{ }}`|`{{ name }}`|
|Control structures|`{% %}`| `{% if condition %}`, `{% else %}`,`{% endif %}`, `{% for item in items %}`, `{% endfor %}`|
|Comments|`{# #}`| `{# very cool comment #}`
|Inheritance|` {% %}`| `{% extends layout.html %}`|
|Filters| `│`| `{{ name │ lower }}`|

## Extends
- We can write lesser boilerplate code using `{% extends %}`
- Create a new file, called `layout.html`
```html
<!--layout.html-->
<!DOCTYPE html>
<html lang="en-gb">
    <head>
        <title>hello</title>
        <meta charset="utf-8">
    </head>
    <body>
        {% block body %}{% endblock %}
        {# {% block ___ %} the blank can be whatever you name the block #}
    </body>
</html>
```
- Then, in `index.html`
```html
{% extends "layout.html" %}
<!-- tells flask this is supposed to go into layout.html-->
<!-- layout.html has to be in quotes -->
{# The name of the block has to be what you called it in layout.html #}
{% block body %}
<form action = "/" method = "post">
    <label>Name:</label>
    <input name="name" type="text">
    <button type="submit">Greet</button>
</form>
{% endblock %}
```
- We also have to edit `greet.html`
```html
{% extends "layout.html" %}
 
{% block body %}
<h1>Hello {{ name }}!</h1>
{% endblock %}
```
## Variable routes
- We can make flask take in information form the route, and pass it as a variable
```Python
# app.py
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route('/<name>')
def greet(name):
	return render_template("greet.html", name = name)

if __name__ == '__main__':
	app.run()  
```
- Now, when you visit `https://yourcoolflaskwebsitehere.com/yournamehere`, it will show your name!
## url_for()
```python
# app.py
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route("/hello")
def hello():
    return render_template("greet.html")

@app.route("/")
def index():
	return render_template("links.html")

@app.route('/<year>')
def showyear(year):
	return render_template("year.html", year = year)

if __name__ == '__main__':
	app.run()  
```
```html
<!--greet.html-->
<!DOCTYPE html>
<html lang="en-gb">
    <head>
        <title>hello</title>
        <meta charset="utf-8">
    </head>
    <body>
        <h1>Hello world!</h1>
    </body>
</html>
```
```html
<!--year.html-->
<!DOCTYPE html>
<html lang="en-gb">
    <head>
        <title>year</title>
        <meta charset="utf-8">
    </head>
    <body>
        <h1>The year is {{ year }}</h1>
    </body>
</html>
```
```html
<!--links.html-->
<!DOCTYPE html>
<html lang="en-gb">
    <head>
        <title>links</title>
        <meta charset="utf-8">
    </head>
    <body>
        <p>
            <a href="{{ url_for('hello') }}">Hello world</a>
            <!-- pass the python name of the function into url_for() -->
        </p>
        <p>
            <a href="{{ url_for('showyear', year = '2023') }}">Year</a>
            <!-- if we are using variable routes, pass the variable and state its value -->
        </p>
    </body>
</html>
```
- So, by using `url_for()`, It looks at the name of the python function specified ( `greet()` or `year()` ), and goes to the route associated with the function ( `urwebsitehere.com/greet` or `urwebsitehere/2023`)
- We use `url_for()` so that we can change the route and it wont break!
## Filters
```python
# app.py
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route("/<name>")
def length(name):
	return render_template("length.html", name = name)

if __name__ == '__main__':
	app.run()
```
```html
<!--length.html-->
<!DOCTYPE html>
<html>
    <head>
        <title>Hello!</title>
        <meta charset="utf-8">
    </head>
    <body>
        <h1>
            Hello, {{ name }}! Your name is {{ name | length }} characters long
            <!--jinja filters can be used by putting a | after the vairable name-->
        </h1>
    </body>
</html>
```
- Filters can be stacked as such `{{ name|striptages| title}}`
- `lower` makes a string lowercase
- `upper` makes a string uppercase
- `title` makes the first character of every word uppercase
- `length` returns the length of a string/ array
- `safe` is used to indicate a strong should be output as-is, without being escaped
- `safe` is useful is you want to include HTML or other code in your templates that you want to be rendered as HTML or code, rather than being treated as plain text
- `safe` has to be used with caution, especially if the content you are showing has user supplied data, as malicious code can be injected into your page
- A list of filters can be found [here](https://jinja.palletsprojects.com/en/3.1.x/templates/#list-of-builtin-filters)
## if statements
- Jinja also has if statements like python, declared by using `{% if %}`
- If the condition is true, it will show the block inside the if
- We can also have `{% elif %}` and `{% else %}`
- Unlike python, if statements need to be ended with an `{% endif %}`
```python
# app.py
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route("/", methods = ["GET", "POST"])
def index():
	if request.method == "GET":
		return render_template("score.html")
	if request.method == "POST":
		score = request.form.get("score")
		return render_template("score.html", score = score)

if __name__ == '__main__':
	app.run()
```
```html
<!--score.html-->
<!DOCTYPE html>
<html lang="en-gb">
    <head>
        <title>score</title>
        <meta charset="utf-8">
    </head>
    <body>
        <form method="post" action="{{ url_for('index') }}">
            <input type="number" name="score" placeholder="Score">
            <button type="submit">Submit</button>
        </form>
        {% if not score %}

        {% elif score | int < 50 %}
        <p>Your score is {{ score }}. You failed...</p>
        {% else %}
        <p>Your score is {{ score }}. You passed!</p>
        {% endif %}
    </body>
</html>
```
## for statements
- Like python, Jinja also has for loops, declared by using `{% for iterator in object %}`
- It can loop through a dictionary, a list, a tuple, a set and a range object
```python
#app.py
from flask import Flask, render_template, request
app = Flask(__name__)

def get_grade(score):
    if score.isnumeric() == False:
        return
    score = int(score)
    if score > 100 or score < 0:
        return
    elif score >= 70:
        return "A"
    elif score >= 60:
        return "B"
    elif score >= 55:
        return "C"
    elif score >= 50:
        return "D"
    elif score >= 45:
        return "E"
    elif score >= 40:
        return "S"
    else:
        return "U"

results={
    "gp": "",
    "mathemathics": "",
    "computing": "",
    "economics": "",
}

@app.route("/", methods = ["GET", "POST"])
def index():
    if request.method == "GET":
        return render_template("grade.html")
    if request.method == "POST":
        for i in results:
            score = request.form.get(i)
            results[i] = get_grade(score)
        
        for i in results.values():
            print(i,bool(i) )
            if not i:
                return render_template("grade.html")
        return render_template("grade.html", results = results)

if __name__ == "__main__":
    app.run()
```
```html
<!--grade.html-->
<!DOCTYPE html>
<html lang="en-gb">
    <head>
        <title>head</title>
        <meta charset="utf-8">
    </head>
    <body>
        <form method="post", action="{{ url_for('index')}}">
            <table>
                <tr>
                    <td>
                        <label>GP:</label>
                    </td>
                    <td>
                        <input type="number" placeholder="score" name="gp">
                    </td>
                </tr>
                <tr>
                    <td>
                        <label>Mathemathics:</label>
                    </td>
                    <td>
                        <input type="number" placeholder="score" name="mathemathics">
                    </td>
                </tr>
                <tr>
                    <td>
                        <label>Computing:</label>
                    </td>
                    <td>
                        <input type="number" placeholder="score" name="computing">
                    </td>
                </tr>
                <tr>
                    <td>
                        <label>Economics:</label>
                    </td>
                    <td>
                        <input type="number" placeholder="score" name="economics">
                    </td>
                </tr>
            </table>
            <button type="submit">Submit</button>
        </form>
        {% if results %}
            <table>
                {% for i in results %}
                <tr>
                    <td>{{ i | title}}:</td>
                    <td>{{ results[i] }}</td>
                </tr>
                {% endfor %}
            </table>
        {% endif %}
    </body>
</html>
```
## External CSS
- CSS files can be put into the `static` directory
- They can be then accessed using `url_for()`
```python
#app.py
from flask import Flask, render_template
app = Flask(__name__)

@app.route("/")
def index():
    return render_template("index.html")

if __name__ == "__main__":
    app.run()
```
```html
<!--index.html-->
<!DOCTYPE html>
<html lang="en-gb">
    <head>
        <title>wow</title>
        <meta charset="utf-8">
        <link rel="stylesheet" href="{{url_for('static', filename='style.css')}}"></link>
    </head>
    <body>
        <h1>Wow! I'm red!</h1>
    </body>
</html>
```
```css
/* style.css */
h1{
    color: red;
}
```

## File and image upload
- When an `<input>` tag has its type se tot `file`, this allows the user to upload files for submission with the form
- But, for it to work properly, the form must use the `POST` method and include an additional `ectype` attribute that is set to `"multipart/form-data"`
-  `"multipart/form-data"` tells that the form data will be divided into multiple parts, each part containing a portion of the data along with the content type, and then sent to the server
- In flask, the data can be then accessed using `request.files`, allowing you to handle files and other form data that has been sent as part of the form submission
- Make a new directory called uploads
```html
<!--upload_file.html-->
<!DOCTYPE html>
<html>
	<body>
		<h1>File upload</h1>
		
		<form method = "post" enctype="multipart/form-data">
			<input type="file" name="photo" />
			<input type="submit" />		
		</form>
		{% for image in images %}
			<img src="photos/{{ image }}" />
		{% endfor %}
	</body>

</html>
```
```python
#app.py
import os
from flask import Flask, render_template, request, send_from_directory

app = Flask(__name__)

photolist = []

@app.route('/', methods=['GET', 'POST'])
def index():
    if request.method == 'GET':
        return render_template("upload_file.html")

    #post
    image = request.files['photo']
    path = os.path.join('uploads', image.filename) # save the photo to uploads folder
    image.save(path)
    photolist.append(image.filename)
    return render_template('upload_file.html', filename = image.filename, images = photolist)

@app.route('/photos/<filename>')
def get_file(filename):
    return send_from_directory('uploads', filename)

app.run()
```
