# 🧠 Logical Operators & Nested If-Else in JavaScript

---

## 📌 1. Logical Operators

Logical operators are used to **combine two or more conditions** and return a Boolean (`true` / `false`).
They are widely used in **if-else statements** and **loops**.

---

### 🔑 Types of Logical Operators

| Operator | Meaning | Example             | Output  |          |   |           |        |
| -------- | ------- | ------------------- | ------- | -------- | - | --------- | ------ |
| `&&`     | AND     | `(5 > 3 && 10 > 5)` | `true`  |          |   |           |        |
| \`       |         | \`                  | OR      | \`(5 > 3 |   | 10 < 5)\` | `true` |
| `!`      | NOT     | `!(5 > 3)`          | `false` |          |   |           |        |

---

### 🔹 AND (`&&`)

✔ Returns `true` **only if both conditions are true**.

```js
let age = 20;
let hasID = true;

if (age >= 18 && hasID) {
  console.log("You can enter the club.");
} else {
  console.log("Access denied.");
}
```

👉 Both conditions are true → Output: `You can enter the club.`

---

### 🔹 OR (`||`)

✔ Returns `true` if **at least one condition is true**.

```js
let isWeekend = true;
let isHoliday = false;

if (isWeekend || isHoliday) {
  console.log("You can relax today!");
} else {
  console.log("Go to work.");
}
```

👉 At least one is true → Output: `You can relax today!`

---

### 🔹 NOT (`!`)

✔ Reverses the truth value.

```js
let isRaining = false;

if (!isRaining) {
  console.log("Let's go for a walk.");
} else {
  console.log("Stay inside.");
}
```

👉 `!false → true` → Output: `Let's go for a walk.`

---

## 🎯 Challenge 1:

Ask the user for age and ID (true/false).
✔ If age ≥ 18 **AND** hasID → "You can vote"
✔ Otherwise → "Not eligible"

```js
let age = +prompt("Enter your age:");
let hasID = prompt("Do you have ID? (yes/no)") === "yes";

if (age >= 18 && hasID) {
  console.log("You can vote.");
} else {
  console.log("Not eligible.");
}
```

---

## 📌 2. Nested if-else

A **nested if-else** means placing an `if-else` block **inside another if-else**.
It is useful for checking multiple conditions in **hierarchical order**.

---

### 📊 Example: Grade Calculator

```js
let marks = 85;

if (marks >= 90) {
  console.log("Grade: A+");
} else {
  if (marks >= 75) {
    console.log("Grade: A");
  } else {
    if (marks >= 50) {
      console.log("Grade: B");
    } else {
      console.log("Fail");
    }
  }
}
```

👉 Output: `Grade: A`

---

### 🎯 Challenge 2:

Ask the user for marks:

* If `marks >= 90` → "Excellent 🎉"
* Else if `marks >= 75` → "Very Good 👍"
* Else if `marks >= 50` → "Good 🙂"
* Else → "Better luck next time ❌"

```js
let marks = +prompt("Enter your marks:");

if (marks >= 90) {
  console.log("Excellent 🎉");
} else {
  if (marks >= 75) {
    console.log("Very Good 👍");
  } else {
    if (marks >= 50) {
      console.log("Good 🙂");
    } else {
      console.log("Better luck next time ❌");
    }
  }
}
```

---

# 📚 Assignments

Solve the following:

1️⃣ **User Input & Sum**
Ask the user for two numbers and show their **sum**.

2️⃣ **Relational Operators**
Check if a number is between 10 and 50 (inclusive).

3️⃣ **Control Flow (if-else)**
Ask for age.

* If age ≥ 18 → "You are an adult"
* Else → "You are a minor"

4️⃣ **Switch Statement**
Ask the user for a number 1–7 and display the **day of the week**.

5️⃣ **Logical Operators**
Ask for age and ID.

* If age ≥ 18 **AND** hasID → "You can vote"
* Else → "Not eligible"

6️⃣ **Nested if-else**
Ask for marks and display grade with messages (A+, A, B, Fail).

---