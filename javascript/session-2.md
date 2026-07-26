# JavaScript Module

# Session 1 (Part 2)

## Live Project — Student Grade Checker

Congratulations! 🎉

You've learned about:

* Variables
* Data types
* `console.log()`
* Operators
* User input
* Conditional statements

Now it's time to combine everything you've learned into your first JavaScript application.

---

# Project Overview

In this project, you will build a **Student Grade Checker**.

The application will:

* Accept a student's name
* Accept a student's score
* Calculate the student's grade
* Display an appropriate message

By the end of this project, you'll understand how JavaScript works with HTML and CSS to create interactive web pages.

---

# What the Application Will Look Like

```text
---------------------------------------

Student Grade Checker

Student Name

[_____________________]

Student Score

[_____________________]

[ Check Grade ]

---------------------------------------

Hello John!

Your Score: 78

Grade: A

Excellent Performance!

---------------------------------------
```

Although this is a simple project, it demonstrates many of the core ideas you'll use in larger applications.

---

# Step 1 — Create the HTML

Open **index.html** and replace its contents with the following:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Grade Checker</title>

    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="container">

    <h1>Student Grade Checker</h1>

    <label for="studentName">Student Name</label>

    <input
        type="text"
        id="studentName"
        placeholder="Enter your name"
    >

    <label for="studentScore">Student Score</label>

    <input
        type="number"
        id="studentScore"
        placeholder="Enter your score"
    >

    <button id="checkGrade">

        Check Grade

    </button>

    <div id="result"></div>

</div>

<script src="script.js"></script>

</body>
</html>
```

---

# Understanding the HTML

Let's break it down.

## The Heading

```html
<h1>Student Grade Checker</h1>
```

This simply displays the title of the application.

---

## The Input Fields

```html
<input
type="text"
id="studentName"
>
```

This allows the user to enter their name.

Notice the `id`.

```html
id="studentName"
```

The `id` acts like a unique name for the element.

Later, JavaScript will use this `id` to find the input on the page.

---

The second input

```html
<input
type="number"
id="studentScore"
>
```

accepts only numbers.

This is where the student enters their score.

---

## The Button

```html
<button id="checkGrade">

Check Grade

</button>
```

When this button is clicked, JavaScript will check the student's grade.

---

## The Result Area

```html
<div id="result"></div>
```

At the moment, this section is empty.

Later, JavaScript will display the student's result here.

---

# Step 2 — Styling the Page

Open **style.css**

```css
*{

    margin:0;

    padding:0;

    box-sizing:border-box;

}

body{

    font-family:Arial, Helvetica, sans-serif;

    background:#f2f5fa;

    display:flex;

    justify-content:center;

    align-items:center;

    min-height:100vh;

}

.container{

    width:420px;

    background:white;

    padding:30px;

    border-radius:10px;

    box-shadow:0 10px 25px rgba(0,0,0,.1);

}

h1{

    text-align:center;

    color:#2563eb;

    margin-bottom:25px;

}

label{

    display:block;

    margin-top:15px;

    margin-bottom:8px;

    font-weight:bold;

}

input{

    width:100%;

    padding:12px;

    border:1px solid #ccc;

    border-radius:6px;

    font-size:16px;

}

button{

    width:100%;

    margin-top:25px;

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

#result{

    margin-top:25px;

    padding:15px;

    border-radius:8px;

    background:#eef4ff;

    min-height:80px;

}
```

Save the file.

Refresh your browser.

You should now have a clean-looking application.

Notice that although it looks good, clicking the button does nothing.

That's because we haven't written any JavaScript yet.

---

# Step 3 — Selecting HTML Elements

Before JavaScript can work with an element, it must first find it.

Open **script.js**

The first thing we'll do is select the elements we need.

```javascript
const studentName =
document.querySelector("#studentName");

const studentScore =
document.querySelector("#studentScore");

const checkGrade =
document.querySelector("#checkGrade");

const result =
document.querySelector("#result");
```

---

## What is `document`?

The word

```javascript
document
```

represents the current webpage.

Everything you see on the page belongs to the document.

---

## What is `querySelector()`?

The method

```javascript
querySelector()
```

searches the webpage and returns the first matching element.

For example,

```javascript
document.querySelector("#studentName")
```

means

> Find the element whose `id` is `studentName`.

Notice the `#`.

Whenever you're selecting an element by its `id`, you must include the `#`.

---

# Step 4 — Listening for a Click

Now let's make the button respond when it's clicked.

```javascript
checkGrade.addEventListener("click", function(){

    console.log("Button Clicked");

});
```

Save your file.

Open the browser.

Press **F12** and go to the **Console**.

Now click the button several times.

You should see

```text
Button Clicked

Button Clicked

Button Clicked
```

This tells us that JavaScript is responding to the click.

---

# Understanding Events

An **event** is simply something that happens on a webpage.

Examples include:

* Clicking a button
* Typing in a textbox
* Moving the mouse
* Pressing a key
* Submitting a form

JavaScript waits for these events and then performs an action.

Think of it like a doorbell.

```text
Visitor presses the bell

↓

The bell rings

↓

Someone opens the door
```

In our application:

```text
User clicks button

↓

JavaScript detects the click

↓

JavaScript checks the grade
```

---

# Step 5 — Reading User Input

Suppose the user types

```text
John
```

How do we get that value?

We use `.value`.

```javascript
console.log(studentName.value);
```

If the user enters

```text
John
```

the console displays

```text
John
```

The `.value` property returns whatever the user typed into an input field.

---

Let's also read the student's score.

```javascript
console.log(studentScore.value);
```

Remember that the value returned from an input field is **text (a string)**, even when the input type is `number`.

We'll convert it to a number before making comparisons.

---

# Step 6 — Writing the Main Program

Replace your click event with the following:

```javascript
checkGrade.addEventListener("click", function(){

    const name = studentName.value;

    const score = Number(studentScore.value);

    console.log(name);

    console.log(score);

});
```

Now try entering your own name and score.

Open the console and check that the values are printed correctly.

---

# Step 7 — Validating User Input

What happens if the user clicks the button without entering anything?

The program should not continue.

Let's check for empty fields.

```javascript
if(name === "" || studentScore.value === ""){

    result.textContent =
    "Please complete all fields.";

    return;

}
```

The `return` statement immediately stops the function.

Without it, the rest of the program would continue running.

Input validation is important because it prevents incorrect or incomplete data from being processed.

---

# Step 8 — Calculating the Grade

Now let's determine the student's grade.

```javascript
let grade = "";

let message = "";
```

These variables will store the final grade and the accompanying message.

Next, add the grading logic.

```javascript
if(score >= 70){

    grade = "A";

    message = "Excellent Performance!";

}
else if(score >= 60){

    grade = "B";

    message = "Very Good!";

}
else if(score >= 50){

    grade = "C";

    message = "Good Job!";

}
else if(score >= 45){

    grade = "D";

    message = "Fair. Keep Practising.";

}
else{

    grade = "F";

    message = "Needs Improvement.";

}
```

This program checks the score from the highest range down to the lowest.

---

# Step 9 — Displaying the Result

Now replace the contents of the result box.

```javascript
result.innerHTML = `

<h2>Hello ${name}!</h2>

<p><strong>Score:</strong> ${score}</p>

<p><strong>Grade:</strong> ${grade}</p>

<p>${message}</p>

`;
```

Notice the use of backticks (`` ` ``).

These are called **template literals**.

They allow us to insert variables directly into a string using:

```javascript
${variableName}
```

This is cleaner and easier to read than joining strings with the `+` operator.

---

# Complete JavaScript Code

```javascript
const studentName = document.querySelector("#studentName");
const studentScore = document.querySelector("#studentScore");
const checkGrade = document.querySelector("#checkGrade");
const result = document.querySelector("#result");

checkGrade.addEventListener("click", function(){

    const name = studentName.value.trim();

    const scoreText = studentScore.value.trim();

    if(name === "" || scoreText === ""){

        result.textContent = "Please complete all fields.";

        return;

    }

    const score = Number(scoreText);

    let grade = "";
    let message = "";

    if(score >= 70){

        grade = "A";
        message = "Excellent Performance!";

    }
    else if(score >= 60){

        grade = "B";
        message = "Very Good!";

    }
    else if(score >= 50){

        grade = "C";
        message = "Good Job!";

    }
    else if(score >= 45){

        grade = "D";
        message = "Fair. Keep Practising.";

    }
    else{

        grade = "F";
        message = "Needs Improvement.";

    }

    result.innerHTML = `
        <h2>Hello ${name}!</h2>
        <p><strong>Score:</strong> ${score}</p>
        <p><strong>Grade:</strong> ${grade}</p>
        <p>${message}</p>
    `;

});
```

---

# Try It Yourself

Make the following improvements to your project:

1. Display the student's name in **uppercase**.
2. Show a different message for each grade.
3. Display **"Perfect Score!"** if the student scores **100**.
4. Display an error message if the score is less than **0** or greater than **100**.

Try to solve these challenges on your own before asking for help. Making mistakes is part of learning to program.

---

# Common Mistakes

### 1. Forgetting `.value`

Incorrect:

```javascript
console.log(studentName);
```

This prints the HTML element, not the text inside it.

Correct:

```javascript
console.log(studentName.value);
```

---

### 2. Comparing Text Instead of Numbers

Incorrect:

```javascript
const score = studentScore.value;
```

Correct:

```javascript
const score = Number(studentScore.value);
```

Converting the input ensures that numerical comparisons behave as expected.

---

### 3. Misspelling an `id`

If your HTML contains:

```html
id="studentScore"
```

then JavaScript must use exactly the same spelling.

IDs are **case-sensitive**.

---

### 4. Forgetting to Save Your Files

If nothing changes in the browser, make sure you've saved:

* `index.html`
* `style.css`
* `script.js`

before refreshing the page.

---

# Session 1 Summary

Congratulations! You've completed your first JavaScript project.

In this session, you learned how to:

* Link JavaScript to an HTML page.
* Use the browser console for testing.
* Store information in variables.
* Work with different data types.
* Perform calculations using operators.
* Make decisions with `if...else`.
* Read user input from form fields.
* Respond to button clicks.
* Update a webpage dynamically using JavaScript.

These are the building blocks of interactive web development. In the next session, you'll build on this foundation by learning how to organise your code with **functions**, work with **arrays**, and repeat tasks using **loops**.
