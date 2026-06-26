# Session 20: CSS Variables (Custom Properties), Design Systems & Dark Mode (2026)

> **Course:** Modern Frontend Development with HTML, CSS, JavaScript & AI Integration (2026)
> **Session Length:** 120 Minutes
> **Module:** Modern CSS Architecture
> **Portfolio Milestone:** Convert the portfolio into a maintainable design system using CSS variables and implement a professional light/dark theme.

---

# Learning Objectives

By the end of this session, students will be able to:

* Explain what CSS Custom Properties (Variables) are and why they are essential in modern frontend development
* Declare and use CSS variables with `:root`
* Override variables for component-specific styling
* Build a simple design system using reusable tokens for colors, spacing, typography, and shadows
* Implement a light and dark theme using CSS variables
* Organize CSS for maintainability and scalability
* Understand how CSS variables work alongside JavaScript (preparing for future sessions)

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Activity

Show students this CSS:

```css
button {
  background: #2563eb;
}

.card {
  border: 1px solid #2563eb;
}

.hero-title {
  color: #2563eb;
}

a {
  color: #2563eb;
}

.icon {
  fill: #2563eb;
}
```

Ask:

> What happens if the client says, "Change the brand color to green"?

Students will realize they must search through the entire stylesheet.

Now show:

```css
:root {
  --primary-color: #2563eb;
}
```

Then:

```css
button {
  background: var(--primary-color);
}

.card {
  border-color: var(--primary-color);
}

.hero-title {
  color: var(--primary-color);
}
```

Now changing one value updates the entire application.

---

# Why CSS Variables Matter

Modern applications have:

* Hundreds of components
* Thousands of CSS rules
* Multiple themes
* Multiple developers

Without variables:

Maintenance becomes difficult.

With variables:

Everything stays consistent.

---

# Real-World Example

Ask students:

Imagine you're building Netflix.

If red changes slightly,

Would you edit:

500 files?

Or

One variable?

Professional developers always choose reusable design tokens.

---

# What Is a Design System?

A Design System is a collection of reusable design rules.

Examples include:

* Colors
* Fonts
* Font sizes
* Border radius
* Shadows
* Spacing
* Animation durations

Instead of repeating values everywhere, you define them once.

---

# Industry Examples

Many companies maintain comprehensive design systems:

* Google Material Design
* IBM Carbon
* Microsoft Fluent
* Shopify Polaris

Even small projects benefit from a lightweight design system.

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Part 1: Creating Your First Variable

CSS

```css
:root {

--primary-color:#2563eb;

}
```

Explain:

`:root` represents the highest level of the document.

Variables declared here are globally available.

---

# Part 2: Using Variables

Instead of:

```css
button {

background:#2563eb;

}
```

Use:

```css
button {

background:var(--primary-color);

}
```

Explain the syntax:

```css
var(--variable-name)
```

---

# Part 3: Multiple Variables

```css
:root {

--primary-color:#2563eb;

--secondary-color:#f97316;

--background:#ffffff;

--text:#111827;

}
```

Apply them across the project.

---

# Part 4: Typography Variables

```css
:root{

--font-heading:"Poppins",sans-serif;

--font-body:"Inter",sans-serif;

--text-sm:0.875rem;

--text-base:1rem;

--text-lg:1.25rem;

--text-xl:2rem;

}
```

Students begin separating content from presentation.

---

# Part 5: Spacing Variables

Instead of:

```css
padding:20px;

margin:20px;
```

Create:

```css
:root{

--space-xs:4px;

--space-sm:8px;

--space-md:16px;

--space-lg:24px;

--space-xl:40px;

}
```

Use:

```css
padding:var(--space-lg);
```

Explain:

Consistent spacing creates professional interfaces.

---

# Part 6: Border Radius Variables

```css
:root{

--radius-sm:6px;

--radius-md:10px;

--radius-lg:16px;

}
```

Use everywhere.

---

# Part 7: Shadow Variables

```css
:root{

--shadow-sm:

0 2px 4px rgba(0,0,0,.08);

--shadow-md:

0 8px 20px rgba(0,0,0,.12);

}
```

Cards become consistent.

---

# Part 8: Dark Mode

Create:

```css
:root{

--bg:#ffffff;

--text:#111827;

}
```

Dark theme:

```css
.dark{

--bg:#111827;

--text:#f9fafb;

}
```

Body:

```css
body{

background:var(--bg);

color:var(--text);

}
```

Observe:

Theme changes automatically.

---

# Part 9: Switching Themes

HTML

```html
<body class="dark">
```

Remove the class.

Observe:

Entire website changes.

Explain:

No need to rewrite individual components.

---

# Part 10: Variable Fallback

```css
color:var(--brand,#2563eb);
```

Explain:

If the variable doesn't exist,

use the fallback value.

---

# Part 11: Component Variables

Example:

```css
.card{

--card-padding:24px;

padding:var(--card-padding);

}
```

Variables can be scoped to individual components.

---

# Part 12: Refactoring the Portfolio

Replace hardcoded values with variables:

* Colors
* Font sizes
* Padding
* Margins
* Border radius
* Shadows

Students immediately notice how much cleaner the CSS becomes.

---

# Part 13: Organizing CSS

Introduce a common structure:

```text
styles/
│
├── variables.css
├── reset.css
├── typography.css
├── layout.css
├── components.css
└── main.css
```

Explain that as projects grow, organizing CSS improves maintainability.

---

# 70–100 Minutes: Guided Practice & Challenges

---

# Exercise 1

Create variables for:

* Primary color
* Secondary color
* Background
* Text

Use them in three components.

---

# Exercise 2

Replace every repeated color in the portfolio with variables.

---

# Exercise 3

Create spacing variables.

Replace all hardcoded padding values.

---

# Exercise 4

Implement a dark theme using variables.

Switch by adding/removing a class on `<body>`.

---

# Exercise 5 (Challenge)

Build a mini design system containing:

* Color palette
* Typography scale
* Spacing scale
* Border radius
* Shadows

Apply it across the portfolio.

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

Where should global variables usually be declared?

Answer:

```css
:root
```

---

How do you use a variable?

```css
var(--primary-color)
```

---

Can variables be overridden?

Answer:

Yes.

---

Can variables be used for spacing?

Answer:

Yes.

---

Can CSS variables power dark mode?

Answer:

Absolutely.

---

# Common Mistakes

---

## Forgetting `var()`

Wrong:

```css
color:--primary-color;
```

Correct:

```css
color:var(--primary-color);
```

---

## Naming Variables Poorly

Avoid:

```css
--blue
```

Prefer:

```css
--primary-color
```

Names should describe purpose, not appearance.

---

## Hardcoding New Values

After introducing variables,

don't return to:

```css
padding:23px;
```

Stay consistent.

---

## Creating Too Many Variables

Not every value needs a variable.

Only reuse frequently repeated values.

---

## Mixing Themes

Don't write separate styles for every component.

Override variables instead.

---

# 110–120 Minutes: Homework Briefing

# Homework Assignment

---

## Basic Level

Create:

```text
variables-demo.html
```

Use variables for:

* Colors
* Font sizes
* Padding

---

## Standard Level

Convert an existing landing page to use CSS variables throughout.

---

## Challenge Level

Refactor the portfolio:

* Complete design token system
* Light theme
* Dark theme
* Consistent spacing
* Consistent typography
* No repeated color values

---

# Key Concepts & Teaching Notes

---

# Variables Improve Maintainability

Instead of editing dozens of selectors,

change one variable.

---

# Think in Design Tokens

Instead of:

```css
#2563eb
```

Think:

```css
--primary-color
```

Instead of:

```css
20px
```

Think:

```css
--space-lg
```

---

# Variables Are Dynamic

Unlike preprocessor variables (e.g., Sass),

CSS variables exist in the browser and can change at runtime.

This makes them perfect for themes.

---

# Design Systems Scale

As projects grow,

design systems save time,

reduce bugs,

and create consistent user experiences.

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
<link rel="stylesheet" href="style.css">
<title>CSS Variables Demo</title>
</head>

<body>

<h1>Design System Demo</h1>

<button>Primary Button</button>

<div class="card">

<h2>Project Card</h2>

<p>Using reusable design tokens.</p>

</div>

</body>
</html>
```

---

## CSS

```css
:root{

--primary-color:#2563eb;

--background:#ffffff;

--text:#111827;

--space-lg:24px;

--radius-md:10px;

--shadow-md:0 8px 20px rgba(0,0,0,.12);

}

body{

background:var(--background);

color:var(--text);

font-family:Arial,sans-serif;

padding:var(--space-lg);

}

button{

background:var(--primary-color);

color:white;

padding:12px 24px;

border:none;

border-radius:var(--radius-md);

}

.card{

margin-top:24px;

padding:var(--space-lg);

border-radius:var(--radius-md);

box-shadow:var(--shadow-md);

background:white;

}

.dark{

--background:#111827;

--text:#f9fafb;

}
```

---

# Student In-Class Exercises

### Exercise 1

Create a global color palette using CSS variables and apply it to buttons, links, and headings.

---

### Exercise 2

Replace hardcoded spacing values with reusable spacing tokens.

---

### Exercise 3

Implement typography variables for headings and body text.

---

### Exercise 4

Create a light and dark theme using CSS variables. Toggle the theme by adding or removing a `.dark` class on the `<body>` element.

---

### Exercise 5

Refactor the portfolio so all repeated colors, spacing, border radii, and shadows come from a centralized design system.

---

# Resources & References

## Official Documentation

* [MDN CSS Custom Properties (Variables)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties?utm_source=chatgpt.com)
* [MDN var() Function](https://developer.mozilla.org/en-US/docs/Web/CSS/var?utm_source=chatgpt.com)

---

## Design System Resources

* [Material Design 3 Foundations](https://m3.material.io?utm_source=chatgpt.com)
* [IBM Carbon Design System](https://carbondesignsystem.com?utm_source=chatgpt.com)
* [Microsoft Fluent Design System](https://fluent2.microsoft.design?utm_source=chatgpt.com)

---

## YouTube Recommendations

* [Kevin Powell – CSS Variables Explained](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)
* [Web Dev Simplified – CSS Variables Tutorial](https://www.youtube.com/@WebDevSimplified?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

## Build a Token-Based Design System

Create variables for:

* Colors
* Typography
* Spacing
* Radius
* Shadows
* Animation durations
* Z-index values

This keeps the design consistent and easy to maintain.

---

## Use Semantic Variable Names

Prefer:

```css
--primary-color
--surface-color
--text-muted
```

instead of:

```css
--blue
--gray
--black
```

Semantic names make theme changes much easier.

---

## Prepare for JavaScript Integration

In upcoming JavaScript sessions, students will use JavaScript to switch themes by adding or removing classes. Because the styling is driven by variables, the JavaScript will remain simple and maintainable.

---

## Organize CSS as Projects Grow

Separate variables, layout, components, and utilities into dedicated files rather than keeping all styles in one large stylesheet.

---

# Portfolio Project Progress

By the end of Session 20, students have transformed their portfolio into a scalable, maintainable application:

```text
✓ Global color system
✓ Typography scale
✓ Consistent spacing system
✓ Reusable shadows and border radii
✓ Light theme
✓ Dark theme foundation
✓ Cleaner, professional CSS architecture
```

The portfolio now resembles the structure used in modern production applications and is well-prepared for JavaScript-driven interactions.

---

# Preview of Session 21: CSS Architecture, Naming Conventions & Building Maintainable Stylesheets

In the next session, students will learn how professional frontend teams organize large CSS codebases.

Topics include:

* CSS architecture principles
* Component-based styling
* Utility classes
* Naming conventions (including BEM)
* File organization
* Avoiding specificity conflicts
* Writing scalable, maintainable CSS
* Preparing for framework-based development (React, Vue, Angular)

By the end of Session 21, students will be writing CSS that remains readable and maintainable as projects grow from a few pages to large production applications.
