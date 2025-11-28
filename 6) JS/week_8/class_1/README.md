# 📘 `this` in JavaScript

**Analogy (quick):**
`this` is like a friend who changes seats in every room. Depending on where the friend sits (where the function is called), `this` points to different things: sometimes a specific object, sometimes the global object, sometimes `undefined`.

---

## What is `this`?

`this` is a special keyword in JavaScript that gives you the **value (context)** of the current execution — i.e. *what object (if any) the current code is working on*. The exact value of `this` depends on **how** a function is called, not where it's defined.

Main rule: **To know `this`, look at the call-site (how a function is invoked).**

---

## The main “binding” rules (order matters)

1. **`new` binding:** When a function is called with `new`, `this` is the newly created object.
2. **Explicit binding:** If `call`, `apply`, or `bind` are used, they explicitly set `this`.
3. **Implicit binding (method call):** If a function is called as a property of an object (`obj.fn()`), `this` is that object.
4. **Default (global) binding:** If none of the above apply, in non-strict mode `this` → `window` (browser) / global object; in strict mode `this` → `undefined`.
5. **Arrow functions:** Arrow functions do **not** have their own `this`. They lexically inherit `this` from the surrounding scope (the value `this` had when the arrow function was defined).

---

## `this` at global level

In a browser (non-strict):

```js
console.log(this === window); // true
console.log(this); // window object
```

In strict mode:

```js
"use strict";
console.log(this); // still global at top-level: window in browsers (but inside functions different)
```

Note: `let` / `const` declared globals do NOT become properties of `window`. `var` globals do.

---

## Implicit binding — object method

When you call a method with dot notation, `this` is the object before the dot.

```js
const employee = {
  id: "Ec035",
  firstName: "John",
  lastName: "Doe",
  age: 30,
  returnThis: function() { return this; },
  getFullName: function() { return this.firstName + " " + this.lastName; }
};

console.log(employee.returnThis()); // employee object
console.log(employee.getFullName()); // "John Doe"
```

If you pass the method off (detach it), implicit binding is lost:

```js
const retFunc = employee.returnThis;
retFunc(); // in non-strict -> window (or undefined in strict)
```

---

## Function calls (default binding)

A plain function call (not as a method) uses default binding:

```js
function sayName() { console.log(this); }
sayName(); // non-strict -> window, strict -> undefined
```

Nested functions behave the same: their `this` is determined by how the inner function is called — usually default binding (window/undefined), unless explicitly bound.

---

## Strict mode effect

In `"use strict"` plain function calls produce `undefined`:

```js
"use strict";
function say() { console.log(this); }
say(); // undefined
```

This prevents accidental dependency on the global object.

---

## Arrow functions — lexical `this`

Arrow functions do **not** create their own `this`. They inherit `this` from the enclosing (lexical) scope.

Bad for methods (if you want object `this`):

```js
const food = {
  name: "Biryani",
  type: "Chicken",
  getDesc: () => `${this.name} is a ${this.type}`
};

console.log(food.getDesc()); // wrong, this is not food
```

Correct approach:

```js
const food = {
  name: "Biryani",
  type: "Chicken",
  getDesc: function() {
    return () => `${this.name} is a ${this.type}`; // arrow here inherits this from getDesc's this (which is food)
  }
}
const descFunc = food.getDesc();
console.log(descFunc()); // "Biryani is a Chicken"
```

Use arrow functions for callbacks inside methods to preserve the outer `this`.

---

## Explicit binding: `call`, `apply`, `bind`

**`call(thisArg, arg1, arg2, ...)`** – calls the function with `thisArg` and arguments individually.

**`apply(thisArg, [args])`** – like `call` but arguments passed as array.

**`bind(thisArg, args...)`** – returns a *new function* permanently bound to `thisArg` (and optionally preset arguments).

Examples:

```js
function greeting() {
  console.log(`Hello ${this.name} from ${this.address}`);
}
const user = { name: "Waqar", address: "123 Main St" };
greeting.call(user); // Hello Waqar from 123 Main St

const likes = function(h1, h2) {
  console.log(`${this.name} likes ${h1} and ${h2}`);
};
likes.call(user, "Coding", "Teaching");
likes.apply(user, ["Coding", "Teaching"]);
const f = likes.bind(user, "Coding", "Teaching");
f();
```

`bind` is frequently used to ensure a method retains `this` when passed as a callback.

---

## `new` binding (constructor)

When a function is called with `new`, JS creates a new object and binds `this` to it.

```js
function Cartoon(name, animal) {
  this.name = name;
  this.animal = animal;
  this.log = function() { console.log(`${this.name} is a ${this.animal}`); };
}

const tom = new Cartoon("Tom", "Cat");
tom.log(); // Tom is a Cat
```

---

## Common interview / tricky examples and fixes

### Problem: inner function loses `this`

```js
const user = {
  name: "Waqar",
  age: 25,
  greet: function() {
    function innerGreet() {
      console.log(`Hello ${this.name}`);
    }
    innerGreet();
  }
};
user.greet(); // Hello undefined (default binding)
```

Fixes:

1. Arrow function for inner:

```js
greet: function() {
  const innerGreet = () => console.log(`Hello ${this.name}`);
  innerGreet();
}
```

2. `bind`:

```js
greet: function() {
  function innerGreet() { console.log(`Hello ${this.name}`); }
  innerGreet.bind(this)();
}
```

3. Capture `this` in a variable:

```js
greet: function() {
  const self = this;
  function innerGreet() { console.log(`Hello ${self.name}`); }
  innerGreet();
}
```

All three ensure the inner function uses the object as `this`.

---

## Detaching methods (loss of implicit binding)

```js
const obj = { name: "Waqar", greet() { console.log(this.name); } };
obj.greet();     // "Waqar"
const f = obj.greet;
f();             // undefined or window.name
f.call(obj);     // "Waqar"
```

If you want to pass `f` around and keep `this`, use `bind`:

```js
const bound = obj.greet.bind(obj);
bound(); // "Waqar"
```

---

## Arrow function methods — gotchas

Arrow functions do not have `this`. If you write:

```js
const person = {
  name: "Alice",
  say: () => console.log(this.name)
};
person.say(); // not "Alice"
```

Because arrow's `this` is inherited from the outer scope (here likely window/global), not the object.

---

## Visual (short) diagram — implicit & explicit

```
obj.method()   ---> implicit binding: this = obj

func()         ---> default binding: this = global/window (non-strict) or undefined (strict)

func.call(x)   ---> explicit binding: this = x

new Func()     ---> new binding: this = newly created object

() => { }      ---> arrow    : this = lexical (parent) this
```

---

# 🏠 Home Task

### **Task 1 — Table of `this`**

Create a table with **two columns**: **Situation** and **Value of `this`**. Fill in rows for **all scenarios below** and give **examples for each**:

1. At the Global Scope
2. Inside an Object Method (implicit binding)
3. Inside a Standalone Non-Arrow Function
4. Inside a Standalone Arrow Function
5. Inside an Arrow Function used as an Object Method
6. Inside an Object created with a Constructor Function

---

### **Task 2 — Arrow function problem**

```js
const user = {
  name: "tapaScript",
  greet: () => {
    console.log(`Hello, ${this.name}!`);
  },
};
user.greet();
```

**Question:**
Explain the problem why the correct name is not logged.

---

### **Task 3 — Detached method problem**

```js
const obj = {
  name: "Tom",
  greet: function () {
    console.log(`Hello, ${this.name}!`);
  },
};
const greetFn = obj.greet;
greetFn();
```

**Question:**
Why does this not log the correct name? How can you fix it?

---

### **Task 4 — Nested function problem**

```js
const user = {
  name: "Alex",
  greet: function () {
    function inner() {
      console.log(`Hello, ${this.name}!`);
    }
    inner();
  },
};
user.greet();
```

**Question:**
Explain why `this` does not refer to the object and how you would fix it.

---

### **Task 5 — Constructor function**

Create a **`Sports` constructor function** that takes `name` and `number of players` as arguments.
Then:

1. Create two sports instances.
2. Log their details using `this`.

---

### **Task 6 — Method borrowing**

```js
const car1 = {
  brand: "Audi",
  model: "A8",
  describe: function () {
    console.log(`This car is a ${this.brand} ${this.model}.`);
  },
};

const car2 = {
  brand: "BMW",
  model: "X1",
};
```

**Question:**
Attach `car1`’s `describe` method to `car2` in **all possible ways** so that it correctly logs `car2`’s details.

---

### **Task 7 — Output prediction**

```js
const person = {
  name: "Charlie",
  sayHello: function () {
    console.log(this.name);
  },
  sayHelloArrow: () => {
    console.log(this.name);
  },
};

person.sayHello();
person.sayHelloArrow();
```

**Question:**
Predict the output and explain why it happens.

---