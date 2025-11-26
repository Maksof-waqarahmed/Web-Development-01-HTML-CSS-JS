# 📘 **JavaScript Objects**

## ✅ **What Is an Object?**

In JavaScript, an **object** is a data structure that stores information in the form of **key–value pairs**.

* A **key** (also called a *property name*) is always a string.
* A **value** can be **any data type**, including another object or a function.

Example:

```js
let user = {
    name: "John",
    age: 30
};
```

---

## ✅ **What Is a Property?**

A **property** is a key–value pair inside an object.

Example:

* `name` → **property name (key)**
* `"John"` → **property value**

```js
let user = {
    name: "John",
    age: 30
};
```

If a property contains a function, it is called a **method**.

---

## ✅ **Ways to Create Objects**

### **1. Object Literal (Most Common)**

```js
let user = {
    name: "John",
    age: 30
};
```

---

## ✅ **Accessing Properties**

### **Dot notation**

```js
console.log(user.name); // John
```

### **Bracket notation (for spaces or dynamic keys)**

```js
console.log(user["age"]); // 30
```

---

## ✅ **Adding and Modifying Properties**

### Add new property

```js
user.city = "New York";
```

### Modify existing property

```js
user.age = 31;
```

---

## ✅ **Deleting Properties**

```js
delete user.city;
console.log(user.city); // undefined
```

---

## ✅ **Dynamic Property Access**

```js
let key = "name";
console.log(user[key]); // John
```

### Dynamic property creation

```js
const car = prompt("Enter your favorite car");
const favCar = { [car]: 5 };
console.log(favCar);
```

---

## ✅ **Constructor Function**

A constructor function acts as a **blueprint** for creating multiple object instances.

> Constructor names start with a capital letter.

```js
function Car(name, model){
    this.name = name;
    this.model = model;
}

const honda = new Car("Honda", 2016);
console.log(honda);
```

### Checking instance

```js
console.log(honda instanceof Car); // true
```

---

## ✅ **Built-in Object Constructor**

```js
const obj = new Object();
obj.name = "Waqar";
```

---

## ✅ **Factory Function**

A function that **returns an object** instead of using `new`.

```js
function createUser(name, age){
    return { name, age };
}

const user1 = createUser("Waqar", 23);
```

---

## ✅ **Methods (Functions Inside Objects)**

```js
let user = {
    name: "John",
    greet(){
        console.log(this.name);
    }
};

user.greet();
```

A function inside an object = **method** ✅

---

## ✅ **Nested Objects**

```js
let user = {
    name: "John",
    address: {
        city: "Karachi",
        country: "Pakistan"
    }
};

console.log(user.address.city);
```

---

## ✅ **Checking If a Property Exists**

Incorrect (fails when value is `undefined`):

```js
if(!user.salary){}
```

Correct:

```js
console.log("salary" in user);
```

### Using static method

```js
user.hasOwnProperty("name"); // true
Object.hasOwn(user, "name"); // true
```

---

## ✅ **Looping Through Objects**

### Keys

```js
for (let key in user){
    console.log(key);
}
```

### Values

```js
for (let key in user){
    console.log(user[key]);
}
```

---

## ✅ **Object Reference Behavior**

Objects are compared by **reference**, not value.

```js
const a = {name: "mango"};
const b = {name: "mango"};

console.log(a === b); // false
```

---

## ✅ **Why `const` Objects Can Change**

`const` prevents reassignment, **not modification**.

```js
const fruit = {name: "mango"};
fruit.color = "yellow"; // allowed
```

---

## ✅ **Useful Static Methods**

### `Object.keys()`

Returns array of keys.

```js
Object.keys(user);
```

### `Object.values()`

Returns array of values.

```js
Object.values(user);
```

### `Object.entries()`

```js
Object.entries(user);
// [ ['name', 'John'], ['age', 30] ]
```

### `Object.fromEntries()`

Converts key-value pairs back into an object.

```js
Object.fromEntries(Object.entries(user));
```

---

## ✅ **Shallow Copy vs Deep Copy (Important!)**

### ✅ **Shallow Copy**

Copies **only top-level properties**, but nested objects share the **same reference**.

Methods that create shallow copies:

* `Object.assign()`
* Spread operator `{ ...obj }`

Example:

```js
const source = {address: {city: "Karachi"}};
const copy = Object.assign({}, source);

copy.address.city = "Lahore";

console.log(source.address.city); // Lahore ❗
```

✔ Same reference → changes reflect in both

---

### ✅ **Deep Copy**

Creates a **completely independent copy**, including nested objects.

Best method:

```js
const clone = structuredClone(source);

clone.address.city = "Lahore";

console.log(source.address.city); // Karachi ✅
```

✔ Different reference
✔ Safe for nested objects

---

## ✅ **Object.freeze()**

Prevents **adding, removing, or modifying** properties.

```js
const emp = { sal: 100 };
Object.freeze(emp);

emp.sal = 200;
console.log(emp.sal); // 100
```

Check:

```js
Object.isFrozen(emp); // true
```

---

## ✅ **Object.seal()**

Allows modifying existing properties but prevents adding/removing.

```js
const dept = { name: "IT" };
Object.seal(dept);

dept.name = "HR"; // allowed
dept.location = "Karachi"; // ignored
```

Check:

```js
Object.isSealed(dept);
```

---

## ✅ **Object.preventExtensions()**

Prevents adding new properties.

```js
Object.preventExtensions(user);
user.salary = 5000; // ignored
```

Check:

```js
Object.isExtensible(user); // false
```

---

## ✅ **Object.is()**

Handles strict comparisons for special cases.

```js
Object.is(NaN, NaN); // true
```

---

## ✅ **Object Destructuring**

Extract values into variables.

```js
const {name, age, address: {city}, meal = "bread"} = student;
```

### Aliasing

```js
const {std: standard} = student;
```

---

## ✅ **Destructuring in Functions**

```js
function sendEmail({parents: {email}}){
    console.log(`Sending email to ${email}`);
}
```

---

## ✅ **Destructuring in Loops**

```js
for (let {name, grade} of students){
    console.log(name, grade);
}
```

---

## ✅ **Optional Chaining (`?.`)**

Prevents runtime errors.

```js
console.log(employee?.department?.name); // undefined ✅
```

---

# 📘 **Home Task**

### ✍️ **Task 1**

What will be the output and why?

```js
const user = { name: "Alex", age: undefined };
console.log(user.age ?? "Not provided");
```

---

### ✍️ **Task 2**

What happens when we try to modify a frozen object?

```js
const obj = Object.freeze({ a: 1 });
obj.a = 2;
console.log(obj.a);
```

Explain the behavior.

---

### ✍️ **Task 3**

Using **destructuring**, extract:

* `name`
* `company`
* `address.city`

from the object below:

```js
const person = {
  name: "Tapas",
  company: {
    name: "tapaScript",
    location: {
      city: "Bangalore",
      zip: "94107"
    }
  }
};
```

---

### ✍️ **Task 4 – Mini Project**

Create a **Student Management System** using an object:

Requirements:

* Store: `name`, `age`, `grades` (array)
* Add a method to calculate **average grade**
* Print student details + average

---

### ✍️ **Task 5 – Mini Project**

Create a **Book Store Inventory System**:

Requirements:

* Store book names and quantity in an object
* Add method to check availability
* Add method to **restock** books
* Test your functions with output

---

### ✍️ **Task 6**

Explain the difference between:

* `Object.keys()`
* `Object.entries()`

Include code examples and output.

---

### ✍️ **Task 7**

Write **three different ways** to check if an object has a specific property.

Example object:

```js
const obj = { city: "Karachi" };
```

---

### ✍️ **Task 8**

Predict the output and explain why:

```js
const person = { name: "John" };
const newPerson = person;
newPerson.name = "Doe";
console.log(person.name);
```

---

### ✍️ **Task 9**

What is the **best way to deeply copy** a nested object?

✅ Explain at least **two methods** with examples.

---

### ✍️ **Task 10**

Using **destructuring**, loop through the array and print values:

```js
const users = [
  { name: "Alex", address: "15th Park Avenue", age: 43 },
  { name: "Bob", address: "Canada", age: 53 },
  { name: "Carl", address: "Bangalore", age: 26 }
];
```

Expected output format:

```
Alex - 15th Park Avenue - 43
```

---

### ⭐ **Bonus (Optional)**

* Create a function that freezes an object and prevents further modifications
* Explain how **TDZ** affects `let` & `const` with an example