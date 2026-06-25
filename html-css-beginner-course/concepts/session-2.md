# Session 2: HTML Fundamentals — Elements, Tags, Attributes & Document Structure

## Learning Objectives

By the end of this session, students will be able to:

* Understand the anatomy of an HTML document
* Differentiate between elements, tags, and attributes
* Create properly structured HTML pages
* Use common text-based HTML elements
* Understand nesting and parent-child relationships
* Build a structured personal profile webpage

---

# Total Time: 120 Minutes

---

# 0–20 Minutes: Introduction & Theory

## Recap from Session 1

Ask students:

* What is frontend development?
* What is HTML used for?
* What does CSS do?
* What does JavaScript do?

Quick reminder:

> HTML gives structure to a webpage.

Just like a house needs a foundation before painting or decoration, websites need HTML before CSS and JavaScript.

---

# What is an HTML Element?

An HTML element is the complete structure:

```html
<h1>Hello World</h1>
```

The entire line above is an element.

---

## What is a Tag?

The opening and closing parts are tags.

Opening Tag:

```html
<h1>
```

Closing Tag:

```html
</h1>
```

---

## Real-Life Analogy

Think of HTML like a package.

Package:

```html
<h1>Hello World</h1>
```

Container:

```html
<h1>
```

Content:

```html
Hello World
```

Closing Container:

```html
</h1>
```

---

# What Are Attributes?

Attributes provide extra information.

Example:

```html
<a href="https://google.com">
  Visit Google
</a>
```

Attribute:

```html
href="https://google.com"
```

Think of attributes as settings or instructions.

Examples:

* href
* src
* alt
* id
* class
* title

---

# Why Structure Matters in 2026

Modern tools rely on good HTML:

* Search engines
* Accessibility tools
* AI website builders
* Screen readers
* Browser automation

Poor HTML structure creates:

* Bad SEO
* Accessibility problems
* Maintenance headaches

Professional developers build structure first.

---

# HTML Document Structure Explained

Every HTML page follows this pattern:

```html
<!DOCTYPE html>
<html>
<head>
</head>
<body>
</body>
</html>
```

Let's understand each part.

---

## DOCTYPE

```html
<!DOCTYPE html>
```

Tells the browser:

> "This is a modern HTML5 document."

---

## HTML Element

```html
<html>
```

The root container.

Everything lives inside it.

---

## Head Section

```html
<head>
```

Contains information for:

* Browser
* Search engines
* Metadata

Users generally don't see this content.

---

## Body Section

```html
<body>
```

Contains everything users see.

Examples:

* Text
* Images
* Buttons
* Forms

---

# 20–70 Minutes: Live Coding & Instructor Demonstration

---

# Step 1: Create Proper HTML Boilerplate

Create:

```text
index.html
```

Add:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Profile</title>
</head>
<body>

</body>
</html>
```

Explain each line.

---

# Step 2: Add Metadata

Upgrade file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>My Profile</title>
</head>
<body>

</body>
</html>
```

---

## Explain Meta Tags

### Character Encoding

```html
<meta charset="UTF-8">
```

Allows support for:

* English
* French
* Arabic
* Emojis
* Most world languages

---

### Viewport

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Makes websites responsive.

Without it, mobile devices may render incorrectly.

---

# Step 3: Add Headings

Add:

```html
<h1>Goodluck Njoku</h1>
```

Discuss heading hierarchy:

```html
<h1>Main Title</h1>
<h2>Section</h2>
<h3>Subsection</h3>
<h4>Smaller Section</h4>
<h5>Minor Heading</h5>
<h6>Smallest Heading</h6>
```

---

## Demonstration

Bad:

```html
<h1>My Website</h1>
<h4>About Me</h4>
```

Good:

```html
<h1>My Website</h1>
<h2>About Me</h2>
```

Explain logical structure.

---

# Step 4: Add Paragraphs

```html
<p>
I am learning frontend development in 2026.
</p>
```

Discuss use cases:

* Blog posts
* Descriptions
* Product information

---

# Step 5: Add Multiple Sections

```html
<h1>Goodluck Njoku</h1>

<h2>About Me</h2>

<p>
I am an aspiring frontend developer.
</p>

<h2>Career Goals</h2>

<p>
I want to build modern web applications.
</p>
```

---

# Step 6: Demonstrate Nesting

Correct:

```html
<body>

    <h1>Portfolio</h1>

    <p>
        Welcome to my website.
    </p>

</body>
```

---

Incorrect:

```html
<body>

<h1>

<p>Hello</p>

</body>
```

Explain why tags must be properly closed.

---

# Step 7: Parent-Child Relationship

Example:

```html
<body>

    <section>

        <h2>About Me</h2>

        <p>Frontend student.</p>

    </section>

</body>
```

Hierarchy:

```text
body
 └─ section
     ├─ h2
     └─ p
```

This concept becomes important in CSS and JavaScript later.

---

# Step 8: Build Personal Profile Page

Final Demo:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>My Profile</title>
</head>

<body>

    <h1>Goodluck Njoku</h1>

    <h2>About Me</h2>

    <p>
        I am learning frontend development and building projects.
    </p>

    <h2>Goals</h2>

    <p>
        Become a professional frontend developer.
    </p>

    <h2>Favorite Technologies</h2>

    <p>
        HTML, CSS, JavaScript and React.
    </p>

</body>

</html>
```

---

# 70–100 Minutes: Guided Practice & Challenges

## Exercise 1 — Create Your Profile Page

Requirements:

* Name
* About Me
* Goal

Expected Structure:

```html
<h1>Name</h1>

<h2>About Me</h2>

<p>...</p>

<h2>Goal</h2>

<p>...</p>
```

---

## Exercise 2 — My Dream Company

Create:

```html
<h1>Dream Company</h1>

<h2>Why I Like It</h2>

<p>...</p>

<h2>Skills Needed</h2>

<p>...</p>
```

---

## Exercise 3 — My Learning Roadmap

Sections:

* HTML
* CSS
* JavaScript

Each section needs:

```html
<h2></h2>
<p></p>
```

---

## Exercise 4 — Create a Personal Blog Homepage

Must include:

* Main title
* About section
* Latest goals
* Learning journey

---

## Exercise 5 (Challenge)

Create:

```text
Future Developer Profile
```

Include:

* Name
* Future job title
* 3 career goals
* Why technology excites you

Use proper heading hierarchy.

---

# 100–110 Minutes: Review, Common Mistakes & Q&A

---

## Review Questions

What is an HTML element?

Answer:

An element includes:

```html
<h1>Hello</h1>
```

Entire structure.

---

What is a tag?

Answer:

Opening and closing markers.

```html
<h1></h1>
```

---

What is an attribute?

Answer:

Additional information for an element.

Example:

```html
href="..."
```

---

Where does visible webpage content go?

Answer:

```html
<body>
```

---

What goes inside the head section?

Answer:

* Title
* Meta tags
* Metadata

---

# Common Mistakes

## Missing Closing Tags

Wrong:

```html
<h1>Portfolio
```

Correct:

```html
<h1>Portfolio</h1>
```

---

## Wrong Nesting

Wrong:

```html
<p>
<h1>Hello</h1>
</p>
```

Correct:

```html
<h1>Hello</h1>

<p>
Welcome
</p>
```

---

## Multiple Main Titles

Avoid:

```html
<h1>About</h1>
<h1>Contact</h1>
<h1>Services</h1>
```

Prefer:

```html
<h1>Website Title</h1>

<h2>About</h2>
<h2>Contact</h2>
<h2>Services</h2>
```

---

# 110–120 Minutes: Homework Briefing

# Homework Assignment

---

## Basic Level

Create:

```text
about-me.html
```

Include:

* Name
* About Me
* Goals

Use:

```html
<h1>
<h2>
<p>
```

---

## Standard Level

Create:

```text
career-roadmap.html
```

Sections:

* Current Skills
* Skills To Learn
* Career Goals

Use proper heading hierarchy.

---

## Challenge Level

Create:

```text
future-portfolio.html
```

Must contain:

### About Me

### Career Journey

### Skills I Want To Learn

### Projects I Want To Build

### Where I See Myself In 5 Years

Use:

```html
<!DOCTYPE html>
<html>
<head>
<body>
<h1>
<h2>
<h3>
<p>
```

Structure everything correctly.

---

# Key Concepts & Teaching Notes

## Elements vs Tags

Students often confuse these.

Tag:

```html
<h1>
```

Element:

```html
<h1>Hello</h1>
```

Remember:

> Tags are pieces.
>
> Elements are complete units.

---

## HTML Is Not Programming

HTML is a markup language.

Its job:

* Structure content
* Describe content
* Organize content

Programming logic comes later with JavaScript.

---

## Nesting

Think of HTML like boxes inside boxes.

Example:

```text
House
 └ Room
     └ Table
         └ Book
```

HTML works similarly.

---

## Document Structure

Every professional webpage starts with:

```html
<!DOCTYPE html>
<html>
<head>
<body>
```

Students should memorize this pattern early.

---

# Live Coding Example (Final Version)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>Frontend Student Profile</title>
</head>

<body>

    <h1>Goodluck Njoku</h1>

    <h2>About Me</h2>

    <p>
        I enjoy building modern web applications.
    </p>

    <h2>Current Learning</h2>

    <p>
        HTML fundamentals and web development.
    </p>

    <h2>Career Goal</h2>

    <p>
        Become a professional frontend developer.
    </p>

</body>

</html>
```

---

# Resources & References

## Official Documentation

* [MDN HTML Elements Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element?utm_source=chatgpt.com)
* [MDN HTML Introduction](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content?utm_source=chatgpt.com)

## Tools

* [Visual Studio Code](https://code.visualstudio.com/?utm_source=chatgpt.com)
* [Chrome DevTools Documentation](https://developer.chrome.com/docs/devtools/?utm_source=chatgpt.com)

## Recommended Extensions

* Live Server
* Prettier
* Error Lens
* HTML CSS Support

---

# Modern Best Practices & 2026 Tips

### Always Use HTML5 Boilerplate

Start every project with:

```html
<!DOCTYPE html>
```

---

### Use Proper Heading Hierarchy

Good structure improves:

* Accessibility
* SEO
* AI indexing
* Screen reader navigation

---

### Format Your Code

Use:

* Prettier
* Consistent indentation
* Meaningful titles

---

### Think Like a Professional

Before writing code ask:

> "What structure does this page need?"

Not:

> "How do I make it look good?"

Structure first.
Style later.

---

# Portfolio Project Progress

Students add a new page:

```text
portfolio/
 ├── index.html
 └── about.html
```

The portfolio project officially begins taking shape.

---

# Preview of Session 3

In Session 3, students will learn:

* Lists
* Links
* Images
* File paths
* Website navigation
* Multi-page websites

By the end of Session 3, students will build their first connected multi-page website with working navigation menus, images, and links.
