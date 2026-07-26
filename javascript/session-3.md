# JavaScript Module

# Session 3 – DOM Manipulation, Events & Building Interactive Websites

**Duration:** 2 Hours

**Final Project:** Student Registration System

---

# Learning Objectives

By the end of this session, you should be able to:

* Understand what the DOM is.
* Explain how JavaScript interacts with HTML elements.
* Select elements from a webpage using JavaScript.
* Change webpage content dynamically.
* Change CSS styles using JavaScript.
* Respond to user actions using events.
* Handle form input.
* Validate user data.
* Build an interactive Student Registration System.

---

# Before We Begin

So far, you have learned how to write JavaScript code.

You have learned:

* Variables
* Data types
* Operators
* Conditions
* Functions
* Arrays
* Loops
* Objects

However, there is one important question:

**How does JavaScript actually control a webpage?**

For example:

* How does a button know when it has been clicked?
* How does a website change text without refreshing?
* How does a dark mode button change the entire page?
* How does a form know what the user typed?

The answer is:

# The DOM

---

# What is the DOM?

DOM stands for:

**Document Object Model**

The DOM is the browser's representation of your HTML page as objects that JavaScript can interact with.

When the browser loads your HTML:

```html
<h1>Hello World</h1>
```

The browser converts it into a structure JavaScript can understand.

It becomes something like:

```
             Document
                 |
              HTML
                 |
              Body
                 |
               h1
                 |
          "Hello World"
```

JavaScript can then:

* Find elements
* Change elements
* Remove elements
* Create new elements
* Respond to user actions

---

# HTML Before JavaScript

Imagine we have this HTML:

```html
<h1>
Welcome
</h1>
```

The browser displays:

```
Welcome
```

The HTML is static.

It does not change by itself.

---

# JavaScript Changes the Page

JavaScript can modify it:

```javascript
heading.textContent = "Hello JavaScript";
```

Now the webpage displays:

```
Hello JavaScript
```

The page has become dynamic.

---

# Selecting HTML Elements

Before JavaScript can change something, it must first find it.

There are different ways to select elements.

The two most common methods are:

* `getElementById()`
* `querySelector()`

---

# Method 1 — getElementById()

HTML:

```html
<h1 id="title">
Learning JavaScript
</h1>
```

JavaScript:

```javascript
const title = document.getElementById("title");
```

Now JavaScript has access to that heading.

---

# Method 2 — querySelector()

This is the modern and more flexible approach.

HTML:

```html
<h1 id="title">
Learning JavaScript
</h1>
```

JavaScript:

```javascript
const title = document.querySelector("#title");
```

Notice:

```javascript
#
```

means we are selecting an ID.

---

## Selecting Classes

HTML:

```html
<p class="description">
Welcome Student
</p>
```

JavaScript:

```javascript
const paragraph =
document.querySelector(".description");
```

Notice:

```javascript
.
```

means we are selecting a class.

---

# Changing Content

Once we select an element, we can modify it.

Example:

HTML:

```html
<h1 id="title">
Welcome
</h1>
```

JavaScript:

```javascript
const title =
document.querySelector("#title");


title.textContent =
"Welcome to JavaScript";
```

The browser now displays:

```
Welcome to JavaScript
```

---

# textContent vs innerHTML

## textContent

Used for plain text.

Example:

```javascript
title.textContent = "Hello";
```

Result:

```
Hello
```

---

## innerHTML

Allows HTML content.

Example:

```javascript
title.innerHTML =
"<span>Hello</span>";
```

Result:

The browser interprets the HTML.

---

For beginners:

Use:

```javascript
textContent
```

when changing text.

Use:

```javascript
innerHTML
```

when creating HTML elements dynamically.

---

# Changing Styles with JavaScript

JavaScript can also modify CSS.

HTML:

```html
<h1 id="title">
Hello
</h1>
```

JavaScript:

```javascript
const title =
document.querySelector("#title");


title.style.color = "blue";
```

The text becomes blue.

---

More examples:

Change background:

```javascript
document.body.style.background =
"black";
```

Change font size:

```javascript
title.style.fontSize =
"40px";
```

---

# The classList Property

Changing individual styles works, but it becomes difficult for larger projects.

A better approach is using CSS classes.

Example:

CSS:

```css
.highlight{

    background:black;

    color:white;

    padding:20px;

}
```

JavaScript:

```javascript
title.classList.add("highlight");
```

Now JavaScript adds the CSS class.

---

Remove a class:

```javascript
title.classList.remove("highlight");
```

Toggle a class:

```javascript
title.classList.toggle("highlight");
```

---

# Events

A webpage is constantly waiting for things to happen.

These actions are called events.

Examples:

* Clicking a button
* Typing text
* Moving the mouse
* Submitting a form
* Pressing a key

JavaScript can listen for these events.

---

# addEventListener()

The most common way to handle events is:

```javascript
element.addEventListener(
"event",
function(){

}
);
```

Example:

HTML:

```html
<button id="button">

Click Me

</button>
```

JavaScript:

```javascript
const button =
document.querySelector("#button");


button.addEventListener(
"click",
function(){

console.log("Button clicked");

});
```

Now every time the button is clicked:

```
Button clicked
```

appears in the console.

---

# Common Events

## Click

```javascript
button.addEventListener(
"click",
function(){

});
```

Used for:

* Buttons
* Links
* Cards

---

## Input

Runs whenever a user types.

```javascript
input.addEventListener(
"input",
function(){

});
```

Used for:

* Search boxes
* Live previews

---

## Change

Runs when a value changes.

Example:

Dropdown selection.

---

## Submit

Used with forms.

Example:

Registration forms.

---

# Working With Forms

Forms collect information from users.

Example:

```html
<input id="username">
```

JavaScript:

```javascript
const username =
document.querySelector("#username");


console.log(username.value);
```

The `.value` property gets what the user typed.

---

# Final Project

# Student Registration System

You are going to combine everything you have learned:

* Variables
* Objects
* Arrays
* Functions
* DOM
* Events
* Validation

Your application will allow users to:

* Enter student information.
* Register students.
* Display registered students.

---

# Project Structure

Create:

```
student-registration-system

│

├── index.html

├── style.css

└── script.js
```

---

# index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>
Student Registration System
</title>

<link rel="stylesheet" href="style.css">

</head>


<body>


<div class="container">


<h1>
Student Registration System
</h1>


<input 
id="name"
placeholder="Student Name"
>


<input 
id="age"
placeholder="Student Age"
type="number"
>


<input 
id="course"
placeholder="Course"
>


<button id="register">

Register Student

</button>


<div id="students">

</div>


</div>


<script src="script.js"></script>


</body>

</html>
```

---

# style.css

```css
body{

font-family:Arial, sans-serif;

background:#f1f5f9;

padding:40px;

}


.container{

max-width:500px;

margin:auto;

background:white;

padding:30px;

border-radius:10px;

}


input{

width:100%;

padding:12px;

margin-bottom:15px;

}


button{

width:100%;

padding:12px;

background:#2563eb;

color:white;

border:none;

cursor:pointer;

}


.student{

margin-top:15px;

padding:15px;

background:#f8fafc;

border-left:5px solid #2563eb;

}
```

---

# script.js

First, select the elements.

```javascript
const nameInput =
document.querySelector("#name");


const ageInput =
document.querySelector("#age");


const courseInput =
document.querySelector("#course");


const registerButton =
document.querySelector("#register");


const studentsContainer =
document.querySelector("#students");
```

---

# Create an Array

We need somewhere to store students.

```javascript
const students = [];
```

Initially:

```
students = []
```

After adding students:

```
students = [

John,

Mary,

David

]
```

---

# Listen For Button Click

```javascript
registerButton.addEventListener(
"click",
function(){

console.log("Register clicked");

});
```

Test it.

Click the button.

The message should appear.

---

# Collect User Data

Inside the function:

```javascript
const student = {

name:nameInput.value,

age:ageInput.value,

course:courseInput.value

};
```

Now we have an object:

```javascript
{
name:"John",
age:22,
course:"Frontend"
}
```

---

# Add Student to Array

Use:

```javascript
students.push(student);
```

Now the student is stored.

---

# Display Students

Create a function:

```javascript
function displayStudents(){

studentsContainer.innerHTML = "";


for(let student of students){


studentsContainer.innerHTML += `

<div class="student">

<h3>${student.name}</h3>

<p>
Age: ${student.age}
</p>

<p>
Course: ${student.course}
</p>


</div>

`;

}


}
```

---

# Complete JavaScript

```javascript
const nameInput =
document.querySelector("#name");


const ageInput =
document.querySelector("#age");


const courseInput =
document.querySelector("#course");


const registerButton =
document.querySelector("#register");


const studentsContainer =
document.querySelector("#students");


const students = [];


registerButton.addEventListener(
"click",
function(){


const student = {

name:nameInput.value,

age:ageInput.value,

course:courseInput.value

};


students.push(student);


displayStudents();


});


function displayStudents(){


studentsContainer.innerHTML = "";


for(let student of students){


studentsContainer.innerHTML += `

<div class="student">

<h3>${student.name}</h3>

<p>
Age: ${student.age}
</p>

<p>
Course: ${student.course}
</p>

</div>

`;

}


}
```

---

# Improvements Challenge

Try adding:

## Challenge 1

Prevent empty registration.

Example:

```text
Please enter all details
```

---

## Challenge 2

Clear inputs after registration.

Hint:

```javascript
nameInput.value = "";
```

---

## Challenge 3

Display the number of students registered.

Example:

```
Total Students: 5
```

---

## Challenge 4

Add a delete button for each student.

---

# Common Beginner Mistakes

## 1. Forgetting the # symbol

Wrong:

```javascript
querySelector("name")
```

Correct:

```javascript
querySelector("#name")
```

---

## 2. Selecting an element before it exists

If JavaScript runs before HTML loads, it cannot find elements.

Solution:

Place your script at the bottom of the HTML.

---

## 3. Forgetting `.value`

Wrong:

```javascript
nameInput
```

Correct:

```javascript
nameInput.value
```

---

## 4. Confusing HTML and JavaScript

HTML:

Creates elements.

JavaScript:

Controls those elements.

---

# JavaScript Module Summary

You have now completed the JavaScript crash course.

You learned:

## Session 1

* JavaScript basics
* Variables
* Data types
* Operators
* Conditions

## Session 2

* Functions
* Arrays
* Loops
* Objects

## Session 3

* DOM manipulation
* Events
* Forms
* Dynamic content

You can now create webpages that respond to users and contain real functionality.

The next stage of frontend development is taking these foundations and applying them to larger projects, APIs, and modern development workflows.
