# Session 16: Advanced Flexbox — `flex-wrap`, `flex-grow`, `flex-shrink`, `flex-basis` & Responsive Layout Patterns

> **Course:** Modern Frontend Development with HTML, CSS, JavaScript & AI Integration (2026)
> **Session Length:** 120 Minutes
> **Module:** Modern CSS Layouts
> **Portfolio Milestone:** Transform the portfolio into a responsive layout that adapts naturally to different screen sizes using advanced Flexbox techniques.

---

# Learning Objectives

By the end of this session, students will be able to:

* Explain how Flexbox distributes available space
* Use `flex-wrap` to create responsive layouts
* Understand `flex-grow`, `flex-shrink`, and `flex-basis`
* Use the `flex` shorthand property
* Build responsive card layouts without media queries
* Create equal-height cards using Flexbox
* Recognize when Flexbox is the right choice versus CSS Grid
* Debug advanced Flexbox layouts using browser DevTools

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Activity

Show students this layout.

Desktop

```text
-------------------------------------------------------

Card 1      Card 2      Card 3      Card 4

-------------------------------------------------------
```

Mobile

```text
-------------

Card 1

Card 2

Card 3

Card 4

-------------
```

Ask:

> Did the developer manually move every card?

Answer:

No.

Flexbox automatically rearranges items.

---

# Review from Previous Session

Students already know:

```css
display:flex;

justify-content;

align-items;

gap;

flex-direction;
```

Today we answer the next question:

> What happens when there isn't enough space?

---

# Why Advanced Flexbox Matters

Modern websites contain:

* Product cards
* Team members
* Pricing plans
* Dashboards
* Statistics cards
* Gallery layouts

All of these need to adapt automatically.

---

# Real-World Analogy

Imagine passengers boarding a bus.

If seats are available:

```text
🙂 🙂 🙂 🙂
```

Everyone sits comfortably.

If more passengers arrive:

Should they:

* Fall off the bus?

or

* Move to another row?

Flexbox chooses another row using:

```css
flex-wrap
```

---

# Space Distribution

Think of Flexbox as negotiating space.

Some items can grow.

Some items shrink.

Some keep their preferred size.

This negotiation is controlled by:

```css
flex-grow

flex-shrink

flex-basis
```

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Part 1: The Problem Without `flex-wrap`

HTML

```html
<section class="cards">

<div class="card">1</div>

<div class="card">2</div>

<div class="card">3</div>

<div class="card">4</div>

<div class="card">5</div>

<div class="card">6</div>

</section>
```

CSS

```css
.cards{

display:flex;

gap:20px;

}

.card{

width:250px;

height:150px;

background:#2563eb;

color:white;

}
```

Shrink browser window.

Observe:

Cards overflow.

---

# Part 2: `flex-wrap`

Solution

```css
.cards{

display:flex;

flex-wrap:wrap;

gap:20px;

}
```

Observe:

Cards automatically move onto new rows.

Explain

This is the beginning of responsive layouts.

---

# Part 3: `nowrap`

Default

```css
flex-wrap:nowrap;
```

Everything stays on one row.

Often causes overflow.

---

# Part 4: `wrap-reverse`

Try

```css
flex-wrap:wrap-reverse;
```

Observe

Rows appear in reverse order.

Rarely used but worth knowing.

---

# Part 5: Understanding `flex-grow`

Question:

Who gets extra space?

Example

```css
.card{

flex-grow:1;

}
```

Observe

Every card expands equally.

---

Now

```css
.card:nth-child(2){

flex-grow:2;

}
```

Observe

Card 2 becomes twice as wide.

Explain

Flex-grow determines how extra space is shared.

---

# Part 6: `flex-shrink`

Default

```css
flex-shrink:1;
```

Meaning

Items shrink when necessary.

Try

```css
.card{

flex-shrink:0;
}
```

Resize browser.

Observe

Cards refuse to shrink.

Overflow appears.

---

Explain

Useful when certain elements must keep their size.

---

# Part 7: `flex-basis`

Preferred starting size.

Example

```css
.card{

flex-basis:300px;
}
```

Explain

Browser begins layout assuming each card is 300px.

Remaining space is negotiated.

---

Compare

```css
width:300px;
```

vs

```css
flex-basis:300px;
```

Discuss differences.

---

# Part 8: The `flex` Shorthand

Instead of

```css
flex-grow:1;

flex-shrink:1;

flex-basis:250px;
```

Write

```css
flex:1 1 250px;
```

Meaning

```text
Grow = 1

Shrink = 1

Basis = 250px
```

Professionals often use shorthand.

---

# Part 9: Responsive Card Grid

CSS

```css
.cards{

display:flex;

flex-wrap:wrap;

gap:20px;

}

.card{

flex:1 1 300px;

padding:30px;

background:white;

border-radius:10px;

}
```

Resize browser.

Observe

Desktop

```text
Card Card Card
```

Tablet

```text
Card Card

Card
```

Phone

```text
Card

Card

Card
```

No media queries needed.

---

# Part 10: Equal Height Cards

Different content lengths.

Without Flexbox

Cards become uneven.

With

```css
display:flex;
```

Cards naturally match heights.

Professional appearance.

---

# Part 11: Pricing Cards

Create

```text
Starter

Pro

Enterprise
```

Different amounts of text.

Use

```css
display:flex;

align-items:stretch;
```

Observe

Equal height.

---

# Part 12: Portfolio Refactor

Convert

Projects Section

Skills Section

Services Section

Testimonials

to

```css
flex-wrap

flex

gap
```

Portfolio becomes naturally responsive.

---

# Part 13: DevTools

Inspect Flexbox.

Show

* Wrapping
* Flex overlay
* Item growth
* Available space

Professional debugging workflow.

---

# 70–100 Minutes: Guided Practice & Challenges

---

# Exercise 1

Wrapping Demo

Create six cards.

Resize browser.

Observe:

Before

```css
nowrap
```

After

```css
wrap
```

---

# Exercise 2

Growing Cards

Create

Three cards.

Assign

```css
1

2

1
```

for

```css
flex-grow
```

Observe width changes.

---

# Exercise 3

Responsive Team Section

Create

Four team members.

Use

```css
flex:1 1 250px;
```

Test responsiveness.

---

# Exercise 4

Pricing Table

Three pricing plans.

Equal heights.

Gap between cards.

---

# Exercise 5 (Challenge)

Upgrade Portfolio

Requirements

Responsive:

* Skills
* Projects
* Services
* Testimonials

Using

```css
flex-wrap

flex

gap
```

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

Which property allows wrapping?

Answer

```css
flex-wrap
```

---

Which property controls expansion?

Answer

```css
flex-grow
```

---

Which property controls shrinking?

Answer

```css
flex-shrink
```

---

Preferred starting size?

Answer

```css
flex-basis
```

---

Shorthand?

Answer

```css
flex
```

---

# Common Mistakes

---

## Forgetting Wrap

Without

```css
flex-wrap:wrap;
```

Cards overflow.

---

## Using Width Instead of Flex

Better

```css
flex:1 1 300px;
```

than

```css
width:300px;
```

for responsive layouts.

---

## Confusing Grow With Basis

Grow

↓

Extra space

Basis

↓

Starting size

---

## Using Huge Flex-Grow Values

Avoid

```css
flex-grow:999;
```

Usually unnecessary.

---

## Forgetting Gap

Margins create inconsistent spacing.

Prefer

```css
gap
```

---

# 110–120 Minutes: Homework Briefing

# Homework Assignment

---

## Basic Level

Create

```text
flex-wrap-demo.html
```

Practice

* Wrap
* No wrap

Observe differences.

---

## Standard Level

Build

Responsive Services Section

Requirements

Six cards.

Automatically wrap.

---

## Challenge Level

Upgrade Portfolio.

Every section should use

```css
flex-wrap

flex

gap
```

Test on:

Desktop

Tablet

Phone

---

# Key Concepts & Teaching Notes

---

# Flexbox Negotiates Space

Unlike older layout methods,

Flexbox continuously calculates:

* Available space
* Preferred sizes
* Growth
* Shrinkage

---

# Think Mobile First

Don't build only for desktop.

Shrink browser constantly while teaching.

Students should develop this habit early.

---

# `flex:1`

Common shorthand

```css
flex:1;
```

Equivalent to

```css
flex:1 1 0%;
```

Explain why this makes sibling elements share available space equally.

---

# Equal Height Cards Are Automatic

One of Flexbox's biggest advantages.

No hacks required.

---

# Flexbox Before Grid

Rule of thumb:

One direction?

↓

Flexbox.

Two directions?

↓

Grid.

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

<title>Advanced Flexbox</title>

</head>

<body>

<section class="cards">

<div class="card">

<h2>HTML</h2>

<p>Structure.</p>

</div>

<div class="card">

<h2>CSS</h2>

<p>Styling and layouts.</p>

</div>

<div class="card">

<h2>JavaScript</h2>

<p>Interactivity.</p>

</div>

<div class="card">

<h2>React</h2>

<p>Modern UI.</p>

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

margin:0;

padding:40px;

}

.cards{

display:flex;

flex-wrap:wrap;

gap:20px;

}

.card{

flex:1 1 280px;

padding:25px;

background:white;

border-radius:10px;

box-shadow:0 4px 10px rgba(0,0,0,.1);

}
```

Resize the browser window several times.

Students immediately see Flexbox adapting.

---

# Student In-Class Exercises

### Exercise 1

Build a responsive card grid using `flex-wrap`.

---

### Exercise 2

Experiment with different `flex-grow` values and explain the results.

---

### Exercise 3

Create a responsive team section using `flex: 1 1 250px`.

---

### Exercise 4

Build a pricing table with three equal-height cards.

---

### Exercise 5

Refactor the portfolio so that every multi-card section adapts gracefully from desktop to mobile.

---

# Resources & References

## Official Documentation

* [MDN flex-wrap Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap?utm_source=chatgpt.com)
* [MDN flex-grow Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow?utm_source=chatgpt.com)
* [MDN flex-shrink Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink?utm_source=chatgpt.com)
* [MDN flex-basis Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis?utm_source=chatgpt.com)
* [MDN flex Shorthand](https://developer.mozilla.org/en-US/docs/Web/CSS/flex?utm_source=chatgpt.com)

---

## Interactive Practice

* [Flexbox Froggy](https://flexboxfroggy.com?utm_source=chatgpt.com)
* [Flexbox Defense](https://www.flexboxdefense.com?utm_source=chatgpt.com)

---

## YouTube Recommendations

* [Kevin Powell – Advanced Flexbox](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)
* [Web Dev Simplified – Flexbox Deep Dive](https://www.youtube.com/@WebDevSimplified?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

## Prefer Flexible Components

Instead of fixed widths like:

```css
width: 300px;
```

prefer:

```css
flex: 1 1 300px;
```

This allows components to adapt gracefully across devices.

---

## Combine Flexbox with `max-width`

For readable layouts:

```css
.card {
    flex: 1 1 300px;
    max-width: 400px;
}
```

This prevents cards from becoming excessively wide on large displays.

---

## Use `gap` for Consistent Spacing

Avoid adding margins to every card. `gap` creates predictable spacing and works in both Flexbox and Grid.

---

## Know When to Stop Using Flexbox

Flexbox excels at **one-dimensional** layouts.

When you need:

* precise rows and columns
* magazine-style layouts
* dashboards
* photo galleries

it's time for **CSS Grid**.

---

# Portfolio Project Progress

By the end of Session 16, students have significantly improved the responsiveness of their portfolio:

```text
✓ Responsive card layouts
✓ Automatically wrapping project section
✓ Flexible skills section
✓ Responsive services grid
✓ Equal-height cards
✓ Cleaner, scalable Flexbox architecture
```

The portfolio now behaves like a modern production website across desktop, tablet, and mobile devices.

---

# Preview of Session 17: CSS Grid — Building Two-Dimensional Layouts

In the next session, students will learn **CSS Grid**, the second major modern layout system.

Topics include:

* Why Grid exists alongside Flexbox
* Grid containers and grid items
* Rows and columns
* `grid-template-columns`
* `grid-template-rows`
* `gap`
* `repeat()`
* `minmax()`
* `fr` units
* Building dashboards, galleries, pricing pages, and magazine layouts

By the end of Session 17, students will understand when to use **Flexbox**, when to use **Grid**, and how the two technologies complement each other in professional frontend development.
