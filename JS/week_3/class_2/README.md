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

Conditional statements allow the program to **decide actions** based on conditions.

---

### 🔹 1) `if` Statement

```js
let age = 20;
if (age >= 18) {
  console.log("You are an adult.");
}
```

---

### 🔹 2) `if...else`

```js
let age = 15;
if (age >= 18) {
  console.log("You can vote.");
} else {
  console.log("You cannot vote.");
}
```

---

### 🔹 3) `if...else if...else`

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

### 🔹 4) `switch`

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

## 🎯 Challenge 2

Ask the user for a number between **1–7**, and print the **day of the week**.

```js
let day = +prompt("Enter a number (1-7):");

switch (day) {
  case 1: console.log("Monday"); break;
  case 2: console.log("Tuesday"); break;
  case 3: console.log("Wednesday"); break;
  case 4: console.log("Thursday"); break;
  case 5: console.log("Friday"); break;
  case 6: console.log("Saturday"); break;
  case 7: console.log("Sunday"); break;
  default: console.log("Invalid input");
}
```

---

# ✅ Summary

✔️ `prompt()` → Always returns string → Convert if number needed.
✔️ Relational operators compare values → Be careful with `==` vs `===`.
✔️ `null == undefined` but `null !== undefined`.
✔️ Relational operators cannot be chained directly → Use `&&`.
✔️ Conditional statements: `if`, `if-else`, `if-else if`, `switch`.

---

# 📝 Assignment Questions

Solve these to practice:

### 🔹 Prompt & Type Conversion

1. Ask the user for their **age** and check if they are **eligible to vote (18+)**.
2. Take two numbers as input and display their **product**.
3. Ask the user for their **marks** and display **Pass/Fail**.

### 🔹 Relational Operators

4. Check if a number entered is between **50 and 100** (inclusive).
5. Compare two numbers and print the **greater one**.
6. Test and explain difference between:

   ```js
   console.log("5" == 5);
   console.log("5" === 5);
   ```

### 🔹 Control Flow

7. Write a program to assign **grades** based on marks using `if-else if-else`.
8. Write a program to print the **day of the week** using `switch`.
9. Ask the user for a number. If it’s even → print `"Even"`, else `"Odd"`.

---