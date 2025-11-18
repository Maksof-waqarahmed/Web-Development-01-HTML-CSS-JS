# 📦 JavaScript Arrays

---

## 🧠 **What is an Array?**

An **array** is a special variable that can store **multiple values** in a single variable.
Instead of creating multiple variables, arrays help group values together.

📌 In JavaScript:

* Arrays are **ordered collections**.
* Each value in an array is called an **element**.
* Each element has an **index** (position) starting from **0**.
* Arrays are **dynamic** — we can add or remove elements anytime.

---


## 🧩 **Array Syntax**

```js
let fruits = [element1, element2, element3, ...];
```

### ▶️ Key Terms:

| Term           | Meaning                                                                           |
| -------------- | --------------------------------------------------------------------------------- |
| `[]`           | Square brackets define an array                                                   |
| **Element**    | A value inside the array (can be string, number, boolean, object, function, etc.) |
| **Index**      | Position of the element (starts from `0`)                                         |
| **Last index** | `array.length - 1`                                                                |
| **Length**     | Number of elements in the array                                                   |

---

## 🏗️ **Ways to Create Arrays**

### 1️⃣ Array Literal (✅ Recommended)

```js
let fruits = ["Apple", "Banana", "Cherry"];
```

### 2️⃣ Array Constructor

```js
let fruits = new Array("Apple", "Banana", "Cherry");
```
📌 Both are valid, but **array literals** are simpler and faster.

---

## ⚠️ **Special Case — Single Number Argument**

```js
let fruits = new Array(2);
console.log(fruits); // [ <2 empty items> ]
```

If you pass **a single number**, JavaScript treats it as **array length**, not as an element.

### 🧩 Example:

```js
let arr = new Array(2);
console.log(arr.length); // 2
console.log(arr[0]); // undefined
console.log(arr); // [ <2 empty items> ]
```

> "empty ×2" means 2 empty slots (no values assigned yet).

But:

```js
let arr = new Array("Waqar");
console.log(arr); // ["Waqar"]
```

✅ Here it's **not a number**, so it becomes a normal array.

---

## ⚙️ **Difference Between the Two**

```js
["Apple", "Banana", "Cherry"] == new Array("Apple", "Banana", "Cherry"); // ❌ false
```

🔹 Both look same, but they’re stored at **different memory locations** (reference types).
So they’re **not equal**.

---

## 🧾 **Accessing Array Elements**

Syntax:

```js
arrayName[index];
```

Example:

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits[0]); // Apple
console.log(fruits[2]); // Cherry
```

---

## ✏️ **Updating Array Elements**

```js
let fruits = ["Apple", "Banana", "Cherry"];
fruits[1] = "Mango";
console.log(fruits); // ["Apple", "Mango", "Cherry"]
```

---

## ⚠️ **Negative Index Example**

```js
let fruits = ["Apple", "Banana", "Cherry"];
fruits[-1] = "Mango";
console.log(fruits); // ["Apple", "Banana", "Cherry", -1: "Mango"]
```

📌 Negative index does **not** change array elements —
It adds a **custom property** named `-1` on the array object.

---

## ➕ **Adding New Elements**

```js
let fruits = ["Apple", "Banana", "Cherry"];
fruits[3] = "Mango";
console.log(fruits); // ["Apple", "Banana", "Cherry", "Mango"]
```

---

## 🔎 **Check if Variable is an Array**

```js
let fruits = ["Apple", "Banana", "Cherry"];
let num = 12;
let obj = { name: "John" };

console.log(Array.isArray(fruits)); // true
console.log(Array.isArray(num));    // false
console.log(Array.isArray(obj));    // false
```

---

## ✂️ **Destructuring Arrays**

Extract values from array into variables.

### 🧩 Old way

```js
let fruits = ["Apple", "Banana", "Cherry"];
const apple = fruits[0];
const banana = fruits[1];
const cherry = fruits[2];
console.log(apple); // Apple
console.log(banana); // Banana
console.log(cherry); // Cherry
```

### ⚡ New way (shortcut)

```js
let fruits = ["Apple", "Banana", "Cherry"];
let [apple, banana, cherry] = fruits;
console.log(apple); // Apple
console.log(banana); // Banana
console.log(cherry); // Cherry
```

## 📦 Use cases 

### 🎁 Default Values: You can assign default values to variables

```js
let fruits = ["Apple"];
let [apple, banana = "Banana"] = fruits;
console.log(apple); // Apple
console.log(banana); // Banana
```

### ⏭️ Skip Elements: You can skip elements by using comma

```js
let fruits = ["Apple", "Banana", "Cherry"];
let [apple, , cherry] = fruits;
console.log(apple); // Apple
console.log(cherry); // Cherry
```

### ⚙️ Undefined Assignment: If array length is less than variables length then undefined will be assigned to remaining variables

```js
let fruits = ["Apple"];
let [apple, banana] = fruits;
console.log(apple); // Apple
console.log(banana); // undefined
```

### 🔄 Position Order

```js 
let fruits = ["Apple", "Banana", "Cherry"];
let [apple, cherry] = fruits;
console.log(apple); // Apple
console.log(cherry); // Cherry
```

### 🧺 Nested Array: Array inside array

```js
let fruits = ["Apple", ["Banana", "Cherry"]];
console.log(fruits[0]); // Apple
console.log(fruits[1]); // ["Banana", "Cherry"]
console.log(fruits[1][0]); // Banana
console.log(fruits[1][1]); // Cherry
```

### 🧠 Example with destructuring

```js
let fruits = ["Apple", ["Banana", "Cherry"]];
let [apple, [banana, cherry]] = fruits;
console.log(apple); // Apple
console.log(banana); // Banana
console.log(cherry); // Cherry
```

### 🌀 Complex Example

```js
let fruits = ["Apple", "Mango", "Orange", ["Banana", "Cherry"]];
let [,,,[, cherry]] = fruits;
console.log(cherry); // Cherry
```

---

## 🌈 **Rest and Spread Operators**

* `...` on **left** → Rest Operator
* `...` on **right** → Spread Operator

### 🧺 **Rest Operator (`...`)**

Collects remaining elements.

```js
let fruits = ["Apple", "Mango", "Orange", ["Banana", "Cherry"]];
let [apple, ...rest] = fruits;
console.log(apple); // Apple
console.log(rest); // ["Mango", "Orange", ["Banana", "Cherry"]]
```

### 🚀 **Spread Operator (`...`)**

Expands elements.

```js
let fruits = ["Apple", "Mango", "Orange", "Banana", "Cherry"];
let fruitsCopy = [...fruits];
console.log(fruitsCopy); // ["Apple", "Mango", "Orange", "Banana", "Cherry"]
```

---

### 🔄 **Swapping Values**

```js
let a = 10;
let b = 20;
[a, b] = [b, a];
console.log(a); // 20
console.log(b); // 10
```

---

### 🔗 **Merging Two Arrays**

```js
let fruits1 = ["Apple", "Mango", "Orange"];
let fruits2 = ["Banana", "Cherry"];
let allFruits = [...fruits1, ...fruits2];
console.log(allFruits);
// ["Apple", "Mango", "Orange", "Banana", "Cherry"]
```

---

## 📏 **Array Length**

Maximum array size = `2 ** 32 - 1 = 4294967295`

```js
let nums = [1,2,3,4,5,6,7,8,9,10];
console.log(nums.length); // 10

nums.length = 5;
console.log(nums); // [1,2,3,4,5]

nums.length = 10;
console.log(nums); // [1,2,3,4,5, empty × 5]
```

Setting array length **shortens or extends** the array dynamically.

---

## 🔁 **Mutability vs Immutability in JavaScript Arrays**

Before understanding array methods, it’s crucial to know which methods **modify** the original array and which ones **return a new array** (without changing the original).

---

## ⚙️ **1️⃣ Mutability (Mutable Methods)**

> **Definition:**
> A **mutable method** is one that **changes (mutates)** the original array directly in memory.
> After using such methods, the **original array content is permanently modified**.

### 📘 Example:

```js
let fruits = ["Apple", "Banana"];
fruits.push("Cherry"); // Modifies the original array
console.log(fruits); // ["Apple", "Banana", "Cherry"]
```

👉 `push()` ne directly `fruits` array me change kiya — isiliye ye **mutable** method hai.

---

### 🧩 **Common Mutable Methods**

| Method         | Description                          | Returns          |
| -------------- | ------------------------------------ | ---------------- |
| `push()`       | Add element at end                   | New length       |
| `pop()`        | Remove last element                  | Removed element  |
| `shift()`      | Remove first element                 | Removed element  |
| `unshift()`    | Add element at beginning             | New length       |
| `splice()`     | Add/remove elements                  | Removed elements |
| `sort()`       | Sort elements                        | Sorted array     |
| `reverse()`    | Reverse order                        | Reversed array   |
| `copyWithin()` | Copy elements within array           | Modified array   |
| `fill()`       | Replace elements with a static value | Modified array   |

---

### ⚠️ **Example — Mutation Proof**

```js
let arr = [1, 2, 3];
let result = arr.reverse(); 

console.log(arr);    // [3, 2, 1] ✅ original array changed
console.log(result); // [3, 2, 1] (same reference)
console.log(arr === result); // true (both are same array)
```

> 🧠 Note: Both `arr` and `result` point to **same memory reference**.

---

## 🚫 **2️⃣ Immutability (Immutable Methods)**

> **Definition:**
> An **immutable method** does **not change** the original array.
> Instead, it **returns a new array or value**, leaving the original unchanged.

---

### 📘 Example:

```js
let fruits = ["Apple", "Banana"];
let newFruits = fruits.concat(["Cherry"]);

console.log(fruits);     // ["Apple", "Banana"] ✅ unchanged
console.log(newFruits);  // ["Apple", "Banana", "Cherry"]
```

👉 `concat()` ne ek **new array** return kiya, original array ko nahi badla.

---

### 🧩 **Common Immutable Methods**

| Method                        | Description                  | Returns       |
| ----------------------------- | ---------------------------- | ------------- |
| `slice()`                     | Copies portion of array      | New array     |
| `concat()`                    | Combines arrays              | New array     |
| `map()`                       | Transform each element       | New array     |
| `filter()`                    | Filter elements              | New array     |
| `reduce()`                    | Reduce array to single value | New value     |
| `flat()`                      | Flatten nested arrays        | New array     |
| `join()`                      | Converts to string           | String        |
| `toString()`                  | Converts to string           | String        |
| `includes()`                  | Checks existence             | Boolean       |
| `indexOf()` / `lastIndexOf()` | Finds index                  | Number        |
| `find()` / `findIndex()`      | Finds item                   | Value / Index |
| `every()` / `some()`          | Test conditions              | Boolean       |

---

### 🧠 **Example — Immutable Method**

```js
let arr = [1, 2, 3];
let copy = arr.slice(0, 2);

console.log(arr);  // [1, 2, 3] ✅ original unchanged
console.log(copy); // [1, 2] (new array)
console.log(arr === copy); // false (different memory)
```

---

## 🔬 **3️⃣ Why Mutability & Immutability Matter**

### ✅ Mutability:

* Fast for in-place updates (no new memory allocation)
* Best when you **don’t need the old version**
* Used in performance-heavy apps (like games, live counters)

### 🚫 Immutability:

* Prevents **accidental modification**
* Easier **debugging** & **state management** (especially in React, Redux)
* Enables **functional programming** (pure functions)

---

### 🧠 Quick Tip

> 🔹 If method **returns nothing or same array**, it’s **mutable**.
> 🔹 If method **returns a new array/value**, it’s **immutable**.

---

### ⚖️ **Summary Table**

| Category             | Mutable Methods                        | Immutable Methods                   |
| -------------------- | -------------------------------------- | ----------------------------------- |
| **Modify Original**  | ✅ Yes                                  | ❌ No                                |
| **Memory Reference** | Same                                   | New                                 |
| **Examples**         | push, pop, splice, sort, reverse       | slice, concat, map, filter, flat    |
| **Use Case**         | When you want to update existing array | When you want a copy or pure result |

---

### 🧩 Example Comparison

```js
// Mutable Example
let nums = [1, 2, 3];
nums.push(4);
console.log(nums); // [1,2,3,4]

// Immutable Example
let nums2 = [1, 2, 3];
let newNums = nums2.concat(4);
console.log(nums2); // [1,2,3]
console.log(newNums); // [1,2,3,4]
```

---

### 💡 Final Note:

> ✅ **Mutable methods** change the array in place.
> ✅ **Immutable methods** return a new one.
> ⚠️ Always know which one you are using — especially when working with React, Redux, or functional JS — because mutating state can cause **unexpected bugs**.

---

## 📚 JavaScript Array Methods

---

## 🧮 1) `length` — Get Number of Elements

✔ Returns total number of elements in array.
✔ **Does not modify** the original array.

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits.length); // 3
```

💡 You can also **manually change** length:

```js
fruits.length = 2;
console.log(fruits); // ["Apple", "Banana"]
```

---

## ➕ 2) Add / Remove Elements

### 🧩 `push(value)` → Add at the **end**

✅ **Modifies** array
✅ Returns **new length**

```js
let fruits = ["Apple"];
const newLength = fruits.push("Mango");
console.log(fruits); // ["Apple", "Mango"]
console.log(newLength); // 2
```

---

### 🧩 `pop()` → Remove **last element**

✅ **Modifies** array
✅ Returns **removed element**

```js
let fruits = ["Apple", "Banana"];
const removed = fruits.pop();
console.log(fruits); // ["Apple"]
console.log(removed); // "Banana"
```

---

### 🧩 `unshift(value)` → Add at the **beginning**

✅ **Modifies** array
✅ Returns **new length**

```js
let fruits = ["Banana"];
const newLength = fruits.unshift("Apple");
console.log(fruits); // ["Apple", "Banana"]
console.log(newLength); // 2
```

---

### 🧩 `shift()` → Remove **first element**

✅ **Modifies** array
✅ Returns **removed element**

```js
let fruits = ["Apple", "Banana"];
const removed = fruits.shift();
console.log(fruits); // ["Banana"]
console.log(removed); // "Apple"
```

---

### ⚠️ `delete arr[index]`

🚫 **Not recommended**
Deletes value but keeps the **slot empty** (i.e. `undefined`).

```js
let fruits = ["Apple", "Banana", "Cherry"];
delete fruits[1];
console.log(fruits); // ["Apple", undefined, "Cherry"]
```

---

## ✂️ 3) Adding / Removing at Custom Positions

### 🧩 `splice(start, deleteCount, item1, item2, ...)`

✔ **Modifies** array
✔ Returns **removed elements array**

---

**1️⃣ Replace elements**

```js
let fruits = ["Apple", "Banana", "Cherry"];
const removed = fruits.splice(1, 1, "Mango");
console.log(fruits); // ["Apple","Mango","Cherry"]
console.log(removed); // ["Banana"]
```

**2️⃣ Insert without deleting**

```js
let fruits = ["Apple", "Banana", "Cherry"];
const removed = fruits.splice(1, 0, "Mango");
console.log(fruits); // ["Apple","Mango","Banana","Cherry"]
console.log(removed); // []
```

**3️⃣ Remove multiple**

```js
let fruits = ["Apple", "Banana", "Cherry"];
const removed = fruits.splice(1, 2);
console.log(fruits); // ["Apple"]
console.log(removed); // ["Banana","Cherry"]
```

💡 `splice()` is **very powerful** — it can **add, remove, or replace** any number of items.

---

## 🧾 4) Copying & Extracting

### 🧩 `slice(start, end)`

✔ **Returns a new array**
❌ **Does not modify** the original

```js
let fruits = ["Apple", "Banana", "Cherry"];
const copy = fruits.slice(0, 2);
console.log(copy); // ["Apple","Banana"]
console.log(fruits); // ["Apple","Banana","Cherry"]
```

💡 If no parameters → full copy

```js
let clone = fruits.slice();
```

---

### 🧩 `concat()`

✔ Joins multiple arrays
✔ **Returns a new array** (immutable)

```js
let a = [1, 2];
let b = [3, 4];
console.log(a.concat(b)); // [1,2,3,4]
```

💡 Combine many arrays:

```js
let all = a.concat(b, [5, 6], [7]);
```

---

## 🔁 5) Copying Within Same Array

### 🧩 `copyWithin(target, start, end)`

✅ **Modifies** the array
Copies part of array and pastes it somewhere else.

```js
let nums = [1, 2, 3, 4, 5, 6, 7];
nums.copyWithin(0, 3, 6);
console.log(nums); // [4,5,6,4,5,6,7]
```

🧠 Parameters:

| Parameter | Meaning                         |
| --------- | ------------------------------- |
| `target`  | index to start copying **to**   |
| `start`   | index to start copying **from** |
| `end`     | stop before this index          |

If no `end` → goes till array end.

---

## 🧩 6) Flattening Nested Arrays

### `flat(depth)`

✔ **Returns a new array**
✔ Flattens nested arrays
✔ Default depth = 1

```js
let arr = [1, [2, 3], [4, [5]]];
console.log(arr.flat()); // [1,2,3,4,[5]]
console.log(arr.flat(2)); // [1,2,3,4,5]
console.log(arr.flat(Infinity)); // [1,2,3,4,5]
```

---

## 🔤 7) Converting Array to String

### 🧩 `toString()`

✔ Returns comma-separated string
✔ Does not modify array

```js
let fruits = ["Apple", "Banana"];
console.log(fruits.toString()); // "Apple,Banana"
```

---

### 🧩 `join(separator)`

✔ Joins elements with custom separator
✔ Returns string
✔ Does not modify array

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits.join(" - ")); // Apple - Banana - Cherry
console.log(fruits.join()); // Apple,Banana,Cherry
console.log(fruits.join("")); // AppleBananaCherry
```

---

## 🧱 8) Filling Arrays

### 🧩 `fill(value, start?, end?)`

✅ **Modifies** array
✔ Replaces all or part with a static value

```js
let fruits = ["Apple", "Banana", "Cherry"];
fruits.fill("Mango");
console.log(fruits); // ["Mango","Mango","Mango"]

fruits.fill("Orange", 1, 2);
console.log(fruits); // ["Mango","Orange","Mango"]
```

💡 If only `start` → fills from start to end.

---

## 🔍 9) Searching in Array

### 🧩 `indexOf(value, fromIndex?)`

✔ Finds **first occurrence**
✔ Returns index or -1
❌ Does not modify array

```js
let fruits = ["Apple", "Banana", "Cherry", "Apple"];
console.log(fruits.indexOf("Apple")); // 0
```

---

### 🧩 `lastIndexOf(value, fromIndex?)`

✔ Finds **last occurrence**
✔ Returns index or -1

```js
let fruits = ["Apple", "Banana", "Cherry", "Apple"];
console.log(fruits.lastIndexOf("Apple")); // 3
```

---

### 🧩 `includes(value, fromIndex?)`

✔ Returns boolean
✔ Checks if element exists
❌ Does not modify array

```js
const months = ["Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"];
console.log(months.includes("Mar")); // true
console.log(months.includes("Mar", 4)); // false
console.log(months.includes("Mar", -4)); // false
console.log(months.includes("Mar", -12)); // true
```

💡 Negative index formula:

```js
finalIndex = array.length + negativeIndex;
```

If result < 0 → starts from 0.

---

## 🧩 10) `at(index)`

✔ Supports **negative indexes**
✔ Does not modify array

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits.at(-1)); // Cherry
console.log(fruits.at(1)); // Banana
```

---

## 🔡 11) Sorting & Reversing

### 🧩 `sort()`

✅ **Modifies** array
✔ Sorts elements alphabetically (by default converts to strings)

```js
let nums = [10, 1, 20];
console.log(nums.sort()); // [1,10,20]
```

⚠️ But check this:

```js
let arr = [10, 1, 20, 1000, 4000, 3];
console.log(arr.sort()); 
// ["1","10","1000","20","3","4000"] (string sort)
```

🧠 For **numeric sort**, pass comparator:

```js
let nums = [10, 1, 20];
nums.sort((a, b) => a - b);
console.log(nums); // [1,10,20]
```

💬 **Comparator Rules:**

| Return | Meaning          |
| ------ | ---------------- |
| `< 0`  | a comes first    |
| `> 0`  | b comes first    |
| `0`    | order stays same |

---

### 🧠 Custom Logic Sort

```js
let names = ["John", "Alice", "Bob"];
names.sort((a, b) => (a === b ? 0 : a > b ? 1 : -1));
console.log(names); // ["Alice","Bob","John"]
```

---

### 🌍 Using `localeCompare()`

Used for **alphabetical / language-based comparison**

```js
let names = ["John", "Alice", "Bob"];
names.sort((a, b) => a.localeCompare(b)); // Ascending (A → Z)
console.log(names); // ["Alice","Bob","John"]

names.sort((a, b) => b.localeCompare(a)); // Descending (Z → A)
console.log(names); // ["John","Bob","Alice"]
```

---

### 🔁 `reverse()`

✅ **Modifies** array
✔ Reverses order

```js
let fruits = ["Apple","Banana"];
console.log(fruits.reverse()); // ["Banana","Apple"]
```

---

## 💎 Summary Table

| Method          | Modifies Array? | Returns         | Description                |
| --------------- | --------------- | --------------- | -------------------------- |
| `push()`        | ✅ Yes           | New length      | Add to end                 |
| `pop()`         | ✅ Yes           | Removed element | Remove from end            |
| `shift()`       | ✅ Yes           | Removed element | Remove from start          |
| `unshift()`     | ✅ Yes           | New length      | Add to start               |
| `splice()`      | ✅ Yes           | Removed items   | Add/Remove at any position |
| `slice()`       | ❌ No            | New array       | Copy/extract part          |
| `concat()`      | ❌ No            | New array       | Combine arrays             |
| `copyWithin()`  | ✅ Yes           | Same array      | Copy within itself         |
| `flat()`        | ❌ No            | New array       | Flatten nested             |
| `fill()`        | ✅ Yes           | Same array      | Replace values             |
| `sort()`        | ✅ Yes           | Same array      | Sort elements              |
| `reverse()`     | ✅ Yes           | Same array      | Reverse order              |
| `indexOf()`     | ❌ No            | Index / -1      | Find first occurrence      |
| `lastIndexOf()` | ❌ No            | Index / -1      | Find last occurrence       |
| `includes()`    | ❌ No            | Boolean         | Check existence            |
| `join()`        | ❌ No            | String          | Join elements              |
| `toString()`    | ❌ No            | String          | Convert to comma string    |
| `at()`          | ❌ No            | Element         | Access by index            |

---

## ⚙️ New Immutable Array Methods (ES2023+)

### 1️⃣ **toReversed()**

👉 Works like `.reverse()` but **does not mutate the original array**.
It returns a **new reversed copy** instead.

```js
const fruits = ["Apple", "Banana", "Cherry"];
const reversedFruits = fruits.toReversed();

console.log(reversedFruits); // ["Cherry", "Banana", "Apple"]
console.log(fruits);         // ["Apple", "Banana", "Cherry"]
```

```js
const nums = [1, 2, 3];
const reversedNums = nums.toReversed();

console.log(reversedNums); // [3, 2, 1]
console.log(nums);         // [1, 2, 3]
```

---

### 2️⃣ **toSorted()**

👉 Works like `.sort()` but **immutable**.
It **returns a new sorted array** without affecting the original one.

```js
const fruits = ["Apple", "Cherry", "Mango", "Banana"];
const sortedFruits = fruits.toSorted();

console.log(sortedFruits); // ["Apple", "Banana", "Cherry", "Mango"]
console.log(fruits);       // ["Apple", "Cherry", "Mango", "Banana"]
```

```js
const nums = [3, 5, 7, 9, 3];
const sortedNums = nums.toSorted();

console.log(sortedNums); // [3, 3, 5, 7, 9]
console.log(nums);       // [3, 5, 7, 9, 3]
```

---

### 3️⃣ **toSpliced(start, deleteCount, ...items)**

👉 Works like `.splice()` but **does not mutate the original array**.
It **returns a new array** with the applied changes.

```js
const fruits = ["Apple", "Cherry", "Mango", "Banana"];
const splicedFruits = fruits.toSpliced(1, 1, "Grape");

console.log(splicedFruits); // ["Apple", "Grape", "Mango", "Banana"]
console.log(fruits);        // ["Apple", "Cherry", "Mango", "Banana"]
```

```js
const nums = [1, 2, 3];
const splicedNums = nums.toSpliced(1, 1, 4);

console.log(splicedNums); // [1, 4, 3]
console.log(nums);        // [1, 2, 3]
```

---

### 4️⃣ **with(index, value)**

👉 Creates a **copy of the array** with the element at the given index replaced.
The **original array remains unchanged**.
It also supports **negative indexing** (e.g., `-1` refers to the last element).

**Syntax:**
`array.with(index, value)`

**Explanation:**

* `index`: position of the element to replace (can be negative)
* `value`: new value to insert at that position

**Examples:**

```js
const fruits = ["Apple", "Cherry", "Mango", "Banana"];
const withFruits = fruits.with(1, "Grape");

console.log(withFruits); // ["Apple", "Grape", "Mango", "Banana"]
console.log(fruits);     // ["Apple", "Cherry", "Mango", "Banana"]
```

```js
const nums = [1, 2, 3, 4, 5];
const withNums = nums.with(1, 4);

console.log(withNums); // [1, 4, 3, 4, 5]
console.log(nums);     // [1, 2, 3, 4, 5]
```

```js
const fruits = ["Apple", "Cherry", "Mango", "Banana"];
const withFruits = fruits.with(-1, "Grape");

console.log(withFruits); // ["Apple", "Cherry", "Mango", "Grape"]
console.log(fruits);     // ["Apple", "Cherry", "Mango", "Banana"]
```

---

## 🧾 Summary Table

| Method         | Mutable | Returns New Array | Description                |
| -------------- | ------- | ----------------- | -------------------------- |
| `reverse()`    | ✅ Yes   | ❌ No              | Reverses same array        |
| `toReversed()` | ❌ No    | ✅ Yes             | Returns reversed copy      |
| `sort()`       | ✅ Yes   | ❌ No              | Sorts same array           |
| `toSorted()`   | ❌ No    | ✅ Yes             | Returns sorted copy        |
| `splice()`     | ✅ Yes   | ❌ No              | Adds/removes in same array |
| `toSpliced()`  | ❌ No    | ✅ Yes             | Returns modified copy      |
| `with()`       | ❌ No    | ✅ Yes             | Replaces element immutably |

---



Home Task:

## 🎯 Challenges

1️⃣ Create an array of 5 fruits.

* Print its length.
* Convert it to string.
* Access last fruit using `at(-1)`.

2️⃣ Ask user for 3 favorite numbers and merge them into one array.

3️⃣ Remove the last element using `pop()`, then add a new fruit using `push()`.

4️⃣ Flatten a nested array like `[1,[2,[3,[4]]]]` into `[1,2,3,4]`.

5️⃣ Sort an array of numbers `[50, 5, 100, 1]` correctly.


1. Take user input for two numbers and print their **sum**.
2. Check if a number is between **10 and 50**.
3. Ask for age → print "Adult" or "Minor".
4. Switch case for day of the week (1–7).
5. Age + ID check using `&&`.
6. Grade calculator (Nested if-else).
7. Create an array of your friends’ names and:

   * Add a new friend at the beginning.
   * Remove the last friend.
   * Join all names with `-`.
8. Merge two arrays of numbers and sort them.
9. Flatten `[1,[2,3],[4,[5]]]` into `[1,2,3,4,5]`.
10. Search for a number inside an array using `includes()`.

1) Find the Total Elements in an Array
1)Write a program that converts an array into a string using .toString() and .join()
2)Use .pop() to remove the last element from an array and console the updated array.
3)Use .push() to add a new element at the end of an array.
4)Use .shift() to remove the first element from an array.
5)Use .unshift() to add a new element at the start of an array.
6)Use .concat() to merge two arrays into one.
7)Use .slice() to return a portion of an array without modifying the original.
8)Remove two elements starting from index 1 and insert new values using .splice().
9)Use .find() to get the first number greater than 20.
10)Sort an array using .sort(). let arr = [3, 1, 4, 2]; (Ascending and Descending).
11)Convert a string into an array, reverse it, and join it back into a string.
12)Use .flat() to convert a nested array into a single-level array.
---





















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

