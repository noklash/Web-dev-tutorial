



# JavaScript Lesson: Arrays 

## What You Will Learn
By the end of this lesson, you should be able to:

- Understand what an array is.
- Create an array.
- Access items inside an array.
- Add and remove items.
- Change values.
- Find the length of an array.
- Loop through an array.
- Use common array methods.

---

# What is an Array?

Imagine you have a shopping list:

- Bread
- Milk
- Eggs
- Butter

Instead of creating four different variables:

```javascript
let item1 = "Bread";
let item2 = "Milk";
let item3 = "Eggs";
let item4 = "Butter";
```

You can store everything inside **one variable**.

```javascript
let shoppingList = ["Bread", "Milk", "Eggs", "Butter"];
```

An **array** is simply a collection of values stored inside one variable.

Think of it as a box that can hold many items.

---

# Creating Arrays

### Strings

```javascript
let fruits = ["Apple", "Orange", "Mango"];
```

### Numbers

```javascript
let scores = [80, 95, 70, 100];
```

### Mixed Data Types

```javascript
let person = ["John", 20, true];
```

Although JavaScript allows different data types in one array, it's good practice to store similar types together.

---

# Array Index

Every item has a position called an **index**.

Arrays start counting from **0**, not 1.

```
Index:     0        1        2        3

Array:   Apple   Orange   Mango   Pear
```

---

# Accessing Items

```javascript
let fruits = ["Apple", "Orange", "Mango"];

console.log(fruits[0]);
```

Output:

```
Apple
```

Second item

```javascript
console.log(fruits[1]);
```

Output

```
Orange
```

Third item

```javascript
console.log(fruits[2]);
```

Output

```
Mango
```

---

# Changing an Item

```javascript
let fruits = ["Apple", "Orange", "Mango"];

fruits[1] = "Banana";

console.log(fruits);
```

Output

```
["Apple", "Banana", "Mango"]
```

---

# Finding the Length

```javascript
let fruits = ["Apple", "Orange", "Mango"];

console.log(fruits.length);
```

Output

```
3
```

`.length` tells us how many items are inside the array.

---

# Adding Items

## push()

Adds an item to the end.

```javascript
let fruits = ["Apple", "Orange"];

fruits.push("Mango");

console.log(fruits);
```

Output

```
["Apple", "Orange", "Mango"]
```

---

## unshift()

Adds an item to the beginning.

```javascript
let fruits = ["Orange", "Mango"];

fruits.unshift("Apple");

console.log(fruits);
```

Output

```
["Apple", "Orange", "Mango"]
```

---

# Removing Items

## pop()

Removes the last item.

```javascript
let fruits = ["Apple", "Orange", "Mango"];

fruits.pop();

console.log(fruits);
```

Output

```
["Apple", "Orange"]
```

---

## shift()

Removes the first item.

```javascript
let fruits = ["Apple", "Orange", "Mango"];

fruits.shift();

console.log(fruits);
```

Output

```
["Orange", "Mango"]
```

---

# Checking if an Item Exists

```javascript
let fruits = ["Apple", "Orange", "Mango"];

console.log(fruits.includes("Orange"));
```

Output

```
true
```

Another example

```javascript
console.log(fruits.includes("Banana"));
```

Output

```
false
```

---

# Finding the Position of an Item

```javascript
let fruits = ["Apple", "Orange", "Mango"];

console.log(fruits.indexOf("Orange"));
```

Output

```
1
```

If the item doesn't exist:

```javascript
console.log(fruits.indexOf("Banana"));
```

Output

```
-1
```

---

# Looping Through an Array

Instead of writing:

```javascript
console.log(fruits[0]);
console.log(fruits[1]);
console.log(fruits[2]);
```

Use a loop.

```javascript
let fruits = ["Apple", "Orange", "Mango"];

for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```

Output

```
Apple
Orange
Mango
```

---

# for...of Loop

An easier way to loop through arrays.

```javascript
let fruits = ["Apple", "Orange", "Mango"];

for (let fruit of fruits) {
    console.log(fruit);
}
```

Output

```
Apple
Orange
Mango
```

---

# Common Array Methods

| Method | Purpose |
|---------|---------|
| push() | Add to end |
| pop() | Remove from end |
| shift() | Remove from beginning |
| unshift() | Add to beginning |
| includes() | Check if item exists |
| indexOf() | Find an item's position |
| length | Count items |

---

# Example 1: Student Scores

```javascript
let scores = [65, 80, 92, 74];

console.log(scores[2]);
console.log(scores.length);

scores.push(100);

console.log(scores);
```

Output

```
92
4
[65, 80, 92, 74, 100]
```

---

# Example 2: Favorite Foods

```javascript
let foods = ["Rice", "Beans", "Pizza"];

foods.pop();

foods.push("Burger");

console.log(foods);
```

Output

```
["Rice", "Beans", "Burger"]
```

---

# Example 3: Loop Through Names

```javascript
let names = ["John", "Mary", "Peter", "Grace"];

for (let name of names) {
    console.log("Hello " + name);
}
```

Output

```
Hello John
Hello Mary
Hello Peter
Hello Grace
```

---

# Class Activity

Create an array called `colors` containing five colors.

1. Print the first color.
2. Print the last color.
3. Add `"Purple"` to the end.
4. Remove the first color.
5. Print the final array.

---

# Mini Project: Student Attendance

```javascript
let students = ["David", "Sarah", "John"];

console.log("Students Present:");

for (let student of students) {
    console.log(student);
}

students.push("Grace");

console.log("Updated List:");

for (let student of students) {
    console.log(student);
}
```

---

# Practice Questions

1. Create an array of five countries.
2. Print the third country.
3. Replace the second country with another one.
4. Add a new country to the end.
5. Remove the first country.
6. Print the total number of countries.
7. Check if `"Nigeria"` exists in the array.
8. Find the index of `"Ghana"`.
9. Loop through the array and print every country.
10. Create an array of five numbers and calculate their total using a loop.

---

# Key Takeaways

- An **array** stores multiple values in one variable.
- Array indexing starts at **0**.
- Use square brackets `[]` to create an array.
- Access items with `array[index]`.
- `.length` tells you the number of items.
- `push()` adds to the end.
- `pop()` removes from the end.
- `shift()` removes from the beginning.
- `unshift()` adds to the beginning.
- `includes()` checks whether an item exists.
- `indexOf()` returns the position of an item.
- Use `for` or `for...of` loops to work with every item in an array.

### Homework

Create a simple **Movie Collection** program.

1. Create an array containing five movie titles.
2. Display all the movies.
3. Add a new movie.
4. Remove one movie.
5. Display the updated list.
6. Display the total number of movies.
