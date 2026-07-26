# JavaScript Crash Course

# Session 1 (Part 1)

**Duration:** 2 Hours

**Session Title:** JavaScript Fundamentals – Introduction, Variables & Data Types

---

# Learning Objectives

At the end of this lesson, students should be able to:

* Explain what JavaScript is.
* Explain the relationship between HTML, CSS and JavaScript.
* Understand where JavaScript runs.
* Create JavaScript files.
* Connect JavaScript to HTML.
* Use the browser developer tools.
* Declare variables using `let` and `const`.
* Identify JavaScript data types.
* Use the `typeof` operator.
* Follow JavaScript naming conventions.
* Write simple JavaScript programs.

---

# Prerequisites

Students should already know:

* HTML Elements
* Forms
* Buttons
* CSS Selectors
* Basic CSS Styling

---

# Lesson Outline

| Time   | Topic                            |
| ------ | -------------------------------- |
| 10 min | Introduction to JavaScript       |
| 10 min | History of JavaScript            |
| 15 min | How JavaScript Works             |
| 10 min | JavaScript in Modern Development |
| 15 min | Setting Up the Environment       |
| 20 min | Variables                        |
| 25 min | Data Types                       |
| 15 min | Live Coding Challenge            |

---

# Introduction

Ask the class:

> **What makes websites interactive?**

Examples:

* Why does Facebook update without refreshing?
* How does YouTube play videos?
* Why does Amazon update the shopping cart instantly?
* How does WhatsApp Web receive messages?

Let students answer.

After a few responses, explain:

> HTML creates the structure.

Example:

```
A house frame
```

---

CSS provides the appearance.

```
Paint
Furniture
Lighting
Decoration
```

---

JavaScript provides behaviour.

```
Opening doors

Turning lights on

Moving objects

Playing music

Submitting forms

Updating pages

Fetching information
```

---

Without JavaScript

```
HTML

↓

Static Website
```

With JavaScript

```
HTML
     +
CSS
     +
JavaScript

↓

Interactive Website
```

---

# Real-World Examples

Ask students:

Which of these use JavaScript?

* Facebook ✔
* Netflix ✔
* Instagram ✔
* WhatsApp Web ✔
* Gmail ✔
* Google Maps ✔
* Spotify ✔

Almost every modern website relies on JavaScript.

---

# What is JavaScript?

JavaScript is a high-level, interpreted programming language primarily used to create interactive web applications.

It allows developers to:

* Respond to user actions
* Update page content
* Validate forms
* Create animations
* Communicate with servers
* Build complete web applications

---

## JavaScript Is Everywhere

Many beginners believe JavaScript only works inside web browsers.

That was true many years ago, but not today.

JavaScript can now be used for:

### Frontend Development

Examples:

* Websites
* Dashboards
* Landing pages

Frameworks:

* React
* Vue
* Angular

---

### Backend Development

Using Node.js

Examples:

* APIs
* Authentication
* Databases
* Payment Systems

---

### Mobile Apps

Using:

* React Native
* NativeScript

Examples:

* Instagram
* Discord
* Shopify Mobile

---

### Desktop Applications

Using Electron

Examples:

* VS Code
* Discord
* Slack
* Postman

---

### Artificial Intelligence

JavaScript is increasingly used to:

* Build AI-powered web applications
* Consume AI APIs
* Build chatbots
* Run TensorFlow.js models in the browser

---

### Internet of Things (IoT)

JavaScript can control:

* Smart devices
* Sensors
* Raspberry Pi
* Robotics

---

# Brief History of JavaScript

Understanding the history helps students appreciate why the language looks the way it does.

### 1995

Netscape wanted a scripting language for its browser.

Brendan Eich was hired.

He created JavaScript in just **10 days**.

Although often repeated, "created in 10 days" refers to the first working version. The language has evolved dramatically over the decades.

---

### Original Name

It was first called:

```
Mocha
```

Then

```
LiveScript
```

Finally

```
JavaScript
```

The name "JavaScript" was chosen largely for marketing reasons because Java was very popular at the time.

**Important:** JavaScript and Java are completely different programming languages.

| Java                         | JavaScript                       |
| ---------------------------- | -------------------------------- |
| Compiled                     | Interpreted/JIT                  |
| Runs on JVM                  | Runs in browsers & Node.js       |
| Strongly typed               | Dynamically typed                |
| Used for enterprise software | Used heavily for web development |

---

# ECMAScript

Many beginners hear the word **ECMAScript** and think it is a different language.

Explain:

JavaScript is the language.

ECMAScript is the official specification that defines how JavaScript should behave.

Think of it this way:

```
Recipe  → ECMAScript

Meal → JavaScript
```

Browser vendors follow the ECMAScript specification when implementing JavaScript engines.

---

### Modern JavaScript

Today we mostly use ES6+ features such as:

* `let`
* `const`
* Arrow functions
* Classes
* Modules
* Template literals
* Destructuring

These make code cleaner and easier to maintain.

---

# How JavaScript Works in the Browser

When a user opens a webpage:

```
Browser

↓

Downloads HTML

↓

Parses HTML

↓

Downloads CSS

↓

Applies styles

↓

Downloads JavaScript

↓

Executes JavaScript
```

---

### The DOM

The browser converts HTML into a structure called the **Document Object Model (DOM)**.

Think of the DOM as a live tree that JavaScript can inspect and modify.

For example, if your HTML contains:

```html
<h1>Welcome</h1>
```

JavaScript can change it to:

```html
<h1>Welcome to JavaScript Class</h1>
```

without reloading the page.

---

# Browser vs Node.js

| Browser                       | Node.js                                         |
| ----------------------------- | ----------------------------------------------- |
| Runs in Chrome, Firefox, Edge | Runs outside the browser                        |
| Can manipulate HTML           | Cannot manipulate HTML directly                 |
| Used for websites             | Used for servers and tools                      |
| Has `document` and `window`   | Does not have `document` or `window` by default |

Tell students:

> During this bootcamp, we will start by writing JavaScript in the browser. Later in the course, you'll encounter tools like Node.js when working with packages and modern frontend tooling.

---

# Setting Up Our Project

Create a folder:

```
javascript-session-1
```

Inside:

```
javascript-session-1/

│

├── index.html

├── style.css

└── script.js
```

Explain the purpose of each file:

* `index.html` – Structure
* `style.css` – Appearance
* `script.js` – Behaviour

---

# Creating the HTML File

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

    <h1>Welcome to JavaScript</h1>

    <script src="script.js"></script>

</body>
</html>
```

### Instructor Note

Ask students:

> Why is the `<script>` tag placed just before `</body>`?

Expected discussion:

* The browser loads the HTML first.
* The elements already exist when JavaScript runs.
* It avoids errors when selecting page elements.
* It can improve perceived page loading.

Mention that modern projects may also use the `defer` attribute when placing scripts in the `<head>`, which you'll cover later.

---

# Creating style.css

```css
body{
    font-family: Arial, Helvetica, sans-serif;
    background:#f4f4f4;
    margin:40px;
}

h1{
    color:#2563eb;
}
```

---

# Creating script.js

```javascript
console.log("Welcome to JavaScript!");
```

---

# Browser Developer Tools

Demonstrate:

Open Chrome.

Right-click

Inspect

OR

```
F12
```

Show:

* Elements
* Console
* Sources
* Network

Explain that the **Console** is the programmer's workspace for testing code, inspecting values, and finding errors.

---

# Using console.log()

```javascript
console.log("Hello World");
```

Explain that `console.log()` sends information to the browser's console for debugging. It does **not** display text on the webpage.

---

More examples:

```javascript
console.log(50);

console.log(true);

console.log("Frontend Development");
```

---

# Variables

Imagine a storage box.

```
Variable

↓

Stores Information
```

Instead of repeatedly typing the same value, we store it in a variable.

Example:

```javascript
let studentName = "John";
```

Now we can reuse `studentName` wherever needed.

---

## Declaring Variables

### let

Use `let` when the value may change.

```javascript
let age = 20;

age = 21;
```

---

### const

Use `const` when the value should not be reassigned.

```javascript
const school = "Frontend Academy";
```

Trying to reassign it:

```javascript
school = "Backend Academy";
```

will produce an error.

---

### Why We Avoid `var`

Explain briefly:

* Function-scoped instead of block-scoped.
* Can be redeclared.
* Leads to bugs in larger applications.

For modern JavaScript, use:

* `let`
* `const`

---

# Variable Naming Rules

Valid:

```javascript
let studentName;

let studentAge;

let totalScore;

let first_name;

let student1;
```

---

Invalid:

```javascript
let 1student;

let first name;

let let;

let @name;
```

---

# Naming Best Practices

Use meaningful names:

```javascript
let totalPrice;
```

instead of:

```javascript
let x;
```

Prefer **camelCase**:

```javascript
studentName
```

rather than:

```javascript
student_name
```

unless your team follows a different convention.

---

# Live Coding Challenge

Ask students to create variables for:

* Their name
* Their age
* Their favourite food
* Their dream job

Example:

```javascript
let studentName = "Amina";
let age = 22;
let favouriteFood = "Jollof Rice";
const dreamJob = "Frontend Developer";

console.log(studentName);
console.log(age);
console.log(favouriteFood);
console.log(dreamJob);
```

Have students run the code and inspect the output in the browser console.

---

## End of Part 1

In the next part, you'll cover **data types in depth**, the `typeof` operator, operators, type conversion, user input, conditionals, and begin the **Student Registration System** project where students start interacting with the DOM using real HTML, CSS, and JavaScript.
