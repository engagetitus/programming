# Module 1: Programming Fundamentals with Python and HTML

## Lesson 5: Basic HTML
### What is HTML?
HTML (HyperText Markup Language) is the standard language for creating web pages and web applications. It describes the structure of a web page and is used to define the content of a web page using a variety of elements and tags.

### What Can HTML Do?
- **Structure Content**: HTML provides the basic structure of a web page, including headings, paragraphs, lists, links, images, and more.
- **Embed Media**: HTML can embed images, audio, video, and other multimedia content.
- **Create Links**: HTML allows you to create hyperlinks to navigate between web pages.
- **Form Input**: HTML forms enable user input and interaction with web services.

### Structure of an HTML Document
#### Basic HTML Document Structure
```
<!DOCTYPE html>
<html>
<head>
    <title>Page Title</title>
</head>
<body>
    <!-- Content goes here -->
</body>
</html>
```
### The `<!DOCTYPE html>` Declaration
Defines the document type and version of HTML.

#### The `<html>`, `<head>`, and `<body>` Tags
- `<html>`: The root element of an HTML document.
- `<head>`: Contains meta-information about the document.
- `<body>`: Contains the content of the document.
### HTML Tags and Elements
#### Understanding Tags and Elements
Tags are the **building blocks** of HTML, used to create elements. Elements represent the structure and content of the web page.

### Common HTML Tags
- Headings: `<h1>`, `<h2>`, `<h3>`, etc.
- Paragraph: `<p>`
- Links: `<a href="url">Link text</a>`
- Images: `<img src="image.jpg" alt="Description">`
- Lists: `<ul>`, `<ol>`, `<li>`
#### Attributes of HTML Tags
Attributes provide **additional information** about HTML elements. They are always included in the opening tag.

```
<a href="https://example.com">Visit Example</a>
<img src="image.jpg" alt="A beautiful scenery">
```
#### Nested HTML Elements
HTML elements can be nested inside other elements to create complex structures.

```
<p>This is a <strong>nested</strong> element.</p>
```
### Creating a Simple Web Page
Putting everything (tags) All Together
```
<!DOCTYPE html>
<html>
<head>
    <title>My First Web Page</title>
</head>
<body>
    <h1>Welcome to My Web Page</h1>
    <p>This is a paragraph of text.</p>
    <a href="https://coding.titus.co.ke">Visit Example</a>
    <img src="coding.jpg" alt="A beautiful scenery">
    <ul>
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
    </ul>
</body>
</html>
```
#### Previewing the Web Page in a Browser
Open the HTML file in a web browser to see the rendered page.

## Challenge 💪
Explore other HTML tags and try to incorporate them into your web page. Some tags to consider:

- `<table>`: Create tables to display data.
- `<form>`: Create forms to collect user input.
- `<video>`: Embed videos.
- `<audio>`: Embed audio files.