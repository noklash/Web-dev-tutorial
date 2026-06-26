# Session 13: CSS Units, Responsive Sizing & CSS Custom Properties (Variables)

> **Course:** Modern Frontend Development with HTML, CSS, JavaScript & AI Integration (2026)
> **Session Length:** 120 Minutes
> **Module:** CSS Foundations
> **Portfolio Milestone:** Refactor the portfolio into a maintainable, scalable website using responsive units and CSS variables (design tokens).

---

# Learning Objectives

By the end of this session, students will be able to:

* Explain the difference between absolute and relative CSS units
* Use `px`, `%`, `em`, `rem`, `vw`, `vh`, and `fr` appropriately
* Understand why `rem` is preferred for scalable typography
* Build fluid layouts using percentages and viewport units
* Create and use CSS Custom Properties (Variables)
* Organize reusable design tokens for colors, spacing, and typography
* Apply responsive sizing principles that prepare students for media queries and Flexbox

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Activity

Show students two websites.

### Website A

```text
Desktop looks good.

On mobile:

Text is tiny.

Cards overflow.

Buttons are too small.
```

---

### Website B

```text
Desktop looks great.

Tablet looks great.

Phone looks great.

Everything scales naturally.
```

Ask:

> Which developer would companies hire?

Obviously Website B.

---

## Why Responsive Sizing Matters

People browse websites on:

* Phones
* Tablets
* Laptops
* Ultra-wide monitors
* TVs
* Foldable devices

Your website must adapt.

Responsive design starts with choosing the correct CSS units.

---

# Absolute vs Relative Units

There are two major categories.

## Absolute Units

Always stay the same.

Examples:

```css
px
```

---

## Relative Units

Depend on something else.

Examples

```css
%

em

rem

vw

vh

fr
```

These make responsive design possible.

---

# Real-World Analogy

Imagine buying clothes.

Absolute sizing:

```text
Medium
```

Always stays medium.

Relative sizing:

```text
Sized according to your body.
```

Adjusts automatically.

Responsive CSS works similarly.

---

# CSS Units We'll Learn

| Unit | Meaning            | Common Use          |
| ---- | ------------------ | ------------------- |
| px   | Pixels             | Borders, icons      |
| %    | Percentage         | Widths              |
| em   | Relative to parent | Component scaling   |
| rem  | Relative to root   | Typography          |
| vw   | Viewport Width     | Hero sections       |
| vh   | Viewport Height    | Full-screen layouts |
| fr   | Fraction           | CSS Grid (preview)  |

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Part 1: Pixels (px)

HTML

```html
<div class="box">

Hello CSS

</div>
```

CSS

```css
.box{

width:300px;

height:150px;

background:#2563eb;

}
```

Explain:

Pixels are fixed.

300px remains 300px.

---

Advantages

* Predictable
* Simple

Disadvantages

* Less flexible on different screens

---

# Part 2: Percentages (%)

HTML

```html
<div class="container">

<div class="box">

Content

</div>

</div>
```

CSS

```css
.container{

width:800px;

}

.box{

width:50%;

}
```

Observe:

The child becomes:

```text
400px
```

Change parent width.

Observe child changes automatically.

---

Explain:

Percentages depend on the parent.

---

# Part 3: em

Explain:

```text
Relative to parent font size
```

Example

```css
.parent{

font-size:20px;

}

.child{

font-size:2em;

}
```

Result

```text
40px
```

---

Discuss why nested `em` values can become confusing.

---

# Part 4: rem

One of the most important CSS units.

Explain:

```text
Relative to root (html)
```

Browser default:

```css
html{

font-size:16px;

}
```

Then

```css
h1{

font-size:3rem;

}
```

Result

```text
48px
```

---

Why professionals love rem

Changing one value updates the entire typography system.

---

# Part 5: Viewport Width (vw)

Example

```css
.hero{

width:100vw;

}
```

Explain:

100%

of

the viewport width.

---

Try

```css
width:50vw;
```

Resize browser.

Observe.

---

# Part 6: Viewport Height (vh)

Example

```css
.hero{

height:100vh;

}
```

Result

Hero fills entire screen.

Common use:

Landing pages.

---

# Part 7: Mixing Units

Professional CSS often combines units.

Example

```css
.card{

width:80%;

max-width:400px;

padding:2rem;

}
```

Discuss why mixing units is powerful.

---

# Part 8: Introduction to CSS Variables

Without variables

```css
h1{

color:#2563eb;

}

button{

background:#2563eb;

}

a{

color:#2563eb;

}
```

Repeated everywhere.

---

Instead

```css
:root{

--primary:#2563eb;

}
```

Use

```css
h1{

color:var(--primary);

}
```

---

Explain

Variables store reusable values.

---

# Part 9: Multiple Variables

```css
:root{

--primary:#2563eb;

--secondary:#7c3aed;

--background:#f8fafc;

--text:#1e293b;

}
```

Use

```css
body{

background:var(--background);

color:var(--text);

}
```

---

# Part 10: Typography Variables

```css
:root{

--fs-heading:3rem;

--fs-body:1rem;

}
```

Use

```css
h1{

font-size:var(--fs-heading);

}
```

---

# Part 11: Spacing Variables

```css
:root{

--space-small:10px;

--space-medium:20px;

--space-large:40px;

}
```

Use

```css
.card{

padding:var(--space-medium);

}
```

---

# Part 12: Build a Mini Design System

```css
:root{

--primary:#2563eb;

--text:#1e293b;

--background:#f8fafc;

--radius:10px;

--spacing:20px;

--font-heading:3rem;

}
```

Students now have reusable design tokens.

---

# Part 13: Upgrade Portfolio

Replace hard-coded values.

Before

```css
padding:20px;

background:#2563eb;
```

After

```css
padding:var(--spacing);

background:var(--primary);
```

Cleaner.

Easier to maintain.

---

# 70–100 Minutes: Guided Practice & Challenges

---

## Exercise 1

Unit Playground

Create:

```html
<div class="box">

Responsive Box

</div>
```

Experiment with

```css
px

%

vw
```

Observe differences.

---

## Exercise 2

Typography Scaling

Use

```css
1rem

2rem

3rem
```

Resize browser text settings (if possible) and discuss accessibility benefits.

---

## Exercise 3

Create Variables

Create

```css
--primary

--background

--text
```

Apply throughout the page.

---

## Exercise 4

Spacing Tokens

Create

```css
--space-small

--space-medium

--space-large
```

Use in

* Cards
* Buttons
* Sections

---

## Exercise 5 (Challenge)

Refactor portfolio.

Requirements

Use variables for:

* Colors
* Typography
* Spacing
* Border radius

Replace all repeated values.

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

Which unit stays fixed?

Answer

```text
px
```

---

Which unit depends on the parent?

Answer

```text
%
```

---

Which unit is best for typography?

Answer

```text
rem
```

---

Which unit fills the screen height?

Answer

```text
100vh
```

---

How do you access a CSS variable?

Answer

```css
var(--primary)
```

---

Where are global variables usually declared?

Answer

```css
:root
```

---

# Common Mistakes

---

## Using Pixels Everywhere

Bad

```css
font-size:16px;

padding:20px;

margin:30px;
```

Better

Mix units strategically.

---

## Naming Variables Poorly

Bad

```css
--blue

--green
```

Better

```css
--primary

--secondary

--text
```

Names should describe purpose.

---

## Forgetting var()

Wrong

```css
color:--primary;
```

Correct

```css
color:var(--primary);
```

---

## Duplicating Values

Without variables

```css
#2563eb
```

Repeated 20 times.

Use variables instead.

---

## Ignoring Accessibility

Tiny fixed font sizes don't scale well.

Prefer

```css
rem
```

for text.

---

# 110–120 Minutes: Homework Briefing

# Homework Assignment

---

## Basic Level

Create

```text
units-practice.html
```

Requirements

Use:

* px
* %
* rem
* vw

Document observations.

---

## Standard Level

Create

```text
variables-demo.html
```

Include

* Three colors
* Three spacing variables
* Two typography variables

Use throughout the page.

---

## Challenge Level

Refactor your portfolio.

Requirements

Create a complete design token system.

Example

```css
:root{

--primary

--secondary

--background

--text

--radius

--space-small

--space-medium

--space-large

--heading-size

--body-size

}
```

Use these variables across the entire project.

---

# Key Concepts & Teaching Notes

---

# Choose Units Intentionally

Every CSS unit has a purpose.

Don't default to pixels.

---

# rem Is the Modern Standard

Most design systems use:

```css
rem
```

for typography because it respects user preferences and improves accessibility.

---

# Variables Reduce Maintenance

Changing

```css
--primary
```

updates every element using that variable.

This saves time on large projects.

---

# Think Like a Design System

Professional teams don't style pages individually.

They create reusable systems.

Variables are the first step toward that mindset.

---

# Responsive Design Starts Here

Media queries help later.

Choosing flexible units today makes future responsiveness much easier.

---

# Live Coding Example (Final Version)

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport"
content="width=device-width, initial-scale=1.0">

<title>CSS Variables Demo</title>

<link rel="stylesheet"
href="style.css">

</head>

<body>

<section class="hero">

<h1>

Goodluck Njoku

</h1>

<p>

Frontend Developer

</p>

</section>

</body>

</html>
```

---

## style.css

```css
:root{

--primary:#2563eb;
--background:#f8fafc;
--text:#1e293b;

--radius:12px;

--space-small:0.5rem;
--space-medium:1.25rem;
--space-large:3rem;

--heading:3rem;
--body:1rem;

}

body{

margin:0;

background:var(--background);

color:var(--text);

font-family:"Inter",sans-serif;

font-size:var(--body);

}

.hero{

background:var(--primary);

color:white;

padding:var(--space-large);

text-align:center;

border-radius:var(--radius);

}

h1{

font-size:var(--heading);

}
```

---

# Student In-Class Exercises

### Exercise 1

Compare `px`, `%`, `vw`, and `rem` by resizing the browser window and observing the behavior.

---

### Exercise 2

Build a simple design token system using CSS variables for colors and spacing.

---

### Exercise 3

Replace hard-coded colors in the portfolio with variables.

---

### Exercise 4

Create a responsive hero section using `vw`, `vh`, and `rem`.

---

### Exercise 5

Refactor the portfolio into a maintainable design system using CSS custom properties.

---

# Resources & References

## Official Documentation

* [MDN Values and Units Guide](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Values_and_units?utm_source=chatgpt.com)
* [MDN CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties?utm_source=chatgpt.com)
* [MDN var() Function](https://developer.mozilla.org/en-US/docs/Web/CSS/var?utm_source=chatgpt.com)

---

## Recommended Tools

* [Utopia Fluid Type Calculator](https://utopia.fyi/type/calculator?utm_source=chatgpt.com)
* [Utopia Fluid Space Calculator](https://utopia.fyi/space/calculator?utm_source=chatgpt.com)
* [CodePen](https://codepen.io/?utm_source=chatgpt.com)

---

## YouTube Recommendations

* [Kevin Powell - CSS Variables Explained](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)
* [Web Dev Simplified](https://www.youtube.com/@WebDevSimplified?utm_source=chatgpt.com)
* [freeCodeCamp CSS Course](https://www.youtube.com/@freecodecamp?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

## Prefer `rem` for Typography

Use `rem` for:

* Headings
* Paragraphs
* Buttons
* Form labels

This respects browser zoom and user accessibility settings.

---

## Build Design Tokens Early

Even small projects benefit from reusable variables for:

* Colors
* Typography
* Spacing
* Border radius
* Shadows

---

## Use Fluid Sizing Carefully

Combine relative units with constraints such as `max-width` to prevent layouts from becoming too wide on large screens.

---

## Keep Variable Names Semantic

Prefer:

```css
--primary
--surface
--text-muted
```

instead of:

```css
--blue
--gray
--dark
```

This makes redesigns much easier.

---

# Portfolio Project Progress

After Session 13, students have upgraded their portfolio into a more maintainable and scalable project:

```text
✓ Responsive CSS units
✓ Better typography scaling
✓ Flexible layouts
✓ CSS variables
✓ Design tokens
✓ Consistent spacing system
✓ Easier maintenance
```

Students are now thinking like frontend engineers who build systems rather than isolated pages.

---

# Preview of Session 14: CSS Positioning — Static, Relative, Absolute, Fixed & Sticky

In the next session, students will learn one of the most powerful—and often misunderstood—topics in CSS:

* The normal document flow
* `position: static`
* `position: relative`
* `position: absolute`
* `position: fixed`
* `position: sticky`
* The `z-index` property
* Layering UI elements
* Building sticky navigation bars and floating action buttons

By the end of Session 14, students will understand how to precisely position elements and build many of the interface patterns used in modern websites and web applications.
