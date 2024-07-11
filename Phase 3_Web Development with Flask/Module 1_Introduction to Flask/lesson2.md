### Phase 3: Web Development with Flask

#### Module 1: Introduction to Flask

---

### Lesson 2: Routing and Views

#### URL Routing

URL routing in Flask is essential for mapping URLs to specific functions (views) that handle requests and generate responses. This allows you to create dynamic web applications with different endpoints.

1. **Basic Routing**

   - **Example:**
     ```python
     from flask import Flask

     app = Flask(__name__)

     @app.route('/')
     def index():
         return 'Hello, World!'

     @app.route('/about')
     def about():
         return 'This is the About page.'

     if __name__ == '__main__':
         app.run(debug=True)
     ```

   - **Explanation:**
     - `@app.route('/')`: Maps the root URL (`'/'`) to the `index` function, which returns a simple greeting.
     - `@app.route('/about')`: Maps the `'/about'` URL to the `about` function, displaying information about the application.

2. **Dynamic Routing**

   - **Example:**
     ```python
     @app.route('/user/<username>')
     def profile(username):
         return f'Hello, {username}!'
     ```

   - **Explanation:**
     - `<username>` is a dynamic part of the URL, passed as an argument to the `profile` function. This allows for personalized responses based on the URL parameter.

3. **URL Building**

   - Flask provides the `url_for()` function to dynamically build URLs for view functions.

   - **Example:**
     ```python
     from flask import Flask, url_for

     app = Flask(__name__)

     @app.route('/')
     def index():
         return 'Hello, World!'

     @app.route('/about')
     def about():
         return 'This is the About page.'

     @app.route('/contact')
     def contact():
         return 'Contact page'

     if __name__ == '__main__':
         app.run(debug=True)
     ```

     - `url_for('index')`: Generates the URL for the `index` function, facilitating navigation within the application.

#### Rendering HTML Templates

Flask supports rendering HTML templates to separate the presentation layer from the application logic, enabling more maintainable and scalable web applications.

1. **Creating Templates**

   - Create a `templates` folder in the project directory to store HTML templates.

   - **Example Structure:**
     ```
     /project
     ├── app.py
     ├── templates
     │   ├── index.html
     │   └── profile.html
     ```

2. **Rendering Templates**

   - **Example:**
     ```python
     from flask import Flask, render_template

     app = Flask(__name__)

     @app.route('/')
     def index():
         return render_template('index.html')

     @app.route('/user/<username>')
     def profile(username):
         return render_template('profile.html', username=username)

     if __name__ == '__main__':
         app.run(debug=True)
     ```

     - `render_template('index.html')`: Renders the `index.html` template located in the `templates` folder when accessing the root URL (`'/'`).
     - `render_template('profile.html', username=username)`: Passes the `username` variable to the `profile.html` template for dynamic content rendering.

3. **Template Inheritance**

   - Allows for reusing HTML structure and reducing redundancy across multiple templates.

   - **Base Template (`base.html`):**
     ```html
     <!DOCTYPE html>
     <html lang="en">
     <head>
         <meta charset="UTF-8">
         <title>{% block title %}{% endblock %}</title>
     </head>
     <body>
         <nav>
             <ul>
                 <li><a href="{{ url_for('index') }}">Home</a></li>
                 <li><a href="{{ url_for('about') }}">About</a></li>
                 <li><a href="{{ url_for('contact') }}">Contact</a></li>
             </ul>
         </nav>
         <div>
             {% block content %}{% endblock %}
         </div>
     </body>
     </html>
     ```

   - **Child Template (`index.html`):**
     ```html
     {% extends 'base.html' %}
     {% block title %}Home - My Website{% endblock %}
     {% block content %}
     <h1>Welcome to my website!</h1>
     {% endblock %}
     ```

     - The `extends` keyword inherits the structure from `base.html`, allowing specific content (`{% block content %}`) to be inserted.

#### Practical Examples and Exercises

- **Exercise 1: Dynamic Routing**
  - Implement a route `/user/<username>/profile` that displays a detailed profile page for a given username.

- **Exercise 2: Template Inheritance**
  - Create a base template (`base.html`) with a navigation bar and a child template (`dashboard.html`) that extends `base.html` and displays personalized dashboard content.

#### Deployment Considerations

- **Local Development vs. Deployment**
  - Discuss differences between running Flask in debug mode (`app.run(debug=True)`) locally and deploying on production servers (e.g., using WSGI servers like Gunicorn).

- **Heroku Deployment**
  - Brief overview of deploying Flask applications on Heroku, highlighting `Procfile` configuration and environment variables setup.



---

