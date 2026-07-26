# JavaScript Module

# Session 2 – Functions, Arrays & Loops

**Duration:** 2 Hours

**Project:** Student Attendance Register

---

# Learning Objectives

By the end of this session, you should be able to:

* Understand why functions are important.
* Create and call functions.
* Use parameters and arguments.
* Return values from functions.
* Understand arrays and why they are useful.
* Add and remove items from arrays.
* Loop through arrays.
* Understand basic objects.
* Build a simple Student Attendance Register application.

---

# Before We Begin

In the previous session, you built a **Student Grade Checker**.

Your application could:

* Receive a student's name.
* Receive a score.
* Calculate a grade.
* Display the result.

However, imagine we want to expand the application.

A school does not have only one student.

A real school may have:

```text
John

Mary

David

Sarah

Michael

...
```

How would we store all these students?

One option would be:

```javascript
let student1 = "John";

let student2 = "Mary";

let student3 = "David";
```

This works for three students.

But what about 1,000 students?

Creating thousands of variables would be impossible.

We need better ways to organize our data.

This session introduces two important concepts:

* **Functions** → Organise and reuse code.
* **Arrays** → Store multiple values together.

---

# Part 1 — Functions

## What is a Function?

A function is a reusable block of code that performs a specific task.

Think about a calculator.

A calculator has buttons:

```text
+ Addition

- Subtraction

× Multiplication

÷ Division
```

Each button performs a specific action.

Functions work the same way.

Instead of writing the same code repeatedly, we create a function once and use it whenever we need it.

---

# Without Functions

Imagine we need to greet three students.

We might write:

```javascript
console.log("Welcome John");

console.log("Welcome Mary");

console.log("Welcome David");
```

This works.

But what if we have 500 students?

The code becomes repetitive.

---

# With Functions

We create one reusable function:

```javascript
function greet(){

    console.log("Welcome Student");

}
```

Now we can use it whenever we want.

```javascript
greet();

greet();

greet();
```

Output:

```text
Welcome Student

Welcome Student

Welcome Student
```

The function saves us from repeating code.

---

# Creating a Function

The basic structure of a function looks like this:

```javascript
function functionName(){

    // code goes here

}
```

Example:

```javascript
function sayHello(){

    console.log("Hello World");

}
```

This creates the function.

However, creating a function does not run it.

We need to call it.

---

# Calling a Function

To execute a function, write its name followed by parentheses.

Example:

```javascript
sayHello();
```

Now the function runs.

Output:

```text
Hello World
```

---

# Functions with Parameters

Sometimes we want a function to work with different values.

For example:

```text
Welcome John

Welcome Mary

Welcome David
```

The names are different, but the action is the same.

Instead of creating separate functions, we can use parameters.

---

Example:

```javascript
function greet(name){

    console.log("Welcome " + name);

}
```

Here:

```javascript
name
```

is a parameter.

It acts like a placeholder.

---

Now we can give the function different values.

```javascript
greet("John");

greet("Mary");

greet("David");
```

Output:

```text
Welcome John

Welcome Mary

Welcome David
```

---

# Parameters vs Arguments

These two words are often confused.

## Parameter

A variable inside the function definition.

Example:

```javascript
function greet(name){

}
```

`name` is a parameter.

---

## Argument

The actual value passed into the function.

Example:

```javascript
greet("John");
```

`"John"` is an argument.

---

Think of it like a form.

A form has empty fields:

```text
Name: __________
```

The empty field is the parameter.

When someone fills it:

```text
Name: John
```

The value is the argument.

---

# Returning Values

Sometimes a function needs to give us a result.

Example:

```javascript
function add(a,b){

    return a + b;

}
```

Now:

```javascript
let result = add(10,5);

console.log(result);
```

Output:

```text
15
```

---

The difference:

`console.log()`

prints something.

`return`

sends something back.

---

Example:

```javascript
function multiply(a,b){

    return a * b;

}

const answer = multiply(5,4);

console.log(answer);
```

Output:

```text
20
```

---

# Arrow Functions

Modern JavaScript has another way to write functions.

Traditional function:

```javascript
function greet(){

    console.log("Hello");

}
```

Arrow function:

```javascript
const greet = () => {

    console.log("Hello");

};
```

Both do the same thing.

For now, focus mainly on normal functions.

Arrow functions will become more familiar as you write more JavaScript.

---

# Practice Exercise 1

Create a function called:

```javascript
introduce()
```

It should display:

```text
My name is John.

I am learning JavaScript.
```

---

# Part 2 — Arrays

## What is an Array?

An array is a special variable that stores multiple values.

Instead of:

```javascript
let student1 = "John";

let student2 = "Mary";

let student3 = "David";
```

We can write:

```javascript
let students = [

"John",

"Mary",

"David"

];
```

One variable.

Multiple values.

---

# Understanding Array Positions

Arrays use indexes.

Important:

**Arrays start counting from zero.**

Example:

```javascript
const students = [

"John",

"Mary",

"David"

];
```

The positions are:

```text
Index        Value

0            John

1            Mary

2            David
```

---

# Accessing Array Items

To get an item, use its index.

Example:

```javascript
console.log(students[0]);
```

Output:

```text
John
```

---

```javascript
console.log(students[2]);
```

Output:

```text
David
```

---

# Updating Array Values

Arrays can be changed.

Example:

```javascript
let students = [

"John",

"Mary",

"David"

];
```

Change Mary:

```javascript
students[1] = "Sarah";
```

Now:

```javascript
console.log(students);
```

Output:

```text
[
"John",
"Sarah",
"David"
]
```

---

# Array Length

The `length` property tells us how many items are inside an array.

Example:

```javascript
const students = [

"John",

"Mary",

"David"

];

console.log(students.length);
```

Output:

```text
3
```

---

# Adding Items to Arrays

## push()

Adds an item to the end.

Example:

```javascript
students.push("Sarah");
```

Now:

```text
John

Mary

David

Sarah
```

---

# Removing Items

## pop()

Removes the last item.

Example:

```javascript
students.pop();
```

Before:

```text
John

Mary

David
```

After:

```text
John

Mary
```

---

# Adding to the Beginning

## unshift()

```javascript
students.unshift("Michael");
```

Result:

```text
Michael

John

Mary

David
```

---

# Removing from the Beginning

## shift()

```javascript
students.shift();
```

Removes the first item.

---

# Part 3 — Loops

## Why Do We Need Loops?

Imagine displaying every student:

```javascript
console.log(students[0]);

console.log(students[1]);

console.log(students[2]);

console.log(students[3]);
```

This becomes repetitive.

Loops allow us to repeat actions automatically.

---

# The for Loop

A basic `for` loop looks like this:

```javascript
for(start; condition; increment){

    // code

}
```

Example:

```javascript
for(let i = 0; i < 5; i++){

    console.log(i);

}
```

Output:

```text
0

1

2

3

4
```

---

# Looping Through an Array

Example:

```javascript
const students = [

"John",

"Mary",

"David"

];


for(let i = 0; i < students.length; i++){

    console.log(students[i]);

}
```

Output:

```text
John

Mary

David
```

---

# for...of Loop

A simpler way to loop through arrays:

```javascript
for(let student of students){

    console.log(student);

}
```

Output:

```text
John

Mary

David
```

For beginners, this is often easier to understand.

---

# Part 4 — Objects (Introduction)

Arrays store lists.

Objects store information about one thing.

Example:

A student has:

* Name
* Age
* Course

An object represents that student.

```javascript
const student = {

    name:"John",

    age:22,

    course:"Frontend Development"

};
```

---

Accessing properties:

```javascript
console.log(student.name);
```

Output:

```text
John
```

---

```javascript
console.log(student.course);
```

Output:

```text
Frontend Development
```

---

# Mini Project

# Student Attendance Register

Now we will combine:

* Variables
* Functions
* Arrays
* Objects
* Loops

to create a simple attendance system.

---

# Project Goal

The application will:

* Allow adding students.
* Store students in an array.
* Display all registered students.
* Show the total number of students.

---

# Project Structure

Create:

```text
student-attendance/

│

├── index.html

├── style.css

└── script.js
```

---

# index.html

```html
<!DOCTYPE html>
<html>

<head>

<title>
Student Attendance Register
</title>

<link rel="stylesheet" href="style.css">

</head>


<body>

<div class="container">

<h1>
Student Attendance Register
</h1>


<input 
id="studentName"
placeholder="Enter student name"
>


<button id="addStudent">

Add Student

</button>


<h2>
Students
</h2>


<ul id="studentList">

</ul>


<p id="totalStudents"></p>


</div>


<script src="script.js"></script>

</body>

</html>
```

---

# style.css

```css
body{

font-family:Arial;

background:#f2f5fa;

padding:40px;

}


.container{

background:white;

max-width:500px;

margin:auto;

padding:30px;

border-radius:10px;

}


input{

padding:10px;

width:70%;

}


button{

padding:10px;

background:#2563eb;

color:white;

border:none;

}
```

---

# script.js

```javascript
const studentInput =
document.querySelector("#studentName");


const addButton =
document.querySelector("#addStudent");


const studentList =
document.querySelector("#studentList");


const totalStudents =
document.querySelector("#totalStudents");


const students = [];


addButton.addEventListener("click", function(){


const name = studentInput.value;


students.push(name);



displayStudents();


studentInput.value = "";


});
```

---

Now create the display function:

```javascript
function displayStudents(){


studentList.innerHTML = "";


for(let student of students){


studentList.innerHTML += `

<li>${student}</li>

`;


}


totalStudents.textContent =

"Total Students: " + students.length;


}
```

---

# What You Built

Your application can now:

✅ Receive user input
✅ Store data in an array
✅ Add new students
✅ Loop through students
✅ Update the webpage dynamically

This is the foundation of many real applications.

---

# Practice Challenges

## Challenge 1

Add a button that clears all students.

Hint:

```javascript
students.length = 0;
```

---

## Challenge 2

Prevent empty names from being added.

Hint:

Use:

```javascript
if()
```

---

## Challenge 3

Display:

```text
Welcome John
```

instead of only:

```text
John
```

---

# Session 2 Summary

Today you learned:

* What functions are and why they matter.
* Parameters and arguments.
* Returning values.
* Arrays and array methods.
* How to add and remove items.
* How loops work.
* Basic objects.
* How to store and display multiple pieces of data.

In the next session, you will learn how JavaScript controls webpages using the **DOM (Document Object Model)** and how to create interactive applications with buttons, forms, and user actions.
