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