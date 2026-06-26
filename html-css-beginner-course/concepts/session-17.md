# Session 17: CSS Grid — Building Modern Two-Dimensional Layouts

> **Course:** Modern Frontend Development with HTML, CSS, JavaScript & AI Integration (2026)
> **Session Length:** 120 Minutes
> **Module:** Modern CSS Layouts
> **Portfolio Milestone:** Refactor the Projects and Skills sections into professional CSS Grid layouts and build a responsive dashboard-style section.

---

# Learning Objectives

By the end of this session, students will be able to:

* Explain the difference between **Flexbox** and **CSS Grid**
* Understand Grid Containers and Grid Items
* Create rows and columns using `grid-template-columns` and `grid-template-rows`
* Use `repeat()`, `fr`, `minmax()`, and `gap`
* Build responsive card grids without relying heavily on media queries
* Create dashboard and gallery layouts using CSS Grid
* Know when to choose Grid versus Flexbox in real-world projects
* Use browser DevTools to inspect and debug Grid layouts

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Activity

Display two layouts.

### Layout 1

```text
Logo      Home   About   Contact
```

Ask:

> Which layout system would you use?

Answer:

**Flexbox**

One direction.

---

Now show:

```text
-----------------------------------

Project 1   Project 2   Project 3

Project 4   Project 5   Project 6

Project 7   Project 8   Project 9

-----------------------------------
```

Ask:

How would you build this?

Answer:

**CSS Grid**

---

## Why CSS Grid Exists

Flexbox solves:

One-dimensional layouts.

Either:

* Row

OR

* Column

Grid solves:

Rows

AND

Columns

at the same time.

---

## Real-World Analogy

Imagine organizing books.

Flexbox

↓

One shelf.

Grid

↓

Entire bookshelf.

Multiple shelves.

Multiple columns.

---

## Modern Development

Professional frontend developers rarely choose:

Grid

OR

Flexbox

Instead they combine both.

Example:

```
Page Layout
    ↓
Grid

Navigation
    ↓
Flexbox

Cards
    ↓
Flexbox

Dashboard
    ↓
Grid
```

---

# Grid Terminology

Two important concepts:

## Grid Container

Parent element.

```html
<section class="projects">

</section>
```

---

## Grid Items

Children.

```html
<section class="projects">

<div>One</div>

<div>Two</div>

<div>Three</div>

</section>
```

---

# The Magic Property

Everything starts with

```css
display:grid;
```

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Part 1: First Grid

HTML

```html
<section class="grid">

<div>1</div>

<div>2</div>

<div>3</div>

<div>4</div>

<div>5</div>

<div>6</div>

</section>
```

CSS

```css
.grid{

display:grid;

}
```

Observe.

Nothing exciting yet.

Explain:

We haven't defined columns.

---

# Part 2: Creating Columns

```css
.grid{

display:grid;

grid-template-columns:

200px 200px 200px;

}
```

Observe

Three columns appear.

---

Discuss

Each column is

200px wide.

---

# Part 3: Fraction Units (`fr`)

Instead of

```css
200px 200px 200px
```

use

```css
1fr 1fr 1fr
```

Explain

Fraction means

Share available space equally.

---

Experiment

```css
2fr 1fr 1fr
```

Observe

Column one becomes twice as wide.

---

Real-world analogy

Pizza.

```
1fr 1fr

↓

Equal slices
```

```
2fr 1fr

↓

One person gets two slices.
```

---

# Part 4: repeat()

Instead of

```css
1fr 1fr 1fr 1fr
```

write

```css
repeat(4,1fr)
```

Cleaner.

Professional.

---

# Part 5: gap

Old way

Margins.

Modern way

```css
gap:20px;
```

Works for

Rows

and

Columns.

---

# Part 6: Rows

Example

```css
grid-template-rows:

200px

200px;
```

Observe

Every row becomes

200px tall.

---

# Part 7: minmax()

One of Grid's best features.

Example

```css
grid-template-columns:

repeat(

auto-fit,

minmax(250px,1fr)

);
```

Explain slowly.

Minimum width

↓

250px

Maximum

↓

1 fraction.

Observe

Browser automatically chooses columns.

Resize window.

Students love this.

---

# Part 8: auto-fit vs auto-fill

Explain conceptually.

auto-fit

↓

Expands items.

auto-fill

↓

Keeps empty tracks.

For beginners,

recommend

```css
auto-fit
```

almost always.

---

# Part 9: Responsive Projects Section

CSS

```css
.projects{

display:grid;

grid-template-columns:

repeat(

auto-fit,

minmax(280px,1fr)

);

gap:25px;

}
```

Observe

Desktop

```
Card Card Card
```

Tablet

```
Card Card

Card
```

Phone

```
Card

Card

Card
```

Without media queries.

---

# Part 10: Dashboard Layout

Create

```
Stats

Chart

Tasks

Calendar
```

Use

Grid.

Explain

Dashboards almost always use CSS Grid.

---

# Part 11: Image Gallery

Create

Gallery

```
□ □ □

□ □ □

□ □ □
```

Using Grid.

Students immediately recognize Pinterest-like layouts.

---

# Part 12: Combining Grid and Flexbox

Projects Section

↓

Grid

Project Card

↓

Flexbox

Explain

Professional websites combine both.

---

# Part 13: Portfolio Refactor

Replace

Projects

Skills

Gallery

Certificates

with Grid.

Portfolio looks significantly more modern.

---

# Part 14: DevTools

Open Chrome DevTools.

Inspect

Grid overlay.

Explain

Professional debugging.

---

# 70–100 Minutes: Guided Practice & Challenges

---

# Exercise 1

Create

Three-column Grid.

Experiment

```css
1fr

2fr

repeat()

gap
```

---

# Exercise 2

Responsive Grid

Create

Eight cards.

Use

```css
repeat(auto-fit,minmax(250px,1fr))
```

Resize browser.

Observe.

---

# Exercise 3

Photo Gallery

Requirements

Nine images.

Three columns.

Gap between images.

---

# Exercise 4

Dashboard

Create

Four dashboard widgets.

Use Grid.

---

# Exercise 5 (Challenge)

Upgrade Portfolio.

Projects Section

↓

Grid

Skills

↓

Grid

Certificates

↓

Grid

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

Enable Grid?

Answer

```css
display:grid;
```

---

Equal columns?

Answer

```css
1fr
```

---

Repeat columns?

Answer

```css
repeat()
```

---

Responsive columns?

Answer

```css
minmax()
```

---

Spacing?

Answer

```css
gap
```

---

Best for two-dimensional layouts?

Answer

CSS Grid

---

# Common Mistakes

---

## Using Flexbox for Everything

Many beginners build dashboards with Flexbox.

Grid is simpler.

---

## Using Fixed Widths

Avoid

```css
300px
```

Prefer

```css
minmax()
```

---

## Forgetting Gap

Produces cramped layouts.

---

## Confusing Rows and Columns

Columns

↓

Vertical tracks

Rows

↓

Horizontal tracks

---

## Ignoring Browser Resize

Resize constantly.

Responsive design isn't theory.

---

# 110–120 Minutes: Homework Briefing

# Homework Assignment

---

## Basic Level

Create

```text
grid-practice.html
```

Requirements

Three columns

Gap

Six cards

---

## Standard Level

Build

Responsive Gallery

Requirements

Nine images.

Use

```css
repeat(auto-fit,minmax(250px,1fr))
```

---

## Challenge Level

Upgrade Portfolio.

Requirements

Projects

↓

Grid

Skills

↓

Grid

Certificates

↓

Grid

Responsive

No horizontal scrolling.

---

# Key Concepts & Teaching Notes

---

# Flexbox vs Grid

Students often struggle here.

Use this sentence repeatedly:

> **Flexbox manages items in one direction. Grid manages items in two directions.**

---

# Fraction Units Are Powerful

Avoid:

```css
width:33%;
```

Instead

```css
1fr
```

Cleaner.

---

# `repeat()` Improves Readability

Instead of

```css
1fr 1fr 1fr 1fr
```

Use

```css
repeat(4,1fr)
```

---

# `minmax()` Creates Truly Responsive Layouts

One of the most important Grid functions.

Professional developers use it daily.

---

# Grid + Flexbox Together

Real websites rarely choose one.

Grid organizes sections.

Flexbox organizes content inside each section.

---

# Live Coding Example (Final Version)

## HTML

```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport"
content="width=device-width,initial-scale=1">

<link rel="stylesheet"
href="style.css">

<title>Grid Demo</title>

</head>

<body>

<section class="projects">

<div class="card">

Project 1

</div>

<div class="card">

Project 2

</div>

<div class="card">

Project 3

</div>

<div class="card">

Project 4

</div>

<div class="card">

Project 5

</div>

<div class="card">

Project 6

</div>

</section>

</body>

</html>
```

---

## CSS

```css
body{

font-family:Arial,sans-serif;

background:#f8fafc;

margin:40px;

}

.projects{

display:grid;

grid-template-columns:

repeat(

auto-fit,

minmax(250px,1fr)

);

gap:20px;

}

.card{

background:white;

padding:30px;

border-radius:12px;

box-shadow:0 4px 10px rgba(0,0,0,.1);

display:flex;

justify-content:center;

align-items:center;

height:180px;

}
```

---

# Student In-Class Exercises

### Exercise 1

Build a three-column project grid using `repeat()` and `fr`.

---

### Exercise 2

Convert the grid into a responsive layout using `auto-fit` and `minmax()`.

---

### Exercise 3

Create a responsive image gallery with at least nine images.

---

### Exercise 4

Design a simple analytics dashboard with four statistic cards using CSS Grid.

---

### Exercise 5

Refactor the portfolio's Projects and Skills sections into Grid layouts while keeping the content inside each card aligned with Flexbox.

---

# Resources & References

## Official Documentation

* [MDN CSS Grid Layout Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout?utm_source=chatgpt.com)
* [MDN grid-template-columns](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns?utm_source=chatgpt.com)
* [MDN repeat() Function](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat?utm_source=chatgpt.com)
* [MDN minmax() Function](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax?utm_source=chatgpt.com)

---

## Interactive Practice

* [CSS Grid Garden](https://cssgridgarden.com?utm_source=chatgpt.com)
* [Grid by Example](https://gridbyexample.com?utm_source=chatgpt.com)

---

## YouTube Recommendations

* [Kevin Powell – CSS Grid Tutorials](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)
* [Web Dev Simplified – CSS Grid Crash Course](https://www.youtube.com/@WebDevSimplified?utm_source=chatgpt.com)
* [freeCodeCamp – CSS Grid Full Course](https://www.youtube.com/@freecodecamp?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

## Use Grid for Page Structure

Grid is ideal for:

* Dashboards
* Admin panels
* Portfolio galleries
* Pricing pages
* Feature sections
* Blog layouts

---

## Use Flexible Grid Tracks

Instead of fixed pixel columns:

```css
grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
```

This creates layouts that scale smoothly from mobile to ultrawide displays.

---

## Combine Grid and Flexbox

A common professional pattern is:

```text
Entire page
    ↓
CSS Grid

Each card
    ↓
Flexbox

Buttons inside cards
    ↓
Flexbox
```

Choosing the right tool at each level leads to simpler, more maintainable code.

---

## Inspect Grid with DevTools

Chrome and Firefox provide Grid overlays that display:

* Column lines
* Row lines
* Gaps
* Track sizes

Learning to use these tools early greatly improves debugging efficiency.

---

# Portfolio Project Progress

By the end of Session 17, students have elevated their portfolio to a production-style layout:

```text
✓ Responsive Projects Grid
✓ Skills Grid
✓ Certificate Gallery
✓ Dashboard-style statistics section
✓ Combined Grid + Flexbox architecture
✓ Mobile-friendly layouts with minimal CSS
```

Their portfolio now uses the same layout systems found in modern SaaS applications, agency websites, and developer portfolios.

---

# Preview of Session 18: Responsive Web Design — Media Queries, Mobile-First Design & Breakpoints

In the next session, students will build on Flexbox and Grid by learning how to adapt layouts intentionally for different devices.

Topics include:

* The mobile-first philosophy
* CSS media queries
* Common breakpoints
* Responsive typography
* Responsive navigation
* Responsive images
* Testing across screen sizes
* Building layouts that work from small phones to ultrawide monitors

By the end of Session 18, students will be able to deliver fully responsive websites that provide an excellent user experience across the wide range of devices used in 2026.
