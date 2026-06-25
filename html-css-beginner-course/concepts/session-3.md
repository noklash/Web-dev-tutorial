# Session 3: HTML Links, Images, Lists & Website Navigation

## Learning Objectives

By the end of this session, students will be able to:

* Understand how websites connect pages together
* Create hyperlinks using anchor (`<a>`) elements
* Add and optimize images using the `<img>` element
* Build ordered and unordered lists
* Understand relative and absolute file paths
* Create navigation menus between multiple pages
* Build a simple multi-page personal website

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Warm-Up Discussion

Ask students:

> "How do you move from YouTube's homepage to a video?"

> "How do you move from Amazon's homepage to a product page?"

The answer:

**Links.**

Without links, websites would be isolated pages.

The modern web is literally a giant network of connected documents.

This is why it's called:

> **World Wide Web**

---

# How Websites Connect

Example:

```text
Home Page
   |
   |--- About Page
   |
   |--- Contact Page
   |
   |--- Services Page
```

Every website uses navigation.

Examples:

* Netflix Menu
* Jumia Categories
* Airbnb Navigation
* GitHub Repository Pages

---

# What is a Hyperlink?

A hyperlink allows users to navigate to:

* Another webpage
* Another website
* A file
* An email address
* A section within the same page

HTML uses:

```html
<a>
```

Anchor element.

---

## Real-World Analogy

Think of a website as a city.

Pages = Buildings

Links = Roads

Without roads, people cannot move between buildings.

---

# Understanding URLs

Example:

```text
https://www.google.com
```

Parts:

```text
https://
```

Protocol

```text
www.google.com
```

Domain

---

# Relative vs Absolute Paths

This concept is critical.

Students often struggle here.

---

## Absolute Path

Points to a complete web address.

Example:

```html
<a href="https://www.google.com">
Google
</a>
```

Browser goes to Google.

---

## Relative Path

Points to a local file.

Example:

```html
<a href="about.html">
About
</a>
```

Browser looks in current project folder.

---

# Why This Matters in 2026

Every modern web application relies heavily on navigation.

Examples:

* Dashboard menus
* Documentation websites
* E-commerce stores
* SaaS platforms
* Learning platforms

Understanding navigation now makes React routing much easier later.

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Project Setup

Create folder:

```text
portfolio-website
│
├── index.html
├── about.html
├── contact.html
└── images
```

Explain project organization.

Professional developers organize files from day one.

---

# Part 1: Creating Links

Open:

```html
index.html
```

Add:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>My Portfolio</title>
</head>

<body>

    <h1>Welcome to My Website</h1>

    <a href="about.html">
        About Me
    </a>

</body>

</html>
```

Save.

Click link.

Nothing happens yet because page doesn't exist.

---

# Create about.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>About Me</title>
</head>

<body>

    <h1>About Me</h1>

    <p>
        I am learning frontend development.
    </p>

</body>

</html>
```

Test navigation.

---

# Demonstration: Back Navigation

Add:

```html
<a href="index.html">
    Home
</a>
```

Students see pages connecting.

---

# Part 2: Multiple Navigation Links

Create:

```html
<nav>

    <a href="index.html">
        Home
    </a>

    <a href="about.html">
        About
    </a>

    <a href="contact.html">
        Contact
    </a>

</nav>
```

Explain:

```html
<nav>
```

Represents website navigation.

Important for:

* Accessibility
* SEO
* Screen readers

---

# Create contact.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Contact</title>
</head>

<body>

    <h1>Contact Me</h1>

    <p>Email: example@email.com</p>

</body>

</html>
```

Test all links.

---

# Part 3: Opening Links in New Tabs

Normal:

```html
<a href="https://github.com">
GitHub
</a>
```

Same tab.

---

New tab:

```html
<a
 href="https://github.com"
 target="_blank">

GitHub

</a>
```

Explain:

```html
target="_blank"
```

Opens new tab.

---

Modern best practice:

```html
<a
 href="https://github.com"
 target="_blank"
 rel="noopener noreferrer">

GitHub

</a>
```

Explain security reasons.

---

# Part 4: Images

Students love this section.

Create:

```text
images
```

folder.

Add image:

```text
profile.jpg
```

---

Basic Image

```html
<img src="images/profile.jpg">
```

Explain:

Nothing appears if image path is wrong.

---

Add Alternative Text

```html
<img
 src="images/profile.jpg"
 alt="Profile picture">
```

Explain:

Alt text helps:

* Accessibility
* Screen readers
* SEO

---

Set Width

```html
<img
 src="images/profile.jpg"
 alt="Profile picture"
 width="300">
```

---

# Demonstration of Broken Paths

Wrong:

```html
<img
 src="profile.jpg"
 alt="Profile">
```

Browser cannot find image.

Discuss troubleshooting.

---

# Part 5: Lists

Lists are everywhere.

Examples:

* Product features
* Navigation menus
* To-do lists
* Documentation

---

# Unordered List

```html
<ul>

    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>

</ul>
```

---

# Ordered List

```html
<ol>

    <li>Learn HTML</li>
    <li>Learn CSS</li>
    <li>Learn JavaScript</li>

</ol>
```

Explain difference.

---

# Part 6: Build Learning Roadmap

```html
<h2>Skills To Learn</h2>

<ol>

    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
    <li>React</li>

</ol>
```

---

# Part 7: Complete Portfolio Homepage

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>My Portfolio</title>
</head>

<body>

    <nav>

        <a href="index.html">Home</a>

        <a href="about.html">About</a>

        <a href="contact.html">Contact</a>

    </nav>

    <h1>Welcome To My Portfolio</h1>

    <img
        src="images/profile.jpg"
        alt="Profile picture"
        width="300">

    <h2>Skills</h2>

    <ul>

        <li>HTML</li>

        <li>CSS</li>

        <li>JavaScript</li>

    </ul>

</body>

</html>
```

---

# 70–100 Minutes: Guided Practice & Challenges

---

# Exercise 1: Build Navigation

Create:

* Home page
* About page
* Contact page

Requirements:

```html
<nav>
```

on every page.

Expected result:

All pages connected.

---

# Exercise 2: Favorite Things Page

Create:

```text
favorites.html
```

Include:

* Favorite movies
* Favorite foods
* Favorite websites

Use lists.

---

# Exercise 3: Add Images

Add:

* Profile photo
* Favorite technology image

Requirements:

Proper alt text.

---

# Exercise 4: Learning Roadmap

Create:

```html
<h2>Frontend Journey</h2>
```

Using ordered list.

Expected output:

```text
1. HTML
2. CSS
3. JavaScript
4. React
5. Next.js
```

---

# Exercise 5 (Challenge)

Build:

```text
mini-portfolio
```

Pages:

```text
Home
About
Projects
Contact
```

Each page linked together.

Include image and lists.

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

# Review Questions

What element creates a hyperlink?

Answer:

```html
<a>
```

---

What attribute controls destination?

Answer:

```html
href
```

---

What element displays images?

Answer:

```html
<img>
```

---

What attribute describes an image?

Answer:

```html
alt
```

---

Difference between:

```html
<ul>
```

and

```html
<ol>
```

?

Unordered vs Ordered list.

---

# Common Mistakes

---

## Missing href

Wrong:

```html
<a>
Google
</a>
```

Correct:

```html
<a href="https://google.com">
Google
</a>
```

---

## Wrong Image Path

Wrong:

```html
<img src="mypic.jpg">
```

when image is inside:

```text
images/
```

Correct:

```html
<img src="images/mypic.jpg">
```

---

## Forgetting Alt Text

Wrong:

```html
<img src="photo.jpg">
```

Correct:

```html
<img
 src="photo.jpg"
 alt="Profile photo">
```

---

## Broken Navigation

Wrong:

```html
<a href="abt.html">
About
</a>
```

File doesn't exist.

Always verify filenames.

---

# 110–120 Minutes: Homework Briefing

# Homework Assignment

---

# Basic Level

Create:

```text
learning-roadmap.html
```

Requirements:

* Heading
* Ordered list
* At least 5 skills

---

# Standard Level

Create:

```text
personal-website
```

Pages:

```text
Home
About
Contact
```

Requirements:

* Navigation
* Images
* Lists

---

# Challenge Level

Build:

```text
Future Developer Portfolio
```

Pages:

```text
Home
About
Skills
Projects
Contact
```

Requirements:

* Working navigation
* Images
* Ordered lists
* Unordered lists
* External links

Bonus:

Link your:

* GitHub
* LinkedIn
* X profile

using:

```html
target="_blank"
```

---

# Key Concepts & Teaching Notes

---

## Hyperlinks Are The Foundation Of The Web

The internet is essentially billions of documents connected by links.

Without links:

* Search engines fail
* Navigation fails
* Websites become isolated

---

## Relative Paths

Most student bugs come from paths.

Example:

```text
project
│
├── index.html
└── about.html
```

Correct:

```html
<a href="about.html">
```

---

## Images Need Accessibility

Always ask:

> "What would a blind user hear?"

Example:

Bad:

```html
alt="image"
```

Good:

```html
alt="Frontend developer working on a laptop"
```

---

## Lists Create Structure

Professional websites use lists constantly.

Examples:

* Menus
* Features
* Benefits
* Product specifications

---

# Live Coding Example (Final)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Frontend Student Portfolio</title>
</head>

<body>

    <nav>

        <a href="index.html">Home</a>

        <a href="about.html">About</a>

        <a href="contact.html">Contact</a>

    </nav>

    <h1>Welcome To My Portfolio</h1>

    <img
        src="images/profile.jpg"
        alt="Profile picture"
        width="300">

    <h2>Current Skills</h2>

    <ul>

        <li>HTML</li>

        <li>CSS</li>

        <li>Git</li>

    </ul>

    <h2>Learning Roadmap</h2>

    <ol>

        <li>HTML</li>

        <li>CSS</li>

        <li>JavaScript</li>

        <li>React</li>

        <li>Next.js</li>

    </ol>

</body>

</html>
```

---

# Resources & References

## Official Documentation

* [MDN Anchor Element Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a?utm_source=chatgpt.com)
* [MDN Image Element Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img?utm_source=chatgpt.com)
* [MDN Lists Documentation](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Lists?utm_source=chatgpt.com)

## Tools

* [Pexels (Free Images)](https://www.pexels.com/?utm_source=chatgpt.com)
* [Unsplash (Free Images)](https://unsplash.com/?utm_source=chatgpt.com)
* [TinyPNG (Image Optimization)](https://tinypng.com/?utm_source=chatgpt.com)

## Recommended YouTube Channels

* [freeCodeCamp](https://www.youtube.com/@freecodecamp?utm_source=chatgpt.com)
* [Traversy Media](https://www.youtube.com/@TraversyMedia?utm_source=chatgpt.com)
* [Kevin Powell](https://www.youtube.com/@KevinPowell?utm_source=chatgpt.com)

---

# Modern Best Practices & 2026 Tips

### Use Meaningful Alt Text

Accessibility is not optional.

---

### Organize Files Properly

Good:

```text
project
│
├── images
├── pages
├── css
└── js
```

---

### Optimize Images

Large images slow websites.

Use:

* TinyPNG
* WebP format

---

### Avoid "Click Here"

Bad:

```html
<a href="about.html">
Click Here
</a>
```

Good:

```html
<a href="about.html">
Read About Me
</a>
```

Improves accessibility and SEO.

---

# Portfolio Project Progress

Current structure:

```text
portfolio
│
├── index.html
├── about.html
├── contact.html
└── images
```

Students now have their first **multi-page website**, a major milestone in becoming a frontend developer.

---

# Preview of Session 4: Semantic HTML & Page Structure

Next session students will learn:

* Semantic HTML
* `<header>`
* `<main>`
* `<section>`
* `<article>`
* `<aside>`
* `<footer>`
* Why semantic HTML matters for accessibility, SEO, AI crawlers, and professional development

Students will refactor their existing portfolio into a professional, semantic HTML structure used in modern production websites.
