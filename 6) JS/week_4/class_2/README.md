# 🔁 **Loops in JavaScript**

---

# 🧩 **What Are Loops?**

A **loop** is a programming structure that repeats a block of code multiple times.

### 🔹 Real-life example:

Imagine you go to the market 5 times:

```
Going to the market
Buying potatoes
Coming back
Repeating again…
```

This is a **loop in real life**.

### 🔹 Why do we use loops?

Without loops:

```js
console.log("Buy potatoes");
console.log("Buy potatoes");
console.log("Buy potatoes");
console.log("Buy potatoes");
```

With a loop:

```js
for (let i = 0; i < 4; i++) {
    console.log("Buy potatoes");
}
```

Much simpler, clean, scalable.

---

# 🧩 **Why Loops Exist?**

Loops give:

* **Efficiency** → Write less, do more
* **Automation** → Repeated tasks run automatically
* **Control** → Stop when a condition becomes false
* **Flexibility** → Work with arrays, strings, inputs, and patterns

---

# 🧩 **Types of Loops in JavaScript**

JavaScript has **three** main looping mechanisms:

1. `for`
2. `while`
3. `do…while`

Let's master each one.

---

# 🧩 **for Loop**

Use the `for` loop when you know **exactly** how many times the loop should run.

### Syntax

```js
for (initialization; condition; increment/decrement) {
    // code to run
}
```

### Example

```js
for (let i = 1; i <= 5; i++) {
    console.log("Going to market");
}
```

### Printing numbers 1–5

```js
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

### Using conditions inside loop

```js
for (let i = 1; i <= 5; i++) {
    if (i % 2 === 0) {
        console.log(i + " is even");
    }
}
```

### Iterating over strings

```js
const str = "Hello";
for (let i = 0; i < str.length; i++) {
    console.log(str[i]);
}
```

### Reverse looping

```js
for (let i = 10; i >= 1; i--) {
    console.log(i);
}
```

```js
for (let i = arr.length - 1; i >= 0; i--) {
    console.log(arr[i]);
}
```

### break — stop the loop immediately

```js
for (let i = 1; i <= 5; i++) {
    if (i === 3) break;
    console.log(i);
}
```

### continue — skip the current iteration

```js
for (let i = 1; i <= 5; i++) {
    if (i === 3) continue;
    console.log(i);
}
```

### Multiple variables in for loop

```js
for (let i = 1, j = 10; i <= 10 && j >= 1; i++, j--) {
    console.log(i, j);
}
```

---

# 🧩 **while Loop — When You Don't Know Repetitions in Advance**

A `while` loop continues **as long as a condition is true**.

### Syntax

```js
while (condition) {
    // code runs
}
```

### ✔ Example

```js
let counter = 1;

while (counter <= 5) {
    console.log("Buying potatoes");
    counter++;
}
```

Useful when:

* You're waiting for user input
* You're reading files
* You're checking some repeated condition

---

# 🧩 **do…while Loop — Always Runs at Least One Time**

Even if the condition is false, the code runs **once**.

### Syntax

```js
do {
    // executed
} while (condition);
```

### Example

```js
let num = 1;

do {
    console.log(num);
    num++;
} while (num <= 5);
```

---

# 🧩 **Nested Loops (Loop inside another loop)**

Nested loops are used when working with **rows and columns**, **grids**, **tables**, **patterns**, and **2D data**.

### Single-Dimension vs Multi-Dimension

* **Single Dimension:**
  Array: `[1, 2, 3, 4]`
* **Multi Dimension:**
  Matrix:

  ```
  1 2 3
  4 5 6
  7 8 9
  ```

### Syntax

```js
for (outer; outerCondition; outer++) {
    for (inner; innerCondition; inner++) {
        // executes multiple times
    }
}
```

### Example

```js
for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 3; j++) {
        console.log(`Row: ${i}, Column: ${j}`);
    }
}
```

### Output

```
Row: 1, Column: 1
Row: 1, Column: 2
Row: 1, Column: 3
Row: 2, Column: 1
Row: 2, Column: 2
Row: 2, Column: 3
Row: 3, Column: 1
Row: 3, Column: 2
Row: 3, Column: 3
```

---

# 🧩 **Infinite Loops — Loops That Never Stop**

They occur when the condition **never becomes false**.

### ❗ Can crash programs or freeze browser.

### for loop infinite

```js
for (;;) {
    console.log("Runs forever");
}
```

### while loop infinite

```js
while (true) {
    console.log("Runs forever");
}
```

### do…while infinite

```js
do {
    console.log("Runs forever");
} while (true);
```

---

# 🏠 **Home Tasks**

1. Print numbers 1 to 50 using `for` loop.
2. Print even numbers 1–100 using `while` loop.
3. Print odd numbers 1–100 using `do…while` loop.
4. Find sum of numbers from 1 to n (user input).
5. Print multiplication table of user input.
6. Print reverse counting 100 to 1 using a loop.
7. Print first n Fibonacci numbers.
8. Check whether a number is prime.
9. Count digits in a given number.
10. Reverse a number using a loop.
11. Print the patterns using nested loops.

### ⭐ Square Pattern

```
* * * * *
* * * * *
* * * * *
* * * * *
* * * * *
```

### ⭐ Increasing Triangle

```
*
* *
* * *
* * * *
* * * * *
```

### ⭐ Decreasing Triangle

```
* * * * *
* * * *
* * *
* *
*
```

### ⭐ Number Triangle (Same Row Number)

```
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```

### ⭐ Number Triangle (1 to n aligning left)

```
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```
12. Find factorial of a number.
13. Count vowels in a string.
14. Find maximum digit in a number.
15. Print all prime numbers from 1–100.

---