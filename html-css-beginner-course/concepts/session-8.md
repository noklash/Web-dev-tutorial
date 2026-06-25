# Session 8: CSS Selectors, Classes & IDs

> **Course:** Modern Frontend Development with HTML, CSS, JavaScript & AI Integration (2026)
>
> **Session Length:** 120 Minutes
>
> **Module:** CSS Foundations
>
> **Portfolio Milestone:** Create reusable styling systems using classes and IDs instead of styling every element individually.

---

# Learning Objectives

By the end of this session, students will be able to:

* Understand what CSS selectors are and why they matter
* Use element selectors effectively
* Create and use classes
* Create and use IDs
* Understand selector specificity fundamentals
* Style multiple elements efficiently
* Use grouping selectors and descendant selectors
* Organize CSS professionally

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Discussion

Ask students:

Imagine a website with:

```text
50 headings
30 buttons
20 cards
15 sections
```

Would you write this?

```css
h1 {
 color: blue;
}

h1 {
 color: blue;
}

h1 {
 color: blue;
}
```

50 times?

Of course not.

CSS gives us selectors so we can target elements efficiently.

---

# What Is a Selector?

A selector tells CSS:

> "Which HTML element should receive these styles?"

Example:

```css
h1 {
    color: blue;
}
```

Selector:

```css
h1
```

Meaning:

```text
Apply this style to every h1 element.
```

---

# Real-World Analogy

Imagine you're a teacher.

You say:

```text
All students stand up.
```

You're targeting everyone.

Now imagine:

```text
Only students in Group A stand up.
```

You're targeting a specific group.

Selectors work the same way.

---

# Why Selectors Matter in Modern Development

Modern websites contain thousands of elements.

Examples:

* Netflix
* Airbnb
* Stripe
* ChatGPT
* GitHub

Without selectors, maintaining styles becomes impossible.

Selectors are one of the foundations of professional CSS.

---

# Types of Selectors We'll Learn Today

### Element Selectors

```css
h1 {}
```

---

### Class Selectors

```css
.card {}
```

---

### ID Selectors

```css
#hero {}
```

---

### Group Selectors

```css
h1, h2 {}
```

---

### Descendant Selectors

```css
nav a {}
```

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Part 1: Element Selectors

HTML:

```html
<h1>Frontend Development</h1>

<p>Learning CSS Selectors</p>
```

CSS:

```css
h1 {
    color: blue;
}

p {
    color: gray;
}
```

Result:

Every h1 becomes blue.

Every p becomes gray.

---

## Problem with Element Selectors

Imagine:

```html
<h1>Home</h1>

<h1>About</h1>

<h1>Contact</h1>
```

All become identical.

What if we want different styling?

We need classes.

---

# Part 2: Introduction to Classes

HTML:

```html
<h1 class="main-title">
    Frontend Development
</h1>
```

CSS:

```css
.main-title {
    color: navy;
}
```

---

## Explain the Dot

Class selectors always start with:

```css
.
```

Example:

```css
.main-title
```

---

## Multiple Elements, Same Class

HTML:

```html
<p class="highlight">
    HTML
</p>

<p class="highlight">
    CSS
</p>

<p class="highlight">
    JavaScript
</p>
```

CSS:

```css
.highlight {
    color: red;
}
```

All three become red.

---

# Why Classes Are Powerful

One class.

Many elements.

Example:

```css
.button {
    background-color: blue;
}
```

Can style:

* Login button
* Signup button
* Contact button

All at once.

---

# Part 3: IDs

HTML:

```html
<h1 id="hero-title">
    Welcome
</h1>
```

CSS:

```css
#hero-title {
    color: green;
}
```

---

## Explain Hash Symbol

ID selectors begin with:

```css
#
```

Example:

```css
#hero-title
```

---

## Class vs ID

### Class

Can be reused.

```html
<p class="highlight"></p>

<p class="highlight"></p>
```

Perfectly valid.

---

### ID

Must be unique.

```html
<h1 id="hero"></h1>
```

Only one hero section.

---

# Real-World Usage

Classes:

```text
Buttons
Cards
Forms
Navigation Links
```

Reusable.

---

IDs:

```text
Hero Section
Main Navigation
Footer
```

Unique.

---

# Part 4: Grouping Selectors

Without grouping:

```css
h1 {
    color: navy;
}

h2 {
    color: navy;
}

h3 {
    color: navy;
}
```

---

Better:

```css
h1,
h2,
h3 {
    color: navy;
}
```

Cleaner code.

---

# Part 5: Descendant Selectors

HTML:

```html
<nav>

    <a href="#">Home</a>

    <a href="#">About</a>

</nav>
```

CSS:

```css
nav a {
    color: red;
}
```

Meaning:

```text
Style links inside nav.
```

Only navigation links affected.

---

# Part 6: Multiple Classes

HTML:

```html
<p class="highlight large-text">
    Frontend Development
</p>
```

CSS:

```css
.highlight {
    color: red;
}

.large-text {
    font-size: 30px;
}
```

Element receives both styles.

---

# Part 7: Build Portfolio Sections

HTML:

```html
<section class="card">

    <h2>About Me</h2>

    <p>
        Frontend student.
    </p>

</section>
```

CSS:

```css
.card {

    background-color: white;

}
```

Add more sections:

```html
<section class="card">

    <h2>Skills</h2>

</section>

<section class="card">

    <h2>Projects</h2>

</section>
```

All share styling.

---

# Part 8: Portfolio Styling System

HTML:

```html
<h1 id="hero-title">
    Goodluck Njoku
</h1>

<p class="subtitle">
    Frontend Developer
</p>

<p class="subtitle">
    Building Modern Websites
</p>
```

CSS:

```css
#hero-title {

    color: navy;

}

.subtitle {

    color: gray;

}
```

Professional structure emerges.

---

# 70–100 Minutes: Guided Practice & Challenges

---

# Exercise 1: Highlight Important Text

Create:

```html
<p class="important">
Important Announcement
</p>
```

Style:

```css
.important {
    color: red;
}
```

---

# Exercise 2: Reusable Card Class

Create three sections.

All must use:

```html
class="card"
```

Expected:

All share same appearance.

---

# Exercise 3: Hero Section

Create:

```html
<h1 id="hero">
Welcome
</h1>
```

Style uniquely.

---

# Exercise 4: Navigation Links

Create:

```html
<nav>

<a>Home</a>

<a>About</a>

<a>Contact</a>

</nav>
```

Use:

```css
nav a
```

---

# Exercise 5 (Challenge)

Build:

```text
Portfolio Homepage
```

Requirements:

### Unique Hero Title

Use ID.

### Reusable Cards

Use classes.

### Navigation Styling

Use descendant selector.

### Grouped Heading Styles

Use grouping selectors.

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

How do we target a class?

Answer:

```css
.class-name
```

---

How do we target an ID?

Answer:

```css
#id-name
```

---

Can classes be reused?

Answer:

Yes.

---

Can IDs be reused?

Answer:

No.

---

What selector styles links inside navigation?

Answer:

```css
nav a
```

---

# Common Mistakes

---

## Forgetting Dot for Classes

Wrong:

```css
card {
}
```

Correct:

```css
.card {
}
```

---

## Forgetting Hash for IDs

Wrong:

```css
hero {
}
```

Correct:

```css
#hero {
}
```

---

## Reusing IDs

Wrong:

```html
<h1 id="hero"></h1>

<h2 id="hero"></h2>
```

IDs must be unique.

---

## Styling Wrong Selector

HTML:

```html
<p class="intro">
```

Wrong CSS:

```css
.introduction {
}
```

Names must match exactly.

---

# 110–120 Minutes: Homework Briefing

---

# Homework Assignment

## Basic Level

Create:

```text
selectors-practice.html
```

Requirements:

* One class
* One ID
* One grouped selector

---

## Standard Level

Upgrade portfolio:

Add:

```text
Hero Section
About Section
Skills Section
```

Use:

* Classes
* IDs

---

## Challenge Level

Build:

```text
developer-showcase.html
```

Requirements:

### Hero Section

Unique ID.

### Three Information Cards

Reusable class.

### Navigation

Descendant selector.

### Headings

Grouping selector.

Apply styling professionally.

---

# Key Concepts & Teaching Notes

---

# Classes Are Reusable

Think:

```text
Uniforms
```

Many students wear the same uniform.

Many HTML elements use the same class.

---

# IDs Are Unique

Think:

```text
Student ID Number
```

Each student has one unique identifier.

---

# Professional CSS Relies Heavily on Classes

Modern frameworks:

* Bootstrap
* Tailwind
* Material UI

Use classes extensively.

Students should become comfortable with them now.

---

# Selectors Create Maintainable Code

Bad:

```css
Inline styles everywhere
```

Good:

```css
Reusable classes
```

One change updates many elements.

---

# Live Coding Example (Final Version)

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <title>Portfolio</title>

    <link
        rel="stylesheet"
        href="style.css">

</head>

<body>

    <nav>

        <a href="#">Home</a>

        <a href="#">About</a>

        <a href="#">Projects</a>

    </nav>

    <h1 id="hero-title">
        Goodluck Njoku
    </h1>

    <p class="subtitle">
        Frontend Developer
    </p>

    <section class="card">

        <h2>About Me</h2>

        <p>
            Learning modern frontend development.
        </p>

    </section>

    <section class="card">

        <h2>Skills</h2>

        <p>
            HTML, CSS, JavaScript
        </p>

    </section>

</body>

</html>
```

---

## CSS

```css
#hero-title {

    color: navy;

    text-align: center;

}

.subtitle {

    text-align: center;

    color: gray;

}

.card {

    background-color: white;

}

nav a {

    color: blue;

}

h1,
h2 {

    font-family: Arial, sans-serif;

}
```

---

# Resources & References

## Official Documentation

* [MDN CSS Selectors Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors?utm_source=chatgpt.com)
* [MDN Class Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors?utm_source=chatgpt.com)
* [MDN ID Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors?utm_source=chatgpt.com)

---

## Practice Resources

* [CSS Diner (Selectors Game)](https://flukeout.github.io/?utm_source=chatgpt.com)
* [Frontend Mentor](https://www.frontendmentor.io/?utm_source=chatgpt.com)
* [CodePen](https://codepen.io/?utm_source=chatgpt.com)

---

## YouTube Recommendations

* [Kevin Powell CSS Selectors Playlist](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)
* [Traversy Media CSS Crash Course](https://www.youtube.com/@TraversyMedia?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

## Prefer Classes Over IDs for Styling

Modern projects mostly use:

```css
.button
.card
.container
```

rather than IDs.

IDs are often reserved for:

* JavaScript hooks
* Page anchors
* Unique sections

---

## Use Meaningful Class Names

Good:

```css
.hero-title
.product-card
.primary-button
```

Bad:

```css
.red-text
.big-box
```

Describe purpose, not appearance.

---

## Keep CSS Reusable

A good class can be used hundreds of times across a project.

---

## Think Component-Based

Modern frontend frameworks like React encourage building reusable UI pieces.

Classes are your first step toward component thinking.

---

# Portfolio Project Progress

Students now have:

```text
portfolio/
│
├── index.html
├── about.html
├── contact.html
├── style.css
└── images/
```

With:

```text
✓ Hero Section
✓ Navigation
✓ Reusable Cards
✓ Classes
✓ IDs
✓ Organized Styling
```

The portfolio is starting to resemble a real product rather than a collection of pages.

---

# Preview of Session 9: The CSS Box Model

Next session students will learn one of the most important concepts in frontend development:

* Width
* Height
* Padding
* Border
* Margin
* Content Area
* Spacing Systems

By the end of Session 9, students will understand why elements occupy space and how professional layouts are built using the CSS Box Model.
