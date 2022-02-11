# JavaScript (JS)
- JS is a programming language that adds interactivity to webpages
- JS is one of the core technologies of the World Wide Web, alongside HTML and CSS

## Adding JS
- JS code/scripts can be placed in ```<body>``` and/or ```<head>``` section of a HTML page
- placing scripts at the end of the HTML document, just be ```</body>``` improves display speed as code interpretation slows the display
- Add JS to a HTML document  
  1. ***Internal JS***
     - inside the HTML document, the JS code is placed within ```<script>``` tags
  1. ***External JS*** *(recommended)*  
     - ```<script src="./main.js"></script>```
     - separates HTML and JS code, more readeble and maintainable and the JS file is cached improving load speed

## JS Comments
- ```// this is a single line comment```
- ```/* this is a multiline comment */```

## JS Output
- use ```console.log("Hello World");``` to print to console

## JS Variables
- variables act as placeholders, they are reusable
- use ```let``` to declare variables with scope, as opposed to ```var```
- this ```=``` is called the assignment operator
```javascript
let name = "Nkata"
console.log("Hello " + name)
```
- use ```const``` to declare constant variables (these never change)
- ***Date Types*** available in JS include Number, String, Boolean, Undefined and more

## JS Arithmetic Operators
- these are used to perform calculations on numbers
- ```+,-,*,**,/,%,++,--```

## JS Assignment Operators
- used to assign values to variables
- ```=, +=,-=```

## JS Comparison Operators
- used in logical statement to compare variables of the same type
- ```==,===,!=,!==,>,>=,<,<=```

## JS Logical Operatos
- also known as Boolean operators, evaluate an expression and return true or false
- ```&&, ||, !```

## String Concatenation
- we use ```+``` to build strings made of smaller strings, and/or variables

## JS Flow Control
- used to control the flow of a program

### if statement
```javascript
if(condition) {
    // do this
} 
else if (condition) {
    // else do this
}
else {
    // if all the conditions are not met, then do it
}
```

### for loop
```javascript
for(let i=0; i < 5; i++) {
    console.log("index: " + i);
}
```

### while loop
```javascript
let i = 0
while(i < 5) {
    console.log("index: " + i);
    i += 1;
}
```

### do-while loop
```javascript
do {
    // do this
} while(condition);
```

### ```break```
- used to jump out of the loop and continue executing code after the loop
- you can also use a ```return``` statement

### ```continue```
- breaks the current iteration and continues to the next one

## JS Functions
- a function is a block of code designed to perform a particular task, makes our code reusable
```javascript
function sum(num1, num2) {
    return num1 + num2;
}

console.log(sum(2, 3));
```
- ```return``` is used to return a value from a fumction

## JS Arrays
- arrays store multipe values in a single variable
```javascript
names = ["nk", "sk"];

console.log("The First Name Is: " + names[0]);
```
- ```names.push("new_element")``` adds a new element to the array

## JS Timing Events
- allows for JS code to be executed in time intervals
```javascript
let counter = 0;

function repeat() {
    console.log("counter: " + counter);
    counter++;

    setTimeout(repeat, 5000);  // 5 seconds
}

repeat();
```

## The Document Object Model (DOM)
- When you open any webpage in a browser, the HTML of the page is loaded and rendered visually on the screen
- To accomplish this, the browser builds the DOM of that page, which is an object oriented model of its structure
- The DOM of an HTML document can be represented as a ***neststed set of boxes***, with each box representing a HTML tag, see example [here](https://www.w3schools.com/js/js_htmldom.asp)
- JS can be used to manipulate the DOM dynamically

## DOM Tree
- The DOM tree represents a HTML document as a tree
- The elements become interelated nodes in the tree
  - a parent node can have child nodes
  - nodes on the same level are siblings

## The ```document``` object
- used to access all the elements in the DOM 

## Selecting HTML Elements
```javascript
document.getElementById("element_id")  // find an element by ID

document.getElementsByClassName("elements_classname")  // find elements by class name
```

## Getting Input 
```javascript
username = document.getElementById("username");
username = username.value
```

## innerHTML
- once you selected the element you want to work with, you can change it's attributes
- ```document.getElementById("id").innerHTML = "<p>Hello World<p>";```

## Changing Styles
- the style of HTML elements can also be changed using JS ```(element_var.style.color = "blue";)```
-remember that you cannot use dashes (-) in the property names, use camel Case, e.g. ```backgroundColor``` instead of ```background-color```

## Add a Class in JS
```document.getElementById("id").classList.add("custum")```

## Remove a Class in JS
```document.getElementById("id").classList.remove("custum")```

## Events
- you can write JS code that executes when an event occurs
- when an event occurs on a target element, a ***handler function*** is executed
- common events include ```onclick, onload, unonload, onchange```

## Event Listeners
- the ```addEventListener("event", function);```method attaches an event handler to an element without overriding existing event handlers
- ```element.addEventListener("click", popup);```, note that we use ```click not onclick```

## Example
- ***HTML***
```html
<body>
    <p id="id">Click Me</p>

    <script src="./main.js"></script>
</body>
```
- ***JS***
```javascript
click = document.getElementById("id");

function next() {
    click.innerHTML = "Hello World";
}

click.addEventListener("click", next);
```

# Advanced JavaScript

## JavaScript Object Notation *(JSON)*
- JSON is a syntax for storing and exchanging data, JSON is language independent
- Since the JSON format is text only, it can easily be send to and from a server

### JSON Syntax
- data is in name-value pairs
- data is seperated by commas
- curly braces hold objects
- square brackets hold arrays

### A JSON Object
```javascript
Student = {
    "name": "nkata",
    "rank": 3,
    "uni": { // an object
        "name": "UJ",
        "open": false,
        "other": null
    },
    "skills": ["web dev", "design"]  // array
}
```
- to access JSON object value use ```object.property``` for example ```Student.name```
- or use ```object["property"]``` for example ```Student["name"]```
- with nested objects use ```Student.uni.name```
- to modify object properties use ```Student.name = "New Name"```
- to delete object properties use ```del Student.name```
- accessing value in the array use ```Student.skills[0]``` to get the first element in the array ```web dev``` 
- to get the length of the array use ```length = Student.skills.length```

### ```JSON.parse()```
- data received from a server is a string, and so it needs to be converted in JSON format
- use ```JSON.parse(response)``` to parse the data to a JSON object

### ```JSON.stringfy()```
- when sending data to a webserver, it has to be a string
- convert a JS object to a string with ```JSON.stringfy(object)```

## Asynchronous *(async)* JavaScript
- Normally JS code runs one statement at a time, also called single threaded
- This means if a section of code takes time to perform it's function the whole code will be blocked
- with ***async*** we can have code that is non-blocking

## Promises
- allow us to associate handler with an async action's eventual success value or failure reason
- A Promise is an object that can have one of these 3 states
  - ***Pending*** *-* initial state, before the promise suceeds or fails
  - ***Resolved*** *-* a completed promise
  - ***Rejected*** *-* a failed promise

## the Life Cycle of a Promise
- when we request data from a server using a Promise, it will be in ***Pending Mode*** until we receive a response
- if if we suceeded in receiving the data, the Promise will be ***Resolved*** successfully
  - ```then()``` method is executed after a promise is ***resolved***
- but if we dont get the data, then the Promise will be in a ***Rejected*** state
  - ```catch()``` method is executed when a promise is ***rejected***
- if there are multiple requests, then after the first promise is resolved (or rejected), a new process will start, which we can also attach directly by a method called ***chaining***

## The Fetch API
- a promise based API that allows us to make HTTP requests to a server
- ```fetch("link", {options})```
- fetch always suceeds even if we get a 404, hence we always have to check if we had a successful response
- a ```GET``` method
```javascript
fetch("https://jsonplaceholder.typicode.com/users")
   // .then(res => res.json())
   .then(res => {
        if (res.ok) {  // checking if the request was successful
            return res.json()   // returns another promise
        } else {
            // handle error
        }
    })
    .then(data => console.log(data))
    .catch(error => console.log(error))
  ```
- a ```POST``` method *(same for ```PUT, DELETE```)*
```javascript
fetch("https://jsonplaceholder.typicode.com/users", {
    method: "POST",
    headers: {
        "Content_Type": "application/json"
    },
    body: JSON.stringify({
        name: "User 1"
    })
})
   .then(res => res.json())
   .then(data => console.log(data))
   .catch(error => console.log(error))
```