# JavaScript Crash Course

# Session 1 (Part 2)

**Duration:** ~2 Hours

**Session Title:** Data Types, Operators, User Input, Conditionals & Functions

---

# Learning Objectives

By the end of this lesson, students should be able to:

* Identify JavaScript primitive and reference data types.
* Use the `typeof` operator.
* Perform arithmetic and logical operations.
* Understand type conversion.
* Accept user input.
* Make decisions using conditional statements.
* Write reusable functions.
* Prepare for DOM manipulation in the next lesson.

---

# Lesson Outline

| Time   | Topic                  |
| ------ | ---------------------- |
| 20 min | JavaScript Data Types  |
| 10 min | typeof Operator        |
| 20 min | Operators              |
| 15 min | Type Conversion        |
| 10 min | User Input             |
| 25 min | Conditional Statements |
| 20 min | Functions              |
| 10 min | Class Challenge        |

---

# Recap from Part 1

Ask students:

* What is JavaScript?
* Difference between HTML, CSS and JavaScript?
* What is a variable?
* Difference between `let` and `const`?

---

# JavaScript Data Types

Everything stored in JavaScript has a **type**.

Think of data types as different kinds of containers.

A bottle stores water.

A wallet stores money.

A variable stores a particular type of data.

Example

```javascript
let name = "David";
let age = 25;
let isStudent = true;
```

Although all are variables, they hold different types of information.

---

# Primitive Data Types

JavaScript has seven primitive data types.

For beginners, focus on these six:

* String
* Number
* Boolean
* Undefined
* Null
* BigInt (brief introduction)

(Symbol can be mentioned but isn't necessary at this stage.)

---

## 1. String

A string represents text.

Examples

```javascript
let firstName = "David";

let country = "Nigeria";

let course = 'Frontend Development';
```

Strings can use either single or double quotes.

```javascript
"Hello"

'Hello'
```

Both are valid.

---

### Common String Examples

```javascript
let email = "john@gmail.com";

let phone = "08012345678";

let address = "Port Harcourt";
```

---

## 2. Number

Numbers include both whole numbers and decimals.

```javascript
let age = 20;

let score = 95;

let temperature = 28.5;
```

Unlike some programming languages, JavaScript has one general `number` type for both integers and floating-point values.

---

## 3. Boolean

A Boolean only has two possible values.

```javascript
true

false
```

Example

```javascript
let isLoggedIn = true;

let hasPaid = false;

let isOnline = true;
```

Booleans are commonly used in conditions.

---

## 4. Undefined

Undefined means:

> A variable has been declared but has not yet been assigned a value.

Example

```javascript
let username;

console.log(username);
```

Output

```javascript
undefined
```

---

## 5. Null

Null means:

> The value has intentionally been set to "nothing."

Example

```javascript
let profilePicture = null;
```

Difference

```javascript
undefined

↓

No value assigned yet.
```

```javascript
null

↓

Value intentionally removed or empty.
```

---

## 6. BigInt (Brief Introduction)

Used for extremely large integers.

Example

```javascript
const population = 12345678901234567890n;
```

Explain that students won't use BigInt often during this course, but it exists for very large numbers.

---

# Reference Data Types

Reference types store more complex information.

The two you'll use constantly are:

* Objects
* Arrays

---

# Objects

Objects store related information.

Example

```javascript
const student = {

    name: "John",

    age: 22,

    course: "Frontend"

};
```

Explain each property.

Think of an object as a digital identity card.

```
Student

Name

John

Age

22

Course

Frontend
```

---

Accessing object properties

```javascript
console.log(student.name);

console.log(student.course);
```

---

# Arrays

Arrays store lists.

Example

```javascript
const fruits = [

"Apple",

"Orange",

"Mango",

"Banana"

];
```

Think of an array as numbered shelves.

```
0 Apple

1 Orange

2 Mango

3 Banana
```

---

Accessing array items

```javascript
console.log(fruits[0]);

console.log(fruits[2]);
```

---

# typeof Operator

JavaScript provides a built-in operator called `typeof`.

It tells us the data type of a value.

Example

```javascript
console.log(typeof "Hello");
```

Output

```
string
```

---

More examples

```javascript
console.log(typeof 50);
```

```
number
```

---

```javascript
console.log(typeof true);
```

```
boolean
```

---

```javascript
console.log(typeof undefined);
```

```
undefined
```

---

Interesting Example

```javascript
console.log(typeof null);
```

Output

```
object
```

Explain:

This is a long-standing quirk in JavaScript dating back to its early implementation. Even though `typeof null` returns `"object"`, `null` is **not** actually an object. Modern developers simply learn this behaviour and work around it when necessary.

---

# Activity

Ask students to predict the output before running:

```javascript
console.log(typeof "Frontend");

console.log(typeof 500);

console.log(typeof false);

console.log(typeof ["Apple","Orange"]);

console.log(typeof {
    name:"John"
});
```

Discuss why arrays also return `"object"`.

---

# Operators

Operators allow JavaScript to perform actions on values.

---

## Arithmetic Operators

```javascript
+

-

*

/

%

**
```

---

Example

```javascript
let a = 20;

let b = 10;

console.log(a + b);

console.log(a - b);

console.log(a * b);

console.log(a / b);
```

---

### Modulus

Returns the remainder.

```javascript
console.log(10 % 2);
```

Output

```
0
```

---

```javascript
console.log(7 % 2);
```

Output

```
1
```

Excellent for checking whether a number is even or odd.

---

### Exponentiation

```javascript
console.log(2 ** 3);
```

Output

```
8
```

---

# Assignment Operators

```javascript
=

+=

-=

*=

/=
```

Example

```javascript
let score = 50;

score += 10;

console.log(score);
```

Output

```
60
```

---

# Increment and Decrement

Increment

```javascript
let count = 1;

count++;

console.log(count);
```

---

Decrement

```javascript
count--;
```

---

# Comparison Operators

Used to compare values.

```
>

<

>=

<=

==
===

!=

!==
```

---

Example

```javascript
console.log(10 > 5);
```

Output

```
true
```

---

## == vs ===

This is one of the most important concepts in JavaScript.

Example

```javascript
console.log(5 == "5");
```

Output

```
true
```

Why?

Because `==` performs **type coercion**, converting values before comparing them.

---

Now

```javascript
console.log(5 === "5");
```

Output

```
false
```

`===` compares both **value** and **type**.

**Instructor Tip:** Encourage students to use `===` by default. It helps avoid subtle bugs.

---

# Logical Operators

```
&&

||

!
```

---

AND

```javascript
let hasID = true;

let hasTicket = true;

console.log(hasID && hasTicket);
```

---

OR

```javascript
console.log(hasID || hasTicket);
```

---

NOT

```javascript
console.log(!true);
```

Output

```
false
```

---

# Type Conversion

Sometimes we need to convert one data type into another.

---

## String to Number

Imagine the user types:

```
25
```

It looks like a number but JavaScript receives it as a string.

```javascript
let age = "25";

console.log(typeof age);
```

Output

```
string
```

---

Convert it

```javascript
age = Number(age);

console.log(typeof age);
```

Output

```
number
```

---

## Number to String

```javascript
let score = 80;

score = String(score);
```

---

## Boolean Conversion

```javascript
Boolean(1);
```

returns

```
true
```

---

```javascript
Boolean(0);
```

returns

```
false
```

Briefly explain that JavaScript considers some values "truthy" and others "falsy", a topic you'll explore in more depth later.

---

# User Input

JavaScript provides simple functions for interacting with users.

---

## alert()

Displays a message.

```javascript
alert("Welcome to JavaScript!");
```

---

## prompt()

Collects text input.

```javascript
let name = prompt("What is your name?");
```

---

Display it

```javascript
alert("Welcome " + name);
```

---

## confirm()

Returns either `true` or `false`.

```javascript
let answer = confirm("Do you want to continue?");
```

---

# Classroom Exercise

Ask students to build a simple greeting.

```javascript
let name = prompt("Enter your name");

alert("Hello " + name);
```

---

# Conditional Statements

Computers make decisions using conditions.

Example

```
IF it rains

↓

Take an umbrella
```

---

## if Statement

```javascript
let age = 20;

if(age >= 18){

    console.log("Adult");

}
```

---

## if...else

```javascript
let score = 40;

if(score >= 50){

    console.log("Pass");

}else{

    console.log("Fail");

}
```

---

## else if

```javascript
let score = 75;

if(score >= 70){

    console.log("Grade A");

}else if(score >= 60){

    console.log("Grade B");

}else if(score >= 50){

    console.log("Grade C");

}else{

    console.log("Fail");

}
```

---

## switch Statement

Useful when checking one value against many options.

```javascript
let day = "Monday";

switch(day){

case "Monday":

    console.log("New week");

    break;

case "Friday":

    console.log("Weekend is near");

    break;

default:

    console.log("Normal day");

}
```

Explain why `break` is important—it stops execution from continuing into the next case.

---

# Functions

Functions are reusable blocks of code.

Instead of repeating code many times, write it once and call it whenever needed.

---

## Function Declaration

```javascript
function greet(){

    console.log("Welcome");

}
```

Calling it

```javascript
greet();
```

---

## Parameters

```javascript
function greet(name){

    console.log("Welcome " + name);

}
```

Call it

```javascript
greet("David");

greet("Mary");

greet("James");
```

One function can work with many different values.

---

## Returning Values

```javascript
function add(a,b){

    return a + b;

}

let result = add(10,20);

console.log(result);
```

Explain that `return` sends a value back to wherever the function was called.

---

## Arrow Functions

Modern JavaScript syntax

```javascript
const add = (a,b)=>{

    return a+b;

};
```

Short version

```javascript
const multiply = (a,b)=> a * b;
```

Mention that arrow functions will become very common when students begin learning React.

---

# Live Coding Challenge

Build a simple calculator.

```javascript
let firstNumber = Number(prompt("Enter first number"));

let secondNumber = Number(prompt("Enter second number"));

function add(a,b){

    return a+b;

}

let answer = add(firstNumber, secondNumber);

alert("The answer is " + answer);
```

### Instructor Discussion

Ask students:

* What happens if you remove `Number()`?
* Why does `"10" + "20"` produce `"1020"` instead of `30`?
* What if the user clicks **Cancel** in the prompt?
* How could we improve the program to handle invalid input?

These questions encourage students to think beyond simply writing code and begin reasoning about how programs behave.

---

# End-of-Class Exercise

Create a small program that:

1. Asks for a student's name.
2. Asks for their score.
3. Converts the score to a number.
4. Displays:

   * **Excellent** if the score is 70 or above.
   * **Good** if the score is between 50 and 69.
   * **Needs Improvement** if the score is below 50.

---

# Homework

1. Create variables representing yourself (name, age, country, favourite programming language).
2. Use `typeof` to determine the type of each variable.
3. Build a simple calculator that performs addition, subtraction, multiplication, and division.
4. Create a grading system using `if...else if`.
5. Write three reusable functions:

   * `add()`
   * `subtract()`
   * `multiply()`

---

# Summary

In this lesson, students learned:

* Primitive and reference data types.
* The `typeof` operator.
* Arithmetic, comparison, assignment, and logical operators.
* Explicit type conversion using `Number()`, `String()`, and `Boolean()`.
* Basic user interaction with `alert()`, `prompt()`, and `confirm()`.
* Decision-making with `if`, `else if`, and `switch`.
* Function declarations, parameters, return values, and arrow functions.

These concepts form the foundation for the next part, where students will begin building a **Student Registration System** using HTML, CSS, and JavaScript. They'll learn how to connect JavaScript to the page, read form input, respond to button clicks, validate user input, and dynamically update the interface using the DOM.
