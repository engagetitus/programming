
# Module 2: Intermediate Programming Concepts

## Lesson 5: CSS Basics for Styling HTML

### Topics
1. Introduction to CSS
2. Styling Text and Layouts
3. Adding CSS to HTML Pages
4. Introduction to Bootstrap
5. Guide to Bootstrap Classes and IDs

---

### 1. Introduction to CSS

#### Overview
CSS (Cascading Style Sheets) is used to style and layout web pages. It controls the appearance of HTML elements.

#### CSS Syntax
```css
selector {
    property: value;
}
```

#### Example
```css
p {
    color: blue;
    font-size: 16px;
}
```

---

### 2. Styling Text and Layouts

#### Styling Text

##### Changing Text Color
```css
h1 {
    color: red;
}
```

##### Changing Font Size
```css
p {
    font-size: 18px;
}
```

##### Changing Font Family
```css
body {
    font-family: Arial, sans-serif;
}
```

#### Styling Layouts

##### Margin and Padding
```css
div {
    margin: 20px;
    padding: 10px;
}
```

##### Border
```css
div {
    border: 1px solid black;
}
```

##### Width and Height
```css
div {
    width: 300px;
    height: 200px;
}
```

##### Display Property
```css
/* Block element */
div {
    display: block;
}

/* Inline element */
span {
    display: inline;
}

/* Inline-block element */
img {
    display: inline-block;
}
```

##### Positioning
```css
/* Relative positioning */
div {
    position: relative;
    top: 10px;
    left: 20px;
}

/* Absolute positioning */
div {
    position: absolute;
    top: 50px;
    left: 100px;
}

/* Fixed positioning */
div {
    position: fixed;
    bottom: 0;
    right: 0;
}
```

##### Flexbox
```css
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.item {
    flex: 1;
}
```

---

### 3. Adding CSS to HTML Pages

#### Inline CSS
```html
<p style="color: red;">This is a red paragraph.</p>
```

#### Internal CSS
```html
<head>
    <style>
        p {
            color: blue;
        }
    </style>
</head>
<body>
    <p>This is a blue paragraph.</p>
</body>
```

#### External CSS
```html
<head>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
    <p>This is a paragraph styled by an external CSS file.</p>
</body>
```

#### Example External CSS File: `styles.css`
```css
p {
    color: green;
}
```

---

### 4. Introduction to Bootstrap

#### Overview
Bootstrap is a popular CSS framework for developing responsive and mobile-first websites. It includes predefined classes and components that make web development faster and easier.

#### Adding Bootstrap to Your Project
You can add Bootstrap to your project by including the following CDN link in the `<head>` of your HTML document:
```html
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
```

---

### 5. Guide to Bootstrap Classes and IDs

#### Grid System
Bootstrap’s grid system uses a series of containers, rows, and columns to layout and align content.
```html
<div class="container">
    <div class="row">
        <div class="col-sm-4">Column 1</div>
        <div class="col-sm-4">Column 2</div>
        <div class="col-sm-4">Column 3</div>
    </div>
</div>
```

#### Typography
```html
<p class="text-primary">This is a primary text.</p>
<p class="text-success">This is a success text.</p>
<p class="text-danger">This is a danger text.</p>
```

#### Buttons
```html
<button class="btn btn-primary">Primary Button</button>
<button class="btn btn-success">Success Button</button>
<button class="btn btn-danger">Danger Button</button>
```

#### Forms
```html
<form>
    <div class="form-group">
        <label for="email">Email address:</label>
        <input type="email" class="form-control" id="email">
    </div>
    <div class="form-group">
        <label for="pwd">Password:</label>
        <input type="password" class="form-control" id="pwd">
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

#### Navigation Bar
```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
            <li class="nav-item active">
                <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#">Features</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#">Pricing</a>
            </li>
        </ul>
    </div>
</nav>
```

#### Cards
```html
<div class="card" style="width: 18rem;">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
</div>
```

---

### Conclusion
CSS is essential for designing and styling web pages, and Bootstrap provides a powerful framework to streamline the process. By mastering these concepts, you can create visually appealing and responsive web pages efficiently.

---
