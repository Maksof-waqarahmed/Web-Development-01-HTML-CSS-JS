# 🧩 **1. Object.groupBy() — Static Method (ES2023)**

`Object.groupBy()` is a **static** method introduced in ES2023.
It allows you to **group array items** based on a key that you return from a callback function.

### ✔ Syntax

```js
Object.groupBy(array, callbackFn)
```

* **array** → the array you want to group
* **callbackFn** → returns the "grouping key" for each element

It returns a **plain object** where **keys** are the grouping criteria, and **values** are arrays containing elements of that group.

---

## ✔ Example: Group employees by department

```js
const employees = [
    { name: "John", age: 30, salary: 4000, department: "HR" },
    { name: "Jane", age: 25, salary: 6000, department: "Marketing" },
    { name: "Bob", age: 35, salary: 5500, department: "IT" },
    { name: "Alice", age: 40, salary: 7000, department: "IT" },
];
const groupedByDepartment = Object.groupBy(employees, (employee) => employee.department);
console.log(groupedByDepartment);
```

### ✔ Output:

```js
{
  HR: [{...}],
  Marketing: [{...}],
  IT: [{...}, {...}]
}
```

---

## ✔ Example: Group by age

```js
const groupedByAge = Object.groupBy(employees, (e) => e.age);
```

---

## ✔ Example: Group by salary above/below 5000

```js
const groupedBySalary5000 = Object.groupBy(employees, (employee) => {
    return employee.salary >= 5000 ? "More than 5000" : "Less than 5000";
});
```

---

## ⭐ Additional Points About `Object.groupBy()`

### ✔ It does NOT modify the original array

It always returns a **new object**.

### ✔ The callback MUST return a string or value that becomes the group key.

### ✔ Better alternative to manual loops

Without groupBy(), you would manually write:

```js
let groups = {};
for (let item of employees) {
    let key = item.department;
    if (!groups[key]) groups[key] = [];
    groups[key].push(item);
}
```

`Object.groupBy()` makes this easy.

---

# 🧩 **2. Array-like Objects**

An **array-like object** is an object that:

✔ Has indexed values
✔ Has a `length` property
❌ Does NOT have built-in array methods (`map`, `filter`, `reduce`, etc.)

### Example:

```js
const array_like = {0: "I", 1: "am", 2: "Waqar", length: 3};
```

You can access values:

```js
console.log(array_like[0]); // "I"
```

But cannot use array functions:

```js
array_like.map(v => v); // ❌ Error
```

---

## ⭐ Where do array-like objects appear?

✔ `arguments` inside functions
✔ DOM lists like `document.querySelectorAll()`
✔ Typed arrays
✔ Custom objects formatted like arrays

---

## ⭐ Convert array-like → real array

```js
Array.from(array_like);
```

---

# 🧩 **3. The `arguments` Object**

Used in **regular functions only**.

```js
function checkArgs() {
    console.log(arguments);
}
checkArgs(2, 45);
```

Output:

```
[2, 45]
```

✔ Contains all function arguments
✔ Array-like (not a real array)
✔ Works only in **normal functions (function keyword)**
❌ NOT available in arrow functions

---

# 🧩 **4. Why `arguments` Does NOT Work In Arrow Functions**

Arrow functions **do not have**:

* `arguments`
* `this`
* `super`
* `new.target`

Arrow functions get these from the **lexical (parent) scope**.

Example:

```js
const fn = () => {
    console.log(arguments); // ❌ Error
};
```

---

# 🧩 **5. Convert Arguments → Real Array**

## ✔ Method 1: Spread Operator

```js
function checkArgs() {
    console.log([...arguments]);
}
```

⚠ Spread fails in arrow functions because they don't have arguments.

---

## ✔ Method 2: Array.from()

```js
function checkArgs() {
    console.log(Array.from(arguments));
}
```

---

## ✔ Method 3: Array.fromAsync() — ES2023

Used for promises inside arrays.

```js
const result = await Array.fromAsync([
    Promise.resolve(10),
    Promise.resolve(20),
]);
console.log(result);
```

✔ Output: `[10, 20]`

---

# 🧩 **6. Array.of()**

Creates an array from values:

```js
const arr = Array.of(1, 2, 3, "Waqar");
```

Why useful?

Because:

```js
Array(5); // creates empty array with 5 holes
Array.of(5); // creates [5]
```

So `Array.of()` avoids confusion.

---

# 🧩 **7. Increment / Decrement Operators**

Used to increase/decrease a value by 1.

---

## ✔ Pre-Increment (++x)

Increases first → returns updated value.

```js
let a = 5;
console.log(++a); // 6
console.log(a); // 6
```

---

## ✔ Post-Increment (x++)

Returns value first → then increases.

```js
let a = 5;
console.log(a++); // 5
console.log(a); // 6
```

---

## ✔ Pre-Decrement (--x)

```js
let a = 5;
console.log(--a); // 4
```

---

## ✔ Post-Decrement (x--)

```js
let a = 5;
console.log(a--); // 5
console.log(a); // 4
```

---

# 🧩 **Compound Operators**

| Operator | Meaning       |
| -------- | ------------- |
| `+=`     | x = x + value |
| `-=`     | x = x - value |
| `*=`     | x = x * value |
| `/=`     | x = x / value |

Example:

```js
let a = 10;
a += 5; // 15
a *= 2; // 30
```

---

# 🧩 **8. Loops / Looping Explained**

Loops allow repeating a block of code multiple times **without writing it again**.

Your example:

Going to the market
Buying potatoes
Coming back
Repeating…

This is a **loop in real life**.

In programming, loops automate repetition.

---

## ✔ Why loops exist?

Without loops:

```js
console.log("Buy potatoes");
console.log("Buy potatoes");
console.log("Buy potatoes");
console.log("Buy potatoes");
```

With loops:

```js
for (let i = 0; i < 4; i++) {
    console.log("Buy potatoes");
}
```

Efficient, readable, scalable.

---

# 🧩 **Types of Loops**

## 1️⃣ **for loop — Best when number of repetitions is known**

Your example:

You know you must go to the market 5 times.

### ✔ Syntax

```js
for (initialization; condition; increment/decrement) {
    // code to be executed
}
```

### ✔ Example

```js
for (let i = 1; i <= 5; i++) {
    console.log("Going to market");
}
```

---

## 2️⃣ **while loop — When you don't know how many times it will repeat**

Example:
You don’t know how many times your mom will send you to buy potatoes.

### ✔ Example

```js
let sendAgain = true;

while (sendAgain) {
    console.log("Buying potatoes");
    sendAgain = Math.random() > 0.3;  // randomly stops
}
```

---

## 3️⃣ **do…while loop — Always runs at least one time**

Your example:
You will go to the market **at least once**, even if nobody asked.

### ✔ Example

```js
let keepGoing;

do {
    console.log("Going to market");
    keepGoing = Math.random() > 0.6;
} while (keepGoing);
```

Runs minimum **one** time.

---

## 4️⃣ **for…of — Loop through arrays**

```js
const fruits = ["Apple", "Banana", "Mango"];

for (let fruit of fruits) {
    console.log(fruit);
}
```

---

## 5️⃣ **for…in — Loop through object keys**

```js
const person = {name: "Waqar", age: 25};

for (let key in person) {
    console.log(key, person[key]);
}
```

---

# 🧠 **FLOWCHARTS — Complete Professional Guide**

## 📌 **What is a Flowchart?**

A **flowchart** is a **visual diagram** that shows the **steps of a process** in order.
It uses **symbols** (shapes) to represent different operations.

A flowchart helps you understand:

* How a program works
* The order of operations
* Decisions inside a process
* Loops, repeating tasks, and conditions
* Inputs & outputs

Flowcharts are used before coding to organize thinking.

---

# 🎯 **Why are Flowcharts Important?**

✔ Makes complex logic easy
✔ Helps in problem-solving
✔ Saves time in development
✔ Helps you plan before coding
✔ Increases clarity
✔ Helps teams understand program logic
✔ Makes debugging easier
✔ Useful in teaching and documenting projects

---

# 🏗 **Where are Flowcharts Used?**

✔ Programming
✔ Algorithms
✔ Business processes
✔ System design
✔ Project planning
✔ Education
✔ UX / Workflow designing
✔ Automation tasks

---

# 🟦 **Flowchart Symbols (All Important Symbols Explained)**

Below are the **standard flowchart symbols** used worldwide.

---

## 🔶 **1. Terminator (Start/End)**

**Shape:** Oval / Rounded rectangle
**Purpose:** Shows **Start** or **End** of the flowchart

```
🔹 Start
🔹 End
```

---

## ⬜ **2. Process / Action**

**Shape:** Rectangle
**Purpose:** Used for **calculations, actions, steps**

Example steps:

* Add a number
* Print result
* Update variable

```
[ Add two numbers ]
```

---

## 🔷 **3. Decision / Condition**

**Shape:** Diamond
**Purpose:** Used when program needs to **choose between true/false**, **yes/no**, or **multiple choices**

Examples:

* Is age ≥ 18?
* Is password correct?

```
     [Age >= 18?]
        /    \
     Yes      No
```

---

## 🟪 **4. Input / Output (I/O)**

**Shape:** Parallelogram
**Purpose:** Shows **input** or **output**

Examples:

* Input age
* Display result

```
/ Input number /
\ Output result \
```

---

## 🟩 **5. Flow Lines / Arrows**

**Purpose:** Show **direction** of the flow.

```
Start → Step 1 → Step 2 → End
```

---

## ⬛ **6. Connector / Off-page Connector**

**Shape:** Small circle or pentagon
**Purpose:** Used when flowchart is long and needs continuation.

Useful for large diagrams.

---

## 🟧 **7. Predefined Process / Function Call**

**Shape:** Rectangle with double borders
**Purpose:** Used for **functions**, **sub-processes**, or **modules**.

Example:

```
[ calculateSalary() ]
```

---

## 🟨 **8. Document / Display**

**Shape:** Wavy bottom rectangle
**Purpose:** Shows printed output or document.

---

## 🟥 **9. Manual Input**

Shows data entered manually (e.g., typing in a form).

---

# 🧩 **Flowchart Rules (Must Follow for Professional Diagrams)**

✔ Flowcharts must start with **Start** and end with **End**
✔ Arrows must show clear direction
✔ Only **one arrow** should enter a process
✔ Decision must have **two outputs** (Yes / No)
✔ Keep flow from **top to bottom (best practice)**
✔ Use consistent shapes
✔ Avoid crossing arrows
✔ Label decision outputs clearly

---

# 📝 **How to Make a Flowchart (Step-by-Step Guide)**

### ✅ Step 1: Understand the problem

What are the steps? What needs to be done?

### ✅ Step 2: Identify inputs & outputs

* What comes IN?
* What goes OUT?

### ✅ Step 3: Break the process into smaller steps

Each step = one rectangle (process).

### ✅ Step 4: Identify decisions

Where do you need Yes/No or True/False?

### ✅ Step 5: Arrange steps in logical order

Top → bottom
Left → right

### ✅ Step 6: Add arrows to show flow direction

### ✅ Step 7: Use proper symbols

### ✅ Step 8: Review the diagram

Does it match the logic?
Is anything missing?

---

# 🧠 **Flowchart Example: Check if Number is Even or Odd**

### Steps:

1. Start
2. Input number
3. Check number % 2 == 0
4. Print “Even” or “Odd”
5. End

### Flowchart:

```
     ⭕ Start
        |
   ⟪ Input number ⟫
        |
   ◼ Is number % 2 == 0?
       /       \
    Yes         No
    |           |
[ Print Even ] [ Print Odd ]
        \       /
            ⭕ End
```

---

# 🧠 **Flowchart Example: Login System**

```
⭕ Start
  |
⟪ Input username & password ⟫
  |
◼ Is username correct?
 /        \
No        Yes
 |         |
[ Show Error ] 
               |
            ◼ Is password correct?
             /        \
           No         Yes
            |           |
     [ Show Error ]   [ Login Successful ]
                      |
                    ⭕ End
```

---

# 🧠 **Flowchart Example: Simple Loop (For Loop)**

```
⭕ Start
  |
⟪ Input n ⟫
  |
[ i = 1 ]
  |
◼ Is i <= n ?
   /     \
 No       Yes
 |          |
 ⭕ End     [ Print i ]
                |
           [ i = i + 1 ]
                |
                ↑ (back to condition)
```

---

# 🧩 **Professional Tips for Clean Flowcharts**

✔ Use Microsoft Visio, Draw.io, Figma, Canva, Lucidchart <br>
✔ Maintain spacing <br>
✔ Keep all arrows straight <br>
✔ Use consistent colors <br>
✔ Keep diagram left-aligned or center-aligned <br>
✔ Avoid long sentences in shapes <br>
✔ Keep diamond decisions short (1 line if possible)

---

# 🧩 **Common Mistakes to Avoid**

❌ Too many lines crossing <br>
❌ No Start or End <br>
❌ Using wrong shapes <br>
❌ Writing code instead of simple steps <br>
❌ Arrows pointing in random directions <br>
❌ Large paragraphs inside shapes <br>
❌ Too many symbols — keep it simple

---

# 🧩 **Advantages of Flowcharts**

✔ Easy to understand <br>
✔ Best for beginners <br>
✔ Helps in debugging <br>
✔ Helps in algorithm planning <br>
✔ Improves documentation quality <br>
✔ Easier to explain logic to students or teammates <br>

---

# 🧩 **Disadvantages of Flowcharts**

❌ Hard to edit if logic changes <br>
❌ Large programs create huge diagrams <br>
❌ Not suitable for very complex algorithms <br>

---