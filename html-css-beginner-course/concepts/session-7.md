# Session 7: Introduction to CSS & Styling Fundamentals

> **Course:** Modern Frontend Development with HTML, CSS, JavaScript & AI Integration (2026)
>
> **Session Length:** 120 Minutes
>
> **Module:** CSS Foundations
>
> **Portfolio Milestone:** Transform a plain HTML website into a visually appealing website using CSS.

---

# Learning Objectives

By the end of this session, students will be able to:

* Understand what CSS is and why it exists
* Explain how HTML and CSS work together
* Use Inline, Internal, and External CSS
* Write basic CSS rules and declarations
* Apply colors, backgrounds, and text styles
* Understand CSS selectors
* Connect CSS files to HTML documents
* Build and style a personal portfolio homepage

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Activity

Show students two websites.

### Website A

Plain HTML:

```text
Black text
White background
No spacing
No colors
```

### Website B

```text
Beautiful layout
Modern colors
Professional typography
Attractive buttons
```

Ask:

> Which website would you trust more?

Most people choose Website B.

---

# Why?

Because design influences perception.

Users judge websites in milliseconds.

Studies consistently show:

* Better design increases trust
* Better design improves usability
* Better design improves conversions

---

# What is CSS?

CSS stands for:

```text
Cascading Style Sheets
```

CSS controls how HTML looks.

HTML provides structure.

CSS provides appearance.

---

# House Analogy

HTML:

```text
Foundation
Walls
Doors
Windows
```

CSS:

```text
Paint
Furniture
Decoration
Lighting
```

Without CSS:

A website works.

With CSS:

A website feels professional.

---

# HTML + CSS Relationship

HTML:

```html
<h1>Frontend Development</h1>
```

CSS:

```css
h1 {
    color: blue;
}
```

Result:

Blue heading.

---

# Why CSS Matters in 2026

Modern users expect:

* Beautiful interfaces
* Mobile responsiveness
* Accessibility
* Fast loading experiences

Every company invests heavily in frontend design.

Examples:

* Airbnb
* Stripe
* Notion
* Linear
* ChatGPT
* Netflix

Their success depends partly on excellent UI design.

---

# CSS Syntax

Basic CSS Rule:

```css
selector {
    property: value;
}
```

Example:

```css
h1 {
    color: blue;
}
```

Breakdown:

Selector:

```css
h1
```

Property:

```css
color
```

Value:

```css
blue
```

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Part 1: Inline CSS

Open:

```html
<h1>Hello World</h1>
```

Add:

```html
<h1 style="color: blue;">
    Hello World
</h1>
```

Result:

Blue text.

---

## Explain

```html
style=""
```

contains CSS directly.

---

### Why We Rarely Use Inline CSS

Bad:

```html
<h1 style="color: blue;">
```

Imagine styling 100 pages.

Maintenance becomes difficult.

---

# Part 2: Internal CSS

Create:

```html
<!DOCTYPE html>
<html>

<head>

</head>

<body>

</body>

</html>
```

Add:

```html
<style>

h1 {
    color: blue;
}

</style>
```

Complete:

```html
<head>

<style>

h1 {
    color: blue;
}

</style>

</head>
```

---

Test:

```html
<h1>Hello CSS</h1>
```

Result:

Blue heading.

---

# Part 3: External CSS (Industry Standard)

Create:

```text
project/
│
├── index.html
└── style.css
```

---

In:

```html
index.html
```

Add:

```html
<link
    rel="stylesheet"
    href="style.css">
```

Inside:

```css
style.css
```

Add:

```css
h1 {
    color: blue;
}
```

Refresh browser.

Result:

Blue heading.

---

## Explain Why External CSS Wins

Advantages:

* Cleaner code
* Easier maintenance
* Reusable
* Faster development

Professional developers use external CSS.

---

# Part 4: Text Color

Add:

```css
h1 {
    color: red;
}
```

Try:

```css
blue
green
purple
orange
```

Demonstrate experimentation.

---

# Part 5: Background Colors

HTML:

```html
<body>
```

CSS:

```css
body {
    background-color: lightgray;
}
```

Observe full page change.

---

Try:

```css
black
navy
beige
whitesmoke
```

---

# Part 6: Font Size

```css
h1 {
    font-size: 40px;
}
```

Explain:

```text
px = pixels
```

Common sizes:

```text
16px
24px
32px
48px
```

---

# Part 7: Text Alignment

```css
h1 {
    text-align: center;
}
```

Values:

```css
left
center
right
```

---

# Part 8: Styling Paragraphs

HTML:

```html
<p>
Frontend development is exciting.
</p>
```

CSS:

```css
p {
    color: darkslategray;
    font-size: 20px;
}
```

---

# Part 9: Multiple Properties

```css
h1 {

    color: blue;

    font-size: 40px;

    text-align: center;

}
```

Explain:

Multiple properties create richer designs.

---

# Part 10: Styling the Portfolio

HTML:

```html
<h1>Goodluck Njoku</h1>

<p>
Frontend Developer in Training
</p>
```

CSS:

```css
body {

    background-color: whitesmoke;

}

h1 {

    color: navy;

    text-align: center;

}

p {

    text-align: center;

    font-size: 20px;

}
```

Students begin seeing professional-looking results.

---

# 70–100 Minutes: Guided Practice & Challenges

---

# Exercise 1: Color Playground

Create:

```html
<h1>My Favorite Color</h1>
```

Apply:

* Text color
* Background color

Experiment with at least 5 colors.

---

# Exercise 2: Style Your Bio

HTML:

```html
<h1>Your Name</h1>

<p>Short Bio</p>
```

Requirements:

* Colored heading
* Larger text
* Center alignment

---

# Exercise 3: Learning Goals Page

Create:

```html
<h1>My Frontend Journey</h1>
```

Add:

```html
<p>
My learning goals...
</p>
```

Style professionally.

---

# Exercise 4: Portfolio Homepage

Use existing portfolio.

Style:

* Background
* Headings
* Paragraphs

---

# Exercise 5 (Challenge)

Create:

```text
developer-profile.html
```

Include:

* Heading
* About Section
* Goals Section

Apply:

* Colors
* Font sizes
* Alignment
* Background styling

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

What does CSS stand for?

Answer:

```text
Cascading Style Sheets
```

---

What does CSS control?

Answer:

Appearance and styling.

---

Which method is most professional?

Answer:

External CSS.

---

What property changes text color?

Answer:

```css
color
```

---

What property changes page background?

Answer:

```css
background-color
```

---

# Common Mistakes

---

## Forgetting Semicolon

Wrong:

```css
h1 {

    color: blue

}
```

Correct:

```css
h1 {

    color: blue;

}
```

---

## Missing Curly Braces

Wrong:

```css
h1

color: blue;
```

Correct:

```css
h1 {

    color: blue;

}
```

---

## Wrong File Link

Wrong:

```html
<link href="styles.css">
```

When file is:

```text
style.css
```

Correct:

```html
<link
 rel="stylesheet"
 href="style.css">
```

---

## Styling Wrong Element

Students often style:

```css
h2
```

while page contains only:

```html
<h1>
```

Always inspect HTML.

---

# 110–120 Minutes: Homework Briefing

---

# Homework Assignment

## Basic Level

Create:

```text
color-practice.html
```

Requirements:

* 1 heading
* 2 paragraphs

Apply:

* Text colors
* Background color

---

## Standard Level

Style your portfolio homepage.

Requirements:

* Background color
* Styled heading
* Styled paragraphs
* Centered content

---

## Challenge Level

Build:

```text
personal-profile.html
```

Sections:

### About Me

### Skills

### Goals

Apply:

* Multiple colors
* Font sizes
* Alignment
* Professional presentation

---

# Key Concepts & Teaching Notes

---

## CSS Is Presentation

Remember:

HTML = Structure

CSS = Appearance

---

## Separation of Concerns

Professional developers separate:

### HTML

Content

### CSS

Styling

### JavaScript

Behavior

This makes projects easier to maintain.

---

## CSS Rules

Every rule follows:

```css
selector {

    property: value;

}
```

Students should memorize this pattern.

---

## External CSS Is Industry Standard

Most professional projects use:

```text
style.css
```

or multiple CSS files.

Rarely inline styles.

---

# Live Coding Example (Final Version)

## index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0">

    <title>Portfolio</title>

    <link
        rel="stylesheet"
        href="style.css">

</head>

<body>

    <h1>Goodluck Njoku</h1>

    <p>
        Frontend Developer in Training
    </p>

</body>

</html>
```

---

## style.css

```css
body {

    background-color: whitesmoke;

}

h1 {

    color: navy;

    font-size: 42px;

    text-align: center;

}

p {

    color: darkslategray;

    font-size: 20px;

    text-align: center;

}
```

---

# Student In-Class Exercises

### Exercise 1

Color Playground

---

### Exercise 2

Bio Styling Challenge

---

### Exercise 3

Learning Goals Page

---

### Exercise 4

Portfolio Styling

---

### Exercise 5

Developer Profile Challenge

---

# Resources & References

## Official Documentation

* [MDN CSS Introduction](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics?utm_source=chatgpt.com)
* [MDN CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference?utm_source=chatgpt.com)
* [MDN Color Property](https://developer.mozilla.org/en-US/docs/Web/CSS/color?utm_source=chatgpt.com)

---

## CSS Practice Tools

* [CSS Tricks](https://css-tricks.com/?utm_source=chatgpt.com)
* [CodePen](https://codepen.io/?utm_source=chatgpt.com)
* [Frontend Mentor](https://www.frontendmentor.io/?utm_source=chatgpt.com)

---

## YouTube Channels

* [Kevin Powell](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)
* [Traversy Media](https://www.youtube.com/@TraversyMedia?utm_source=chatgpt.com)
* [freeCodeCamp](https://www.youtube.com/@freecodecamp?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

## Use External CSS Files

Avoid:

```html
style=""
```

for large projects.

---

## Keep Styles Organized

Group related styles together.

Example:

```css
body {}

h1 {}

p {}
```

---

## Use Meaningful Colors

Don't choose colors randomly.

Think:

* Readability
* Accessibility
* Branding

---

## Test Frequently

Professional workflow:

```text
Code
Save
Refresh Browser
Repeat
```

Fast feedback improves learning.

---

## Think Mobile First

Even before responsive design, remember:

Most users browse on phones.

Avoid giant text and poor color contrast.

---

# Portfolio Project Progress

Current portfolio now contains:

```text
portfolio/
│
├── index.html
├── about.html
├── contact.html
├── style.css
└── images/
```

Students have officially transitioned from **structure-only development** to **visual frontend development**.

Their websites are beginning to look like real products.

---

# Preview of Session 8: CSS Selectors, Classes & IDs

Next session students will learn:

* Element selectors
* Class selectors
* ID selectors
* Grouping selectors
* Descendant selectors
* Reusable styling techniques
* Professional CSS organization

By the end of Session 8, students will be able to style individual sections of a website independently and build much more sophisticated designs.
