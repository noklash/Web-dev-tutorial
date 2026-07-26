# JavaScript Module

# Session 1 – JavaScript Fundamentals

**Duration:** 2 Hours

**Project:** Student Grade Checker

---

# Learning Objectives

By the end of this session, you should be able to:

* Explain what JavaScript is.
* Explain the difference between HTML, CSS and JavaScript.
* Set up a JavaScript project.
* Use the browser Developer Tools.
* Print information using `console.log()`.
* Declare variables using `let` and `const`.
* Identify common JavaScript data types.
* Use operators.
* Write simple conditional statements.
* Build your first JavaScript application.

---

# Before We Begin

Think about some websites you use every day.

* YouTube
* Facebook
* Instagram
* Netflix
* WhatsApp Web
* Amazon

Have you noticed that when you click a button, something immediately happens?

Examples:

* Clicking the **Like** button increases the number of likes.
* Typing in a search box instantly shows suggestions.
* Clicking **Add to Cart** updates your shopping cart.
* Logging in takes you to your dashboard.

Can HTML do these things?

No.

Can CSS do these things?

No.

So what makes them happen?

**JavaScript.**

---

# What is JavaScript?

JavaScript is a programming language used to make web pages interactive.

HTML creates the structure.

CSS makes the page beautiful.

JavaScript makes the page behave.

Think of building a car.

```text
Car Body
    ↓
HTML

Paint & Interior
    ↓
CSS

Engine
    ↓
JavaScript
```

Without the engine, the car looks nice but cannot move.

Without JavaScript, a webpage may look beautiful but cannot respond to user actions.

---

# HTML, CSS and JavaScript Working Together

Imagine you're building a simple login page.

### HTML

Creates:

* Username field
* Password field
* Login button

### CSS

Makes it look attractive.

### JavaScript

Checks whether:

* Username is correct
* Password is correct
* Displays an error if they're wrong
* Redirects the user after a successful login

Each language has its own responsibility.

| Language   | Responsibility |
| ---------- | -------------- |
| HTML       | Structure      |
| CSS        | Styling        |
| JavaScript | Behaviour      |

---

# Where Does JavaScript Run?

Originally, JavaScript only ran inside web browsers.

Today, JavaScript runs in many places:

* Web browsers
* Servers (Node.js)
* Mobile apps
* Desktop applications
* Smart devices
* AI-powered web applications

For this course, we'll focus on **JavaScript in the browser**.

---

# Setting Up Our Project

Create a folder called:

```text
javascript-session-1
```

Inside it, create these files:

```text
javascript-session-1

│

├── index.html

├── style.css

└── script.js
```

This is a common project structure for small web applications.

---

# Creating the HTML File

Open **index.html** and type the following:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Session 1</title>

    <link rel="stylesheet" href="style.css">
</head>
<body>

    <h1>Learning JavaScript</h1>

    <script src="script.js"></script>

</body>
</html>
```

## Understanding the Code

### Linking the CSS file

```html
<link rel="stylesheet" href="style.css">
```

This tells the browser:

> "Load the styles from **style.css**."

---

### Linking the JavaScript file

```html
<script src="script.js"></script>
```

This tells the browser:

> "Load and execute the code inside **script.js**."

---

# Why is the `<script>` Tag at the Bottom?

Notice that we placed it just before the closing `</body>` tag.

```html
<body>

    ...

    <script src="script.js"></script>

</body>
```

This is a common practice because we want the browser to load the HTML first before running JavaScript.

Later in the course, you'll learn another approach using the `defer` attribute.

---

# Styling the Page

Open **style.css**

```css
body{

    font-family: Arial, sans-serif;

    background:#f4f4f4;

    padding:40px;

}

h1{

    color:#2563eb;

}
```

Save the file.

Refresh the browser.

Your heading should now appear in blue.

---

# Writing Your First JavaScript

Open **script.js**

Type:

```javascript
console.log("Welcome to JavaScript!");
```

Save.

Nothing appears on the webpage.

Does that mean it didn't work?

No.

The output is displayed in the **Console**.

---

# Opening Developer Tools

In Google Chrome:

Press

```text
F12
```

or

Right-click anywhere on the page

↓

Inspect

↓

Console

You should see:

```text
Welcome to JavaScript!
```

Congratulations!

You have just executed your first JavaScript program.

---

# Understanding `console.log()`

The `console.log()` function prints information to the browser's console.

It is mainly used for:

* Testing code
* Debugging
* Displaying values
* Understanding what your program is doing

Examples:

```javascript
console.log("Frontend Development");
```

```javascript
console.log(100);
```

```javascript
console.log(true);
```

```javascript
console.log("Hello", "World");
```

---

# Variables

Imagine you have a labelled storage box.

Instead of carrying an item everywhere, you put it inside the box.

Later, whenever you need it, you simply open the box.

Variables work in exactly the same way.

A variable stores information so it can be used later.

---

Instead of writing

```javascript
"John"
```

many times...

Store it once.

```javascript
let studentName = "John";
```

Now you can use

```javascript
studentName
```

anywhere in your program.

---

# Declaring Variables

JavaScript provides different ways to declare variables.

The two you'll use most often are:

* `let`
* `const`

---

## Using `let`

Use `let` when the value may change.

Example:

```javascript
let age = 18;
```

Later...

```javascript
age = 19;
```

This is allowed because variables declared with `let` can be reassigned.

---

## Using `const`

Use `const` when the value should remain the same.

Example:

```javascript
const country = "Nigeria";
```

Trying to change it:

```javascript
country = "Ghana";
```

produces an error.

As a general rule:

* Use `const` by default.
* Use `let` only when you know the value will change.

---

# Variable Naming Rules

Good variable names make code easier to read.

Valid examples:

```javascript
let studentName;

let firstName;

let totalScore;

let favouriteColour;

const schoolName = "ABC Academy";
```

Invalid examples:

```javascript
let 1student;

let first name;

let let;
```

---

# Naming Convention

JavaScript commonly uses **camelCase**.

Example:

```javascript
studentName
```

Not:

```javascript
student_name
```

or

```javascript
StudentName
```

Use names that clearly describe what the variable stores.

Good:

```javascript
let totalMarks;
```

Poor:

```javascript
let x;
```

---

# JavaScript Data Types

Not all information is the same.

Names are different from numbers.

Numbers are different from true or false values.

JavaScript categorises information into **data types**.

Today, we'll learn the most common ones.

---

## String

A string stores text.

Examples:

```javascript
let name = "Mary";
```

```javascript
let city = "Port Harcourt";
```

```javascript
let course = "Frontend Development";
```

Strings are enclosed in quotation marks.

---

## Number

Numbers are used for calculations.

Examples:

```javascript
let age = 22;

let score = 85;

let temperature = 30.5;
```

Notice that numbers are **not** placed inside quotation marks.

---

## Boolean

A Boolean has only two values.

```javascript
true
```

or

```javascript
false
```

Example:

```javascript
let hasPaid = true;

let isLoggedIn = false;
```

These are often used when making decisions.

---

## Undefined

Undefined means:

The variable exists, but no value has been assigned.

Example:

```javascript
let email;

console.log(email);
```

Output:

```text
undefined
```

---

## Null

Null means:

"There is intentionally no value."

Example:

```javascript
let profilePhoto = null;
```

Think of it as an empty placeholder.

---

# The `typeof` Operator

Sometimes you may not know what type of data a variable contains.

JavaScript provides the `typeof` operator.

Example:

```javascript
let name = "John";

console.log(typeof name);
```

Output:

```text
string
```

---

More examples:

```javascript
console.log(typeof 100);
```

Output:

```text
number
```

---

```javascript
console.log(typeof true);
```

Output:

```text
boolean
```

---

# Practice Activity

Predict the output before running the code.

```javascript
console.log(typeof "Frontend");

console.log(typeof 300);

console.log(typeof false);
```

Were your predictions correct?

If not, go back and review the data types.

---

# Operators

Operators allow JavaScript to perform calculations and comparisons.

---

## Arithmetic Operators

Suppose:

```javascript
let a = 20;

let b = 5;
```

Addition:

```javascript
a + b
```

Result:

```text
25
```

Subtraction:

```javascript
a - b
```

Result:

```text
15
```

Multiplication:

```javascript
a * b
```

Division:

```javascript
a / b
```

Remainder:

```javascript
a % b
```

---

# Comparison Operators

These compare values.

Example:

```javascript
10 > 5
```

Result:

```text
true
```

---

```javascript
5 < 3
```

Result:

```text
false
```

---

Common comparison operators include:

```text
>

<

>=

<=

==

===

!=
```

For beginners, remember this rule:

Whenever possible, use:

```javascript
===
```

instead of:

```javascript
==
```

because it performs a stricter and more reliable comparison.

---

# User Input

JavaScript can communicate with users.

### Display a Message

```javascript
alert("Welcome to JavaScript!");
```

---

### Ask a Question

```javascript
let name = prompt("What is your name?");
```

---

### Display the Answer

```javascript
alert("Hello " + name);
```

Run the code and see what happens.

---

# Conditional Statements

Sometimes our program needs to make decisions.

Imagine this situation:

If a student's score is greater than or equal to 50,

display:

```text
Pass
```

Otherwise:

```text
Fail
```

This is called a conditional statement.

---

## Using `if`

```javascript
let score = 70;

if(score >= 50){

    console.log("Pass");

}
```

---

## Using `if...else`

```javascript
let score = 40;

if(score >= 50){

    console.log("Pass");

}else{

    console.log("Fail");

}
```

---

## Using `else if`

```javascript
let score = 85;

if(score >= 70){

    console.log("Excellent");

}else if(score >= 50){

    console.log("Good");

}else{

    console.log("Needs Improvement");

}
```

---

# Class Activity

Write a program that checks a person's age.

If the age is 18 or above, display:

```text
You can vote.
```

Otherwise, display:

```text
You are too young to vote.
```

Try it yourself before looking at the solution.

---

# Mini Project

In the next part of this session, you'll build your first complete JavaScript application:

## Student Grade Checker

The application will:

* Ask for a student's name.
* Allow the student to enter a score.
* Display the student's grade.
* Display a personalised message.
* Use HTML, CSS, and JavaScript together.

This project will help you combine everything you've learned in this lesson into one practical application.
