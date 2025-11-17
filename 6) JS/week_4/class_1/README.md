# 🧠 Logical Operators & Nested If-Else in JavaScript

---

## 📌 1. Logical Operators

Logical operators are used to **combine two or more conditions** and return a Boolean (`true` / `false`).
They are widely used in **if-else statements** and **loops**.

---

### 🔑 Types of Logical Operators

| Operator | Meaning | Example             | Output  |
| --------- | -------- | ------------------- | -------- |
| `&&`      | AND      | `(5 > 3 && 10 > 5)` | `true`   |
| `\|\|`    | OR       | `(5 > 3 \|\| 10 < 5)` | `true`   |
| `!`       | NOT      | `!(5 > 3)`          | `false`  |

---

### 🔹 AND (`&&`)

✔ Returns `true` **only if both conditions are true**. If any condition is false, it will return false.

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

✔ Returns `true` if **at least one condition is true**. If all conditions are false, it will return false.

```js
let isWeekend = true;
let isHoliday = false;

if (isWeekend || isHoliday) {
  console.log("You can relax today!");
} else {
  console.log("Go to work.");
}
```

---

### 🔹 NOT (`!`)

✔ Reverses the truth value. If a condition is true, ! makes it false and vice versa.

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

## 📌 2. Nested if-else

A **nested if-else** means placing an `if-else` block **inside another if-else**.
It is useful for checking multiple conditions in **hierarchical order**.

---

### 📊 Examples:
```js
if(condition){
  if(condition){
    if(condition){
      // code to execute if all conditions are true
    }else{
      // code to execute if condition is false
    }
  }else{
    // code to execute if condition is false
  }
} else {
  // code to execute if condition is false
}

```

```js
const userGuess = +prompt("Guess the number between 1 to 10");
const secretNumber = 5;

if(userGuess > 0 && userGuess <= 10){
  if(userGuess === secretNumber){
    console.log("Bingo! Correct answer.");
  } else {
    console.log("Better luck next time ❌");
  }
} else {
  console.log("Invalid input. Please enter a number between 1 and 10.");
}
```

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

---

# 🏠 **Home Tasks**

1. Check if a number is between **10 and 50 (inclusive)**.
2. Ask for age:
    • If age ≥ 18 → “You are an adult.”
    • Else → “You are a minor.”
3. Ask for marks and display **grade** with messages (A+, A, B, Fail).
4. Write a program to check if a person is **eligible to vote** (age ≥ 18 and citizen = true).
5. Write a program to check if a **customer gets a discount** (isMember = true or totalBill > 100).
6. Write a program that checks **user login credentials** — print “Invalid credentials” if username or password is incorrect.
7. Write a program to determine which **age group** a person belongs to:
    • Child (< 12)
    • Teen (12–17)
    • Adult (18–59)
    • Senior (60+)
8. Write a program to check if a number is **positive, negative, or zero**.
9. Write a program to check if a given year is a **leap year**.
10. Write a program to check whether a letter is a **vowel or consonant**.
11. Write a program that takes the **temperature** as input and gives advice:
     • Below 0 → “Freezing weather.”
     • 0–20 → “Cold weather.”
     • 21–30 → “Pleasant weather.”
     • Above 30 → “Hot weather.”
12. Write a program to check the **strength of a password**:
     • Less than 8 characters → “Weak password.”
     • At least 8 characters but no number → “Moderate password.”
     • At least 8 characters and contains a number → “Strong password.”
13. Write a program for a restaurant order system:
     • If the customer orders “Pizza,” ask if they want **Veg** or **Non-Veg**.
     • If they order “Burger,” ask if they want **Cheese** or **No Cheese**.
     • If the order is invalid, display “Item not available.”
14. Write a program to calculate **car insurance premiums**:
     • If the person is below 25 → “High premium.”
     • If 25 or older but has no driving experience → “Moderate premium.”
     • If 25 or older and has driving experience → “Low premium.”
15. Write a program to suggest a **holiday destination**:
     • If it’s summer and the person prefers beaches → “Goa.”
     • If it’s winter and they like snow → “Manali.”
     • If it’s monsoon → “Kerala.”
     • Otherwise → “Stay home and relax.”

---