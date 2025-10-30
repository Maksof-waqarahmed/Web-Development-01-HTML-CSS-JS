# 📝 JavaScript: User Input, Relational Operators & Control Flow

---

## 📌 1. User Input with `prompt()`

The **`prompt()` function** shows a dialog box where the user can enter input.

👉 **Syntax:**

```js
prompt(text, defaultText);
```

* `text`: The message displayed.
* `defaultText`: (Optional) Default value.
* Returns: The **input as a string**, or `null` if the user cancels.

---

### 📊 Example

```js
let name = prompt("What is your name?", "Guest");
console.log("Hello, " + name);
```

👉 If the user clicks **Cancel**, result = `null`.

---

### ⚡ Input Always Comes as a String

Even if the user types a number, it is stored as a **string**.
You must convert it to a **number** if required.

#### 1️⃣ Using Unary `+`

```js
let age = +prompt("Enter your age:");
console.log(typeof age, age); // number
```

#### 2️⃣ Using `Number()`

```js
let marks = Number(prompt("Enter your marks:"));
console.log(typeof marks, marks); // number
```

👉 If input is not numeric (e.g., `"hello"`) → result = `NaN`.

---

## 🎯 Challenge 1

Write a program that asks the user for two numbers and shows their **sum**.

```js
let num1 = +prompt("Enter first number:");
let num2 = +prompt("Enter second number:");
console.log("Sum = " + (num1 + num2));
```

---

## 📌 2. Relational (Comparison) Operators

Relational operators compare values and return a **Boolean (`true`/`false`)**.

---

### 🔑 Operators

| Operator | Meaning          | Example     | Output  |
| -------- | ---------------- | ----------- | ------- |
| `>`      | Greater than     | `5 > 3`     | `true`  |
| `<`      | Less than        | `5 < 3`     | `false` |
| `>=`     | Greater or equal | `5 >= 5`    | `true`  |
| `<=`     | Less or equal    | `3 <= 5`    | `true`  |
| `==`     | Loose equality   | `"5" == 5`  | `true`  |
| `===`    | Strict equality  | `"5" === 5` | `false` |
| `!=`     | Loose not equal  | `"5" != 5`  | `false` |
| `!==`    | Strict not equal | `"5" !== 5` | `true`  |

---

### 📊 Examples

```js
console.log(10 > 5);          // true
console.log("5" == 5);        // true (loose equality)
console.log("5" === 5);       // false (strict equality)
console.log(null == undefined); // true (special case)
console.log(null === undefined); // false
```

---

### ⚠️ Special Cases

1. **`null` & `undefined`**

```js
console.log(null < 1);     // true  (null → 0)
console.log(null == 0);    // false (special case)
console.log(undefined < 1);// false (undefined → NaN)
```

2. **Chaining Relational Operators ❌**

```js
console.log(5 < 10 < 20);  
// true → because (5 < 10) → true → (true < 20) → 1 < 20 → true
```

✅ Correct way:

```js
let x = 7;
console.log(x > 5 && x < 10); // true
```

---

## 📌 3. Control Flow Statements

A conditional statement in programming is a feature that allows you to perform different actions based on whether a certain condition (or expression) evaluates to true or false. It enables decision-making in your code.

---

### 🔹 Types of Conditional Statements:

1) `if` Statement: Executes a block of code if the condition is true.

```js
if (condition) {
  // code to execute if condition is true
}
```

```js
let age = 20;
if (age >= 18) {
  console.log("You are an adult.");
}
```

---

2) `if...else` Statement: Executes one block of code if the condition is true, and another block if the condition is false.

```js
if (condition) {
  // code to execute if condition is true
} else {
  // code to execute if condition is false
}
```

```js
let age = 15;
if (age >= 18) {
  console.log("You can vote.");
} else {
  console.log("You cannot vote.");
}
```

---

3) `if...else if...else` Statement: Allows you to check multiple conditions in sequence.

```js
if (condition) {
  // code to execute if condition is true
} else if (condition) {
  // code to execute if condition is false
} else {
  // code to execute if condition is false
}
```

```js
let marks = 72;

if (marks >= 90) {
  console.log("Grade: A+");
} else if (marks >= 75) {
  console.log("Grade: A");
} else if (marks >= 50) {
  console.log("Grade: B");
} else {
  console.log("Fail");
}
```

---

Note: if you have one statement to execute, you can write it in one line or without the curly braces.

one line: 
```js
if (condition) statement;
```

```js
let age = 20;
if (age >= 18) console.log("You are an adult.");
```

without the curly braces:
```js
if (condition)
  statement;
```

```js
let age = 20;
if (age >= 18)
  console.log("You are an adult.");
```

---

4) `switch` Statement: Used to comparision to multiple values only used for comparison.

```js
switch (expression) {
  case value1:
    // code to execute if expression === value1
    break;
  case value2:
    // code to execute if expression === value2
    break;
  default:
    // code to execute if expression doesn't match any case
}
```

```js
let day = 3;

switch (day) {
  case 1: 
    console.log("Monday"); 
    break;
  case 2: 
    console.log("Tuesday"); 
    break;
  case 3: 
    console.log("Wednesday"); 
    break;
  default: 
    console.log("Invalid day");
}
```

```js
let day = 3;

switch (day) {
  case 1: console.log("Monday"); break;
  case 2: console.log("Tuesday"); break;
  case 3: console.log("Wednesday"); break;
  default: console.log("Invalid day");
}
```

---

# 🏠 **Home Tasks**

1. Write a program that takes marks of three subjects from the user, stores them in variables, and prints them.
2. Write a program that takes the price of soap and shampoo from the user, calculates the total price, and prints it.
3. Write a program that takes the radius of a circle as input, calculates its area, and prints it.
4. Write a program that takes two numbers from the user and prints their sum, difference, multiplication, division, and remainder.
5. Write a program that checks if a number is positive, negative, or zero.
6. Write a program that takes a student’s marks and prints “A” for marks ≥ 90, “B” for marks ≥ 80 and < 90, “C” for marks ≥ 70 and < 80, and “Fail” for marks < 70.
7. Write a program that checks if a number is even or odd.
8. Write a program that checks if a person is eligible to drive (age ≥ 18).
9. Use a switch statement to print the day of the week based on user input (1 for Monday, 7 for Sunday).
10. Write a program that checks if a year is a leap year.
11. Write a program to simulate a traffic light system. Input can be "red", "yellow", or "green" and output should be "Stop", "Ready", or "Go".
12. Write a program that uses a switch statement to check if a number is odd or even.
13. Write a program that takes two numbers and an operator (+, -, *, /) as input and performs the corresponding operation using a switch statement.
14. Write a program to take gender as input. If male, print “Good Morning Sir”; if female, print “Good Morning Ma’am.”
15. Write a program to take input of remaining fuel in a car (in liters). If fuel < 0.25 liters, print “Please refill the fuel in your car.”
16. Write a program that takes temperature as input and shows a message based on these conditions:
     a) T > 40 → “It is too hot outside.”
     b) T > 30 → “The weather today is normal.”
     c) T > 20 → “Today’s weather is cool.”
     d) T > 10 → “OMG! Today’s weather is so cool.”
17. Store a secret number (1–10). Ask user to guess. If correct → “Bingo! Correct answer.” If guessed +1 → “Close enough to the correct answer.”