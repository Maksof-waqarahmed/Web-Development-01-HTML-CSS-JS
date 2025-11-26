# 📘 JavaScript Scope

---

# 🏠 Analogy: Understanding Scope

Imagine you are in a **house with multiple rooms**.

* Some things are available **everywhere** in the house → *like WiFi*.
* Some things are available only in **one specific room** → *like a bed or diary*.

👉 **Scope in JavaScript works exactly the same way.**

**Scope means: *Where a variable is accessible in JS***.

---

# 🔥 Types of Scope

### 1️⃣ Global Scope

### 2️⃣ Function Scope

### 3️⃣ Block Scope

### 4️⃣ Module Scope

Below is each type explained properly.

---

# 🌍 1. Global Scope

Variables that are declared **outside any function or block** belong to the global scope.

```js
var name = "Waqar Rana";

function greeting() {
    console.log("Hello " + name);
}

greeting();
console.log(name);
```

➡️ `name` is accessible:

* Inside function
* Inside block
* Anywhere in code

### Block Example

```js
{
    console.log("Inside block", name);
}
```

Still works because `name` is global.

---

## 🌐 Global Execution Context and window object

When a JS file runs, the **Global Execution Context (GEC)** is created.
Inside GEC two things are automatically available:

1. `window` object (in browser)
2. `this` keyword

Now see the difference between **var**, **let**, **const** in global scope:

### Example with let

```js
let name = "Waqar Rana";
console.log(window.name);
```

👉 Output: `""` (empty string)

Because `let` variables are **NOT** added to the global window object.

### Example with var

```js
var name = "Waqar Rana";
console.log(window.name);
```

👉 Output: `Waqar Rana`

### ❗ Why?

Variables declared with **var in global scope** become **properties of the window object**.
`let` and `const` do **NOT**.

---

# 🧩 2. Function Scope

Variables declared **inside a function** exist only inside that function.

### Example with var

```js
function greeting() {
    var name = "Waqar Rana";
    console.log("Hello " + name);
}

greeting();

console.log(name); // ❌ ReferenceError
```

### Same for let or const

```js
function greeting() {
    let name = "Waqar Rana";
    console.log("Hello " + name);
}

greeting();

console.log(name); // ❌ ReferenceError
```

✔ Function variables die after function finishes.

---

# 🧱 3. Block Scope

A block means `{}` — we use blocks in:

* if/else
* loops
* switch
* try/catch

`let` and `const` are **block scoped**.

```js
{
    let name = "Waqar Rana";
    console.log(name); // OK
}

console.log(name); // ❌ ReferenceError
```

### But var is NOT block-scoped

```js
{
    var name = "Waqar Rana";
    console.log(name);
}

console.log(name); // ✔ "Waqar Rana"
```

So:

* **var → function scoped**
* **let/const → block scoped**

---

# 📊 Comparison Table (var vs let vs const)

| Feature                 | var                                | let                | const                                      |
| ----------------------- | ---------------------------------- | ------------------ | ------------------------------------------ |
| Scope                   | Function scope                     | Block scope        | Block scope                                |
| Hoisting                | Hoisted (initialized as undefined) | Hoisted but in TDZ | Hoisted but in TDZ                         |
| Attached to window?     | Yes                                | No                 | No                                         |
| Re-declared?            | Yes                                | No                 | No                                         |
| Reassigned?             | Yes                                | Yes                | No                                         |
| Initial value required? | No                                 | No                 | Yes                                        |
| Mutability              | Mutable                            | Mutable            | Immutable (but object contents can change) |
| Loop Usage              | Not recommended                    | Best choice        | Not recommended                            |

---

# 🔗 Scope Chaining

When JS tries to access a variable:

1. It looks in the **current scope**
2. If not found, goes **one level up**
3. Repeats until **global scope**
4. If still not found → **ReferenceError**

### Example

```js
let globalVar = "I am a global variable";

function outer() {
    var outerVar = "I am an outer variable";

    function inner() {
        let innerVar = "I am an inner variable";
        console.log(innerVar);
        console.log(outerVar);
        console.log(globalVar);
    }

    inner();
}

outer();
```

---

# 🌓 Variable Shadowing

Shadowing happens when **inner scope has a variable with the same name** as outer scope.

The inner one **overrides** the outer one **inside that inner scope**.

### Example

```js
let message = "I am doing great";

function situation() {
    let message = "I am not doing great";
    console.log(message); // Inner
}

situation();
console.log(message); // Outer
```

---

# 🧠 Practice Tasks (GEC + FEC Thinking)

### Task 01

```js
var count = 10;

function outer(){
    var count = 20;
    function inner(){
        var count = 30;
        console.log(count);
    }
    inner();
    console.log(count);
}

outer();

console.log(count);
```

### Task 02

```js
var count = 10;

function outer(){
    var count = 20;
    function inner(){
        console.log(count);
    }
    inner();
    console.log(count);
}

outer();

console.log(count);
```

### Task 03

```js
var count = 10;

function outer(){
    function inner(){
        console.log(count);
    }
    inner();
    console.log(count);
}

outer();
console.log(count);
```

---

# 📝 Home Tasks

### 1. Output and Explanation

```js
let user = "Alice";

function outer() {
    function inner() {
        console.log(user);
    }
    let user = "Bob";
    inner();
}

outer();
```

### 2. Identify the Mistake

```js
let total = 0; // Global (bad practice)

function add(num) {
    total += num;
}

add(5);
add(10);
console.log(total);
```

### 3. Create a nested function and print parent variable.

### 4. Use a loop inside a function; try to access loop variable outside.

### 5. Try accessing a variable declared inside another function.

### 6. Output and explanation

```js
console.log(a);
let a = 10;
```

### 7. Where is `age` accessible?

```js
function showAge() {
    let age = 25;
    console.log(age);
}

console.log(age);
```

Options:
A: Global
B: Only inside showAge
C: Causes an error
D: None

### 8. Output and explanation

```js
let message = "Hello";

function outer() {
    let message = "Hi";
    function inner() {
        console.log(message);
    }
    inner();
}

outer();
```

### 9. Output and why

```js
let x = "Global";

function outer() {
    let x = "Outer";
    function inner() {
        let x = "Inner";
        console.log(x);
    }
    inner();
}

outer();
```

### 10. Output and why

```js
function counter() {
    let count = 0;
    return function () {
        count--;
        console.log(count);
    };
}

const reduce = counter();
reduce();
reduce();
```

---