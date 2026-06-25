# Session 10: CSS Display, Width, Height & Layout Fundamentals

> **Course:** Modern Frontend Development with HTML, CSS, JavaScript & AI Integration (2026)
>
> **Session Length:** 120 Minutes
>
> **Module:** CSS Foundations
>
> **Portfolio Milestone:** Understand how elements are positioned and rendered on a page, laying the groundwork for Flexbox, Grid, and responsive design.

---

# Learning Objectives

By the end of this session, students will be able to:

* Understand how browsers render block and inline elements
* Use the `display` property effectively
* Differentiate between block, inline, and inline-block elements
* Control width and height appropriately
* Understand content overflow and how to handle it
* Build cleaner layouts using display properties
* Inspect layout behavior using browser DevTools
* Prepare for modern layout systems like Flexbox and Grid

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Activity

Ask students:

Why does this happen?

```html
<h1>Frontend Development</h1>

<p>Learn HTML</p>

<p>Learn CSS</p>

<p>Learn JavaScript</p>
```

Output:

```text
Frontend Development

Learn HTML

Learn CSS

Learn JavaScript
```

Everything appears on separate lines.

---

Now show:

```html
<a href="#">Home</a>

<a href="#">About</a>

<a href="#">Contact</a>
```

Output:

```text
Home About Contact
```

All on one line.

---

Question:

> Why are they behaving differently?

Because HTML elements have default display behavior.

---

# Understanding Browser Layout

Every HTML element has a default display type.

Examples:

| Element | Default Display |
| ------- | --------------- |
| h1      | block           |
| p       | block           |
| div     | block           |
| section | block           |
| a       | inline          |
| span    | inline          |
| strong  | inline          |
| em      | inline          |

---

# Block Elements

Block elements:

```text
Take up full width available
Start on a new line
Stack vertically
```

Example:

```html
<div>Box 1</div>

<div>Box 2</div>
```

Output:

```text
Box 1

Box 2
```

---

# Inline Elements

Inline elements:

```text
Only take up necessary width
Stay on same line
Do not force line breaks
```

Example:

```html
<a>Home</a>

<a>About</a>

<a>Contact</a>
```

Output:

```text
Home About Contact
```

---

# Why This Matters

Understanding display behavior explains:

* Why layouts break
* Why width isn't working
* Why height isn't applying
* Why spacing behaves strangely

Every frontend developer must master this.

---

# Real-World Analogy

Imagine bookshelves.

### Block Elements

```text
Each book gets its own shelf.
```

---

### Inline Elements

```text
Books sit beside each other on the same shelf.
```

That's exactly how browsers think.

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Part 1: Block Elements in Action

HTML:

```html
<div>First Box</div>

<div>Second Box</div>

<div>Third Box</div>
```

CSS:

```css
div {

    border: 1px solid black;

}
```

Observe:

Each div occupies its own row.

---

# Part 2: Width on Block Elements

```css
div {

    width: 300px;

    border: 1px solid black;

}
```

Explain:

Block elements respect width.

---

Try:

```css
width: 100px;

width: 500px;
```

Observe changes.

---

# Part 3: Inline Elements

HTML:

```html
<a href="#">Home</a>

<a href="#">About</a>

<a href="#">Contact</a>
```

CSS:

```css
a {

    border: 1px solid red;

}
```

Observe:

Links stay on same line.

---

# Part 4: Width Doesn't Work on Inline Elements

Try:

```css
a {

    width: 300px;

}
```

Nothing happens.

---

Explain:

Inline elements ignore:

```text
width
height
```

in most situations.

---

# Part 5: Display Property

CSS allows us to change behavior.

Syntax:

```css
display: value;
```

---

# Part 6: Make Block Become Inline

HTML:

```html
<div>Box One</div>

<div>Box Two</div>

<div>Box Three</div>
```

CSS:

```css
div {

    display: inline;

}
```

Observe:

All boxes move onto one line.

---

# Part 7: Make Inline Become Block

HTML:

```html
<a href="#">Home</a>

<a href="#">About</a>

<a href="#">Contact</a>
```

CSS:

```css
a {

    display: block;

}
```

Observe:

Links stack vertically.

---

# Part 8: Inline-Block

One of the most important display values.

```css
display: inline-block;
```

---

Benefits:

```text
✓ Stay on same line
✓ Respect width
✓ Respect height
```

Best of both worlds.

---

Example:

```css
.card {

    display: inline-block;

    width: 250px;

    border: 1px solid gray;

}
```

---

HTML:

```html
<div class="card">

    Card One

</div>

<div class="card">

    Card Two

</div>

<div class="card">

    Card Three

</div>
```

Observe:

Cards align horizontally.

---

# Part 9: Height Property

```css
.card {

    height: 150px;

}
```

Observe:

Cards grow vertically.

---

Explain:

Height defines vertical size.

Use carefully.

Content-driven layouts are often better.

---

# Part 10: Overflow

Create:

```html
<div class="box">

Lorem ipsum dolor sit amet consectetur
adipisicing elit. Necessitatibus
asperiores reprehenderit.

</div>
```

CSS:

```css
.box {

    width: 200px;

    height: 50px;

    border: 1px solid black;

}
```

Observe:

Content spills outside.

---

# Overflow Property

```css
overflow: hidden;
```

Hides excess content.

---

```css
overflow: scroll;
```

Adds scrollbars.

---

```css
overflow: auto;
```

Shows scrollbar only when needed.

---

Demonstrate all three.

---

# Part 11: Create Portfolio Cards

HTML:

```html
<section class="card">

    <h2>About Me</h2>

</section>

<section class="card">

    <h2>Skills</h2>

</section>

<section class="card">

    <h2>Projects</h2>

</section>
```

CSS:

```css
.card {

    display: inline-block;

    width: 250px;

    padding: 20px;

    border: 1px solid lightgray;

}
```

Observe:

Cards align neatly.

---

# Part 12: DevTools Layout Inspection

Open DevTools.

Inspect:

```text
Computed Width
Computed Height
Display Type
```

Show students where browsers reveal layout behavior.

---

# 70–100 Minutes: Guided Practice & Challenges

---

# Exercise 1: Block vs Inline

Create:

```html
<div>Box A</div>

<div>Box B</div>
```

Observe behavior.

Then change:

```css
display: inline;
```

Compare.

---

# Exercise 2: Navigation Menu

Create:

```html
<a href="#">Home</a>

<a href="#">About</a>

<a href="#">Projects</a>
```

Convert links into:

```css
display: block;
```

Observe changes.

---

# Exercise 3: Inline-Block Cards

Create three cards.

Requirements:

```css
display: inline-block;
width: 200px;
```

---

# Exercise 4: Overflow Testing

Create small container.

Add lots of text.

Experiment with:

```css
overflow: hidden;
overflow: scroll;
overflow: auto;
```

---

# Exercise 5 (Challenge)

Build:

```text
Developer Services Page
```

Requirements:

Three service cards:

```text
Web Design
Frontend Development
UI Development
```

Each card must:

* Use inline-block
* Have width
* Have padding
* Have border

Arrange horizontally.

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

Which elements start on a new line?

Answer:

```text
Block Elements
```

---

Which elements stay on same line?

Answer:

```text
Inline Elements
```

---

Which display value combines both behaviors?

Answer:

```css
display: inline-block;
```

---

Which property controls hidden content?

Answer:

```css
overflow
```

---

Which overflow value adds scrollbars when needed?

Answer:

```css
overflow: auto;
```

---

# Common Mistakes

---

## Applying Width to Inline Elements

Wrong expectation:

```css
a {

    width: 300px;

}
```

Often does nothing.

---

Solution:

```css
a {

    display: inline-block;

    width: 300px;

}
```

---

## Excessive Fixed Heights

Bad:

```css
height: 1000px;
```

Usually unnecessary.

---

## Forgetting Display Type

Students often wonder:

```text
Why isn't width working?
```

Answer:

Check display type.

---

## Using Overflow Hidden Accidentally

```css
overflow: hidden;
```

Can hide important content.

Use carefully.

---

# 110–120 Minutes: Homework Briefing

# Homework Assignment

---

## Basic Level

Create:

```text
display-practice.html
```

Requirements:

* Two block elements
* Two inline elements
* Experiment with display changes

---

## Standard Level

Build:

```text
navigation-demo.html
```

Create navigation links.

Experiment with:

```css
display: block;
display: inline;
display: inline-block;
```

Document observations.

---

## Challenge Level

Upgrade portfolio.

Create:

### About Card

### Skills Card

### Projects Card

Requirements:

```css
display: inline-block;
width: 250px;
padding: 20px;
```

Arrange cards neatly.

---

# Key Concepts & Teaching Notes

---

# Display Controls Layout Behavior

Most beginner CSS problems involve misunderstanding:

```css
display
```

Understanding it solves many layout issues.

---

# Block Elements Stack

Think:

```text
One box per row
```

Examples:

```html
<div>
<section>
<p>
<h1>
```

---

# Inline Elements Flow

Think:

```text
Words in a sentence
```

Examples:

```html
<a>
<span>
<strong>
```

---

# Inline-Block Is Transitional Knowledge

Historically important.

Still useful.

But later:

```text
Flexbox
Grid
```

will replace many use cases.

---

# Width Depends on Display

Many students struggle because:

```css
width
```

behaves differently depending on:

```css
display
```

---

# Live Coding Example (Final Version)

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <title>Display Demo</title>

    <link
        rel="stylesheet"
        href="style.css">

</head>

<body>

    <section class="card">

        <h2>About Me</h2>

        <p>Frontend Developer</p>

    </section>

    <section class="card">

        <h2>Skills</h2>

        <p>HTML, CSS</p>

    </section>

    <section class="card">

        <h2>Projects</h2>

        <p>Portfolio Website</p>

    </section>

</body>

</html>
```

---

## CSS

```css
.card {

    display: inline-block;

    width: 250px;

    padding: 20px;

    margin: 10px;

    border: 1px solid lightgray;

}
```

---

# Student In-Class Exercises

### Exercise 1

Block vs Inline Demonstration

---

### Exercise 2

Navigation Layout Practice

---

### Exercise 3

Inline-Block Cards

---

### Exercise 4

Overflow Playground

---

### Exercise 5

Developer Services Challenge

---

# Resources & References

## Official Documentation

* [MDN Display Property](https://developer.mozilla.org/en-US/docs/Web/CSS/display?utm_source=chatgpt.com)
* [MDN Width Property](https://developer.mozilla.org/en-US/docs/Web/CSS/width?utm_source=chatgpt.com)
* [MDN Height Property](https://developer.mozilla.org/en-US/docs/Web/CSS/height?utm_source=chatgpt.com)
* [MDN Overflow Property](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow?utm_source=chatgpt.com)

---

## Practice Resources

* [CSS Tricks Display Guide](https://css-tricks.com/almanac/properties/d/display/?utm_source=chatgpt.com)
* [CodePen](https://codepen.io/?utm_source=chatgpt.com)
* [Frontend Mentor](https://www.frontendmentor.io/?utm_source=chatgpt.com)

---

## YouTube Recommendations

* [Kevin Powell CSS Layout Tutorials](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)
* [Traversy Media CSS Crash Course](https://www.youtube.com/@TraversyMedia?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

### Don't Build Complex Layouts With Inline-Block

Modern developers use:

```text
Flexbox
Grid
```

for major layouts.

We're learning inline-block to understand layout fundamentals.

---

### Use DevTools Frequently

Inspect:

* Width
* Height
* Display
* Overflow

Professional developers do this daily.

---

### Avoid Fixed Heights Unless Necessary

Content should usually determine element height.

---

### Think Component-Based

Cards, buttons, navigation items, and sections should be reusable building blocks.

---

# Portfolio Project Progress

Students now understand:

```text
✓ Box Model
✓ Width
✓ Height
✓ Display Types
✓ Inline vs Block
✓ Inline-Block
✓ Overflow
```

Their portfolio has evolved from a collection of HTML pages into a structured layout with reusable UI components.

---

# Preview of Session 11: CSS Typography, Fonts & Text Styling

Next session students will learn:

* Font families
* Web-safe fonts
* Google Fonts
* Font weight
* Line height
* Letter spacing
* Text transformations
* Building modern typography systems

By the end of Session 11, students will dramatically improve the readability and professionalism of their websites through effective typography.
