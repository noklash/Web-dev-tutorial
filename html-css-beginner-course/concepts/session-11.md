# Session 11: CSS Typography, Fonts & Text Styling

> **Course:** Modern Frontend Development with HTML, CSS, JavaScript & AI Integration (2026)
> **Session Length:** 120 Minutes
> **Module:** CSS Foundations
> **Portfolio Milestone:** Build a professional typography system that dramatically improves readability and visual hierarchy across the portfolio website.

---

# Learning Objectives

By the end of this session, students will be able to:

* Explain why typography is one of the most important aspects of UI design
* Use CSS font properties to style text professionally
* Apply web-safe fonts and Google Fonts
* Control font size, weight, style, line height, and letter spacing
* Create visual hierarchy using typography
* Improve accessibility through readable typography
* Build a reusable typography system for their portfolio

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Activity

Show students two versions of the same page.

### Version A

```text
Arial
Everything same size
Tiny text
No spacing
Bold everywhere
```

---

### Version B

```text
Modern font
Clear headings
Comfortable spacing
Readable paragraphs
Professional appearance
```

Ask:

> Which website would you rather read for 10 minutes?

Almost everyone chooses Version B.

---

# Typography Is More Than Fonts

Many beginners think typography means:

```text
Choosing a fancy font
```

Professional designers know typography includes:

* Font family
* Font size
* Font weight
* Line height
* Letter spacing
* Word spacing
* Alignment
* Contrast
* Readability
* Hierarchy

Typography determines whether users enjoy reading your website.

---

# Real-World Examples

Excellent typography:

* Medium
* Notion
* Stripe
* Apple
* Linear
* GitHub Docs

Poor typography:

* Tiny text
* Low contrast
* Crowded paragraphs
* Random font sizes
* Inconsistent spacing

---

# Why Typography Matters in 2026

Users spend most of their time reading:

* Documentation
* Blogs
* Dashboards
* SaaS Applications
* Landing Pages
* Product Descriptions

Good typography improves:

* User trust
* Accessibility
* Conversion rates
* Reading speed
* Overall UX

---

# Typography Analogy

Imagine a book.

Even if the story is amazing...

If it's printed like this:

```text
tinyletterswithnospacingandbadformatting
```

People won't enjoy reading it.

Good typography makes content effortless to consume.

---

# CSS Typography Properties

Today we'll learn:

```css
font-family
font-size
font-weight
font-style
line-height
letter-spacing
text-transform
text-decoration
text-align
```

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Part 1: Font Family

HTML

```html
<h1>Frontend Development</h1>

<p>Welcome to the course.</p>
```

CSS

```css
body {

    font-family: Arial, sans-serif;

}
```

Explain:

The browser tries:

```text
Arial
```

If unavailable:

```text
sans-serif
```

acts as the fallback.

---

# What Is a Font Family?

Examples:

```css
font-family: Arial, sans-serif;

font-family: Verdana, sans-serif;

font-family: Georgia, serif;

font-family: "Courier New", monospace;
```

Discuss differences.

---

# Serif vs Sans-Serif

### Serif

```text
Traditional
Books
Formal
```

Examples:

* Georgia
* Times New Roman

---

### Sans-Serif

```text
Modern
Minimal
Digital
```

Examples:

* Arial
* Inter
* Roboto

Most modern websites use sans-serif fonts.

---

# Part 2: Font Size

```css
h1 {

    font-size: 48px;

}

p {

    font-size: 18px;

}
```

Observe hierarchy.

---

Explain:

Bigger text = More important.

---

Common Sizes

```text
Body:
16–18px

Subheading:
24–32px

Heading:
40–64px
```

---

# Part 3: Font Weight

```css
font-weight: normal;

font-weight: bold;

font-weight: 300;

font-weight: 500;

font-weight: 700;
```

Explain numeric values.

Professional websites often use:

```text
400
500
600
700
```

---

# Part 4: Font Style

```css
font-style: italic;
```

Used sparingly.

Common uses:

* Quotes
* Emphasis
* Captions

---

# Part 5: Line Height

One of the most overlooked properties.

Without:

```css
line-height: normal;
```

Paragraphs feel crowded.

---

Better:

```css
line-height: 1.6;
```

Observe dramatic improvement.

---

Explain:

Higher line height improves readability.

---

# Part 6: Letter Spacing

```css
letter-spacing: 2px;
```

Useful for:

* Buttons
* Logos
* Navigation
* Small uppercase labels

---

Too much:

```css
letter-spacing: 10px;
```

Looks awkward.

---

# Part 7: Text Alignment

```css
text-align: left;
```

```css
text-align: center;
```

```css
text-align: right;
```

Discuss:

Most paragraphs should remain left-aligned for readability.

---

# Part 8: Text Decoration

Default link:

```html
<a href="#">Visit</a>
```

Browser adds:

```text
Underline
```

Remove:

```css
a {

    text-decoration: none;

}
```

---

Discuss:

If removing underlines, provide another visual cue like hover effects or color.

---

# Part 9: Text Transform

```css
text-transform: uppercase;
```

Results:

```text
Frontend
```

becomes

```text
FRONTEND
```

Other values:

```css
lowercase

capitalize
```

---

# Part 10: Google Fonts

Visit:

[Google Fonts](https://fonts.google.com?utm_source=chatgpt.com)

Choose:

```text
Inter
```

Copy:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet"
href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap">
```

Use:

```css
body {

    font-family: "Inter", sans-serif;

}
```

Explain why custom fonts improve branding.

---

# Part 11: Typography System

Instead of styling randomly:

```css
h1 {

    font-size: 48px;

}

h2 {

    font-size: 32px;

}

p {

    font-size: 18px;

}
```

Maintain consistency.

---

# Part 12: Upgrade Portfolio

Apply:

```css
body {

    font-family: "Inter", sans-serif;

    line-height: 1.6;

}

h1 {

    font-size: 48px;

    font-weight: 700;

}

h2 {

    font-size: 30px;

}

p {

    font-size: 18px;

}
```

Portfolio immediately looks more polished.

---

# 70–100 Minutes: Guided Practice & Challenges

## Exercise 1: Font Comparison

Create:

```html
<h1>Typography Test</h1>
```

Try:

* Arial
* Georgia
* Verdana
* Courier New

Discuss readability.

---

## Exercise 2: Heading Hierarchy

Create:

```html
<h1>Main Title</h1>

<h2>Subtitle</h2>

<p>Body text.</p>
```

Use different font sizes and weights.

---

## Exercise 3: Reading Experience

Create a paragraph with 8–10 lines.

Experiment with:

```css
line-height:

1

1.4

1.8

2
```

Observe which is easiest to read.

---

## Exercise 4: Navigation Styling

Create:

```html
<nav>

<a>Home</a>

<a>About</a>

<a>Projects</a>

</nav>
```

Style:

* Remove underline
* Increase letter spacing
* Use uppercase
* Change font weight

---

## Exercise 5 (Challenge)

Build a:

```text
Developer Portfolio Hero Section
```

Include:

* Name
* Role
* Short introduction

Requirements:

* Google Font
* Professional spacing
* Typography hierarchy
* Consistent font sizes

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

What property changes the font?

Answer:

```css
font-family
```

---

What property controls text size?

Answer:

```css
font-size
```

---

What improves paragraph readability?

Answer:

```css
line-height
```

---

What property removes link underlines?

Answer:

```css
text-decoration
```

---

Which property converts text to uppercase?

Answer:

```css
text-transform
```

---

# Common Mistakes

---

## Using Too Many Fonts

Bad:

```text
Heading:
Comic Sans

Paragraph:
Times New Roman

Buttons:
Courier New

Navigation:
Papyrus
```

Use one or two font families maximum.

---

## Tiny Body Text

Bad:

```css
font-size: 10px;
```

Better:

```css
16px–18px
```

---

## Centering Long Paragraphs

Bad:

```css
text-align: center;
```

for large blocks of text.

Prefer:

```css
text-align: left;
```

---

## No Line Height

Without:

```css
line-height
```

paragraphs become difficult to read.

---

## Excessive Letter Spacing

Too much spacing makes words difficult to recognize.

---

# 110–120 Minutes: Homework Briefing

# Homework Assignment

---

## Basic Level

Create:

```text
typography-practice.html
```

Requirements:

* One heading
* One subheading
* Two paragraphs

Style using:

* Font family
* Font size
* Font weight

---

## Standard Level

Upgrade your portfolio.

Requirements:

* Use Google Fonts
* Improve heading hierarchy
* Improve paragraph readability
* Remove default link underlines

---

## Challenge Level

Build:

```text
personal-blog-homepage.html
```

Include:

* Hero heading
* Featured article
* Navigation
* About section

Apply:

* Professional typography
* Consistent spacing
* Readable paragraphs
* Modern font

---

# Key Concepts & Teaching Notes

---

# Typography Creates Hierarchy

Users should instantly know:

```text
What is most important?
```

Good typography answers this visually.

---

# Readability Beats Decoration

Choose fonts that are easy to read.

Avoid decorative fonts for body text.

---

# Consistency Is Critical

Don't randomly change:

* Font sizes
* Font weights
* Font families

Create a system.

---

# Google Fonts Is Industry Standard

Most modern websites use web fonts for branding and consistency.

Popular choices include:

* Inter
* Roboto
* Open Sans
* Poppins
* Lato

---

# Accessibility Matters

Readable typography benefits everyone, including users with visual impairments or reading difficulties.

Aim for:

* Good contrast
* Adequate font size
* Comfortable line height

---

# Live Coding Example (Final Version)

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0">

    <title>Typography Demo</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">

    <link rel="stylesheet"
          href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap">

    <link rel="stylesheet"
          href="style.css">

</head>

<body>

    <h1>Goodluck Njoku</h1>

    <h2>Frontend Developer</h2>

    <p>

        I enjoy building modern, responsive, and accessible web applications
        using HTML, CSS, and JavaScript.

    </p>

</body>

</html>
```

---

## style.css

```css
body {

    font-family: "Inter", sans-serif;

    background-color: whitesmoke;

    line-height: 1.6;

    padding: 40px;

}

h1 {

    font-size: 48px;

    font-weight: 700;

    color: #1e3a8a;

}

h2 {

    font-size: 30px;

    font-weight: 600;

    color: #475569;

}

p {

    font-size: 18px;

    color: #334155;

}

a {

    text-decoration: none;

    font-weight: 600;

}
```

---

# Student In-Class Exercises

1. Compare four different font families and discuss which works best for a portfolio website.

2. Build a typography hierarchy using `<h1>`, `<h2>`, and `<p>`.

3. Experiment with different `line-height` values and identify the most readable.

4. Style a navigation menu using uppercase text, increased letter spacing, and custom font weights.

5. Build a professional hero section using Google Fonts and a clear typography system.

---

# Resources & References

## Official Documentation

* [MDN CSS Fonts Guide](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Text_styling/Fundamentals?utm_source=chatgpt.com)
* [MDN font-family Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family?utm_source=chatgpt.com)
* [MDN line-height Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height?utm_source=chatgpt.com)
* [MDN text-decoration Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration?utm_source=chatgpt.com)

---

## Recommended Tools

* [Google Fonts](https://fonts.google.com?utm_source=chatgpt.com)
* [Fontpair (Font Pairing Inspiration)](https://www.fontpair.co?utm_source=chatgpt.com)
* [Type Scale Calculator](https://typescale.com?utm_source=chatgpt.com)

---

## YouTube Recommendations

* [Kevin Powell - Typography in CSS](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)
* [DesignCourse](https://www.youtube.com/@DesignCourse?utm_source=chatgpt.com)
* [freeCodeCamp CSS Full Course](https://www.youtube.com/@freecodecamp?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

## Build a Typography Scale

Instead of arbitrary values:

```css
16px
17px
29px
41px
```

Use a consistent scale, such as:

```text
16px
20px
24px
32px
48px
64px
```

---

## Limit Font Families

Most professional websites use:

* One primary font
* One optional accent font

---

## Prioritize Accessibility

* Body text: at least 16px
* Comfortable line-height: 1.5–1.8
* High color contrast
* Avoid long lines of centered text

---

## Think Design System

Professional teams define typography tokens early and reuse them throughout the project.

---

# Portfolio Project Progress

After Session 11, students have transformed their portfolio with:

```text
✓ Modern Google Font
✓ Professional typography hierarchy
✓ Improved readability
✓ Consistent heading sizes
✓ Better paragraph spacing
✓ Styled navigation links
```

Their websites now begin to resemble professional portfolios rather than simple student exercises.

---

# Preview of Session 12: CSS Colors, Backgrounds, Gradients & Visual Design

In the next session, students will learn how to create visually engaging interfaces using:

* Modern color theory
* Hex, RGB, HSL, and CSS Color Level 4 syntax
* Background images
* Linear and radial gradients
* Multiple backgrounds
* Background sizing and positioning
* Color accessibility and contrast

By the end of Session 12, students will have a visually polished landing page with modern color palettes and backgrounds that follow current 2026 design trends.
