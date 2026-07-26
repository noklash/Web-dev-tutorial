# JavaScript Crash Course

# Session 1 (Part 3)

**Duration:** 2 Hours

**Session Title:** Live Project – Student Registration System (Introduction to the DOM)

> **Instructor's Note**
>
> This is the students' first real JavaScript application. Resist the temptation to type everything yourself. Let students write the code with you. Pause after every section, ask them to predict what will happen, then run the code together.

---

# Learning Objectives

By the end of this lesson, students should be able to:

* Understand what the DOM is
* Select HTML elements with JavaScript
* Read values from form inputs
* Listen for button click events
* Validate user input
* Create JavaScript objects
* Dynamically update a webpage
* Apply beginner debugging techniques

---

# The Project

Today we're building the first version of a **Student Registration System**.

By the end of today's lesson, students will have an application that looks like this:

```text
------------------------------------

Student Registration System

Name
[________________]

Age
[________________]

Course
[________________]

[ Register Student ]

------------------------------------

Registered Students

John
Age: 22
Course: Frontend Development

------------------------------------
```

Later sessions will extend this into a complete Student Management Dashboard.

---

# Project Folder

```text
student-registration/

│

├── index.html

├── style.css

└── script.js
```

---

# Step 1 — Building the HTML

## index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Registration System</title>

    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="container">

    <h1>Student Registration System</h1>

    <div class="card">

        <label>Name</label>

        <input
            type="text"
            id="studentName"
            placeholder="Enter student's name"
        >

        <label>Age</label>

        <input
            type="number"
            id="studentAge"
            placeholder="Enter age"
        >

        <label>Course</label>

        <input
            type="text"
            id="studentCourse"
            placeholder="Frontend Development"
        >

        <button id="registerBtn">

            Register Student

        </button>

    </div>

    <div id="message"></div>

    <hr>

    <h2>Registered Students</h2>

    <div id="studentList">

    </div>

</div>

<script src="script.js"></script>

</body>
</html>
```

---

## Explain Every HTML Element

Ask students:

**Why did we give the inputs IDs?**

Example:

```html
<input id="studentName">
```

Answer:

Because JavaScript needs a way to find this particular input.

Think of IDs as house addresses.

Without an address...

JavaScript won't know where to go.

---

# Step 2 — Styling the Application

## style.css

```css
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{

    background:#eef2f7;

    font-family:Arial, Helvetica, sans-serif;

    padding:40px;
}

.container{

    width:700px;

    margin:auto;

    background:white;

    padding:30px;

    border-radius:10px;

    box-shadow:0 8px 20px rgba(0,0,0,.1);

}

h1{

    margin-bottom:25px;

    color:#2563eb;

}

.card{

    display:flex;

    flex-direction:column;

}

label{

    margin-top:15px;

    margin-bottom:5px;

    font-weight:bold;

}

input{

    padding:12px;

    border:1px solid #ccc;

    border-radius:6px;

    font-size:16px;

}

button{

    margin-top:20px;

    padding:14px;

    background:#2563eb;

    color:white;

    border:none;

    border-radius:6px;

    cursor:pointer;

    font-size:16px;

}

button:hover{

    background:#1d4ed8;

}

#message{

    margin-top:20px;

    font-weight:bold;

}

.student{

    margin-top:20px;

    padding:15px;

    border-left:5px solid #2563eb;

    background:#f8fafc;

    border-radius:6px;

}
```

---

# Instructor Discussion

Ask:

**Did CSS make the application functional?**

No.

It only made it look better.

The application still cannot register students.

That's JavaScript's job.

---

# Step 3 — Creating script.js

Initially

```javascript
console.log("JavaScript Connected Successfully");
```

Open the browser.

Open DevTools.

Show Console.

Students should see

```text
JavaScript Connected Successfully
```

This confirms JavaScript is connected correctly.

---

# Understanding the DOM

Write this HTML.

```html
<h1>Hello World</h1>
```

Ask:

Can JavaScript change this?

Yes.

How?

The browser converts HTML into something called the **Document Object Model (DOM).**

Think of it like this.

```text
HTML

↓

Browser

↓

DOM

↓

JavaScript
```

JavaScript doesn't manipulate raw HTML.

It manipulates the DOM.

---

# Selecting Elements

JavaScript must first find an element.

Example

```javascript
const heading =
document.querySelector("h1");
```

Explain

```javascript
document
```

means

> The webpage.

---

```javascript
querySelector()
```

means

> Find something.

---

Now change the heading.

```javascript
heading.textContent =
"JavaScript is Awesome!";
```

Refresh.

The heading changes instantly.

Students usually smile at this moment 😊

Point out:

"This is the first time you've used JavaScript to change a webpage."

---

# Selecting Our Inputs

```javascript
const studentName =
document.querySelector("#studentName");

const studentAge =
document.querySelector("#studentAge");

const studentCourse =
document.querySelector("#studentCourse");
```

Explain why we use

```javascript
#
```

Because we're selecting IDs.

---

# Selecting the Button

```javascript
const registerButton =
document.querySelector("#registerBtn");
```

---

# Selecting the Output Area

```javascript
const studentList =
document.querySelector("#studentList");

const message =
document.querySelector("#message");
```

---

# Events

Computers wait for something to happen.

These "somethings" are called **events**.

Examples

* Clicking
* Typing
* Hovering
* Scrolling
* Double-clicking
* Pressing a key

---

Today we'll use

```text
click
```

---

# Listening for a Click

```javascript
registerButton.addEventListener(
"click",

function(){

    console.log("Button Clicked");

});
```

Click the button.

Console

```text
Button Clicked

Button Clicked

Button Clicked
```

Explain

The computer is now listening.

When the event happens...

The function runs.

---

# Reading User Input

Suppose the student typed

```text
John
```

How do we get it?

```javascript
console.log(studentName.value);
```

Explain

```javascript
.value
```

means

> Give me whatever the user typed.

---

Try

```javascript
console.log(studentAge.value);

console.log(studentCourse.value);
```

---

# Registering a Student

Now let's store the values.

```javascript
registerButton.addEventListener(

"click",

function(){

    const name = studentName.value;

    const age = studentAge.value;

    const course = studentCourse.value;

    console.log(name);

    console.log(age);

    console.log(course);

});
```

---

# Input Validation

Ask the class:

"What if someone clicks Register without entering anything?"

Students should answer:

"We shouldn't allow it."

Exactly.

---

Validation

```javascript
if(

name === "" ||

age === "" ||

course === ""

){

    message.textContent =
    "Please fill all fields.";

    return;

}
```

Explain

```javascript
return;
```

stops the function immediately.

---

# Success Message

If validation passes

```javascript
message.textContent =
"Student Registered Successfully!";
```

Refresh.

Test.

Students should now see messages appear on the page.

---

# Creating an Object

Instead of having

```javascript
name

age

course
```

Let's group them.

```javascript
const student = {

    name:name,

    age:age,

    course:course

};
```

Show the shorthand syntax too:

```javascript
const student = {
    name,
    age,
    course
};
```

Explain why the shorthand works.

---

Print it

```javascript
console.log(student);
```

Console

```text
{

name:"John",

age:"22",

course:"Frontend"

}
```

Explain

One object.

Three properties.

Exactly how real applications store records.

---

# Displaying the Student

Now update the webpage.

```javascript
studentList.innerHTML =

`
<div class="student">

<h3>${student.name}</h3>

<p>Age: ${student.age}</p>

<p>Course: ${student.course}</p>

</div>

`;
```

Run.

Students finally see information appear.

Huge milestone.

---

# Explain Template Literals

Old JavaScript

```javascript
"Hello " + name
```

Modern

```javascript
`Hello ${name}`
```

Much cleaner.

---

# Complete JavaScript File

```javascript
const studentName = document.querySelector("#studentName");
const studentAge = document.querySelector("#studentAge");
const studentCourse = document.querySelector("#studentCourse");

const registerButton = document.querySelector("#registerBtn");

const studentList = document.querySelector("#studentList");

const message = document.querySelector("#message");

registerButton.addEventListener("click", function () {

    const name = studentName.value.trim();

    const age = studentAge.value.trim();

    const course = studentCourse.value.trim();

    if (
        name === "" ||
        age === "" ||
        course === ""
    ) {

        message.textContent =
            "Please fill all fields.";

        message.style.color = "red";

        return;

    }

    const student = {

        name,

        age,

        course

    };

    message.textContent =
        "Student Registered Successfully!";

    message.style.color = "green";

    studentList.innerHTML = `

    <div class="student">

        <h3>${student.name}</h3>

        <p>Age: ${student.age}</p>

        <p>Course: ${student.course}</p>

    </div>

    `;

});
```

---

# Live Exercise 1

Add another field.

```text
Email
```

Display it.

---

# Live Exercise 2

Add another field.

```text
Phone Number
```

---

# Live Exercise 3

Add another field.

```text
Department
```

---

# Challenge

Instead of

```text
Student Registered Successfully
```

Display

```text
Welcome John!

Registration Completed Successfully.
```

(Hint: use the student's name in the message.)

---

# Common Beginner Mistakes

❌ Forgetting `.value`

```javascript
console.log(studentName);
```

prints the HTML element, **not** what the user typed.

Use:

```javascript
console.log(studentName.value);
```

---

❌ Misspelling IDs

HTML

```html
id="studentName"
```

JavaScript

```javascript
"#studentname"
```

IDs are case-sensitive.

---

❌ Forgetting `#`

Wrong

```javascript
document.querySelector("studentName");
```

Correct

```javascript
document.querySelector("#studentName");
```

---

❌ Forgetting `return`

Without it, the code continues running even after validation fails.

---

❌ Not trimming input

Without `.trim()`:

```text
"     "
```

is treated as valid input.

Always use:

```javascript
value.trim()
```

---

# Instructor Wrap-Up

Today students learned to:

* Connect JavaScript to HTML
* Understand the DOM
* Select HTML elements
* Respond to button clicks
* Read user input
* Validate form data
* Create JavaScript objects
* Display dynamic content using `innerHTML`
* Use template literals

## Looking Ahead (Session 2)

Tell the students:

> "Right now, our application can only display **one student**. Every new registration replaces the previous one. In the next session, we'll learn **arrays**, **loops**, and **array methods** so we can store and display **multiple students**, search through them, and eventually build a complete Student Management Dashboard."

This creates anticipation and shows how today's work forms the foundation for more advanced JavaScript concepts.
