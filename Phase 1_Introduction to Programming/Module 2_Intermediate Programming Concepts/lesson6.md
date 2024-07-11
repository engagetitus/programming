
# Module 2: Intermediate Programming Concepts

## Lesson 6: Introduction to JavaScript for HTML Interaction

### Topics
1. Basic Syntax and Data Types
2. Simple DOM Manipulation
3. Basic Event Handling

---

### 1. Basic Syntax and Data Types

#### Overview
JavaScript is a versatile programming language that can be used for both client-side and server-side development. It is essential for adding interactivity to web pages.

#### Basic Syntax

##### Declaring Variables
```javascript
// Using var (function-scoped)
var x = 10;

// Using let (block-scoped)
let y = 20;

// Using const (block-scoped, constant value)
const z = 30;
```

##### Data Types
- **Number**: Numeric values
- **String**: Text values
- **Boolean**: `true` or `false`
- **Array**: Ordered list of values
- **Object**: Key-value pairs

##### Examples
```javascript
// Number
let num = 42;

// String
let str = "Hello, JavaScript!";

// Boolean
let isTrue = true;

// Array
let arr = [1, 2, 3, 4, 5];

// Object
let person = {
    name: "Charles",
    age: 30,
    city: "Nairobi"
};
```

##### Functions
```javascript
function greet(name) {
    return "Hello, " + name + "!";
}

console.log(greet("Charles")); // Output: Hello, Charles!
```

##### Arrow Functions
```javascript
const add = (a, b) => a + b;
console.log(add(5, 3)); // Output: 8
```

---

### 2. Simple DOM Manipulation

#### Overview
The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content.

#### Selecting Elements
```javascript
// Select by ID
let element = document.getElementById("myElement");

// Select by Class
let elements = document.getElementsByClassName("myClass");

// Select by Tag
let paragraphs = document.getElementsByTagName("p");

// Select using Query Selector
let selectedElement = document.querySelector(".myClass");
let allSelectedElements = document.querySelectorAll(".myClass");
```

#### Changing Content
```javascript
// Change inner HTML
document.getElementById("myElement").innerHTML = "New Content";

// Change text content
document.getElementById("myElement").textContent = "New Text";
```

#### Changing Styles
```javascript
// Change style
document.getElementById("myElement").style.color = "red";
document.getElementById("myElement").style.backgroundColor = "yellow";
```

#### Example HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM Manipulation</title>
</head>
<body>
    <div id="myElement">Original Content</div>
    <button onclick="changeContent()">Change Content</button>

    <script>
        function changeContent() {
            document.getElementById("myElement").innerHTML = "Content Changed!";
        }
    </script>
</body>
</html>
```

---

### 3. Basic Event Handling

#### Overview
Event handling in JavaScript is the mechanism that allows you to capture and respond to user actions like clicks, keyboard presses, and mouse movements.

#### Adding Event Listeners
```javascript
// Add event listener
document.getElementById("myButton").addEventListener("click", function() {
    alert("Button Clicked!");
});
```

#### Common Events
- **click**: User clicks on an element
- **mouseover**: User moves the mouse over an element
- **mouseout**: User moves the mouse away from an element
- **keydown**: User presses a key on the keyboard
- **load**: Web page has finished loading

#### Example HTML with Event Listeners
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Event Handling</title>
</head>
<body>
    <button id="myButton">Click Me</button>

    <script>
        document.getElementById("myButton").addEventListener("click", function() {
            alert("Button Clicked!");
        });
    </script>
</body>
</html>
```

#### Example: Changing Background Color on Button Click
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Change Background Color</title>
</head>
<body>
    <button id="colorButton">Change Background Color</button>

    <script>
        document.getElementById("colorButton").addEventListener("click", function() {
            document.body.style.backgroundColor = "lightblue";
        });
    </script>
</body>
</html>
```

---

### Conclusion
JavaScript is a powerful language that allows you to add interactivity to your web pages. By understanding its basic syntax, manipulating the DOM, and handling events, you can create dynamic and responsive web applications.

---
