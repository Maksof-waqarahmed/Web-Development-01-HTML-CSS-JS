# 📦 JavaScript Arrays

---

## 📌 What is an Array?

An **array** is a special variable that can store **multiple values** in a single variable.
Instead of creating separate variables, arrays help group values together.

👉 Each value in an array has a **numeric index**, starting from **0**.

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits[0]); // Apple
console.log(fruits[2]); // Cherry
```

---

## 🔹 JavaScript is Dynamically Typed

JavaScript is a **dynamically typed language**, which means:

* You don’t need to declare a specific data type (like `int`, `string`, etc. in C or Java) when creating a variable.
* The variable’s type is decided **at runtime**, based on the value assigned to it.

### Example:

```js
let x = 10;        // x is a number
x = "Hello";       // now x is a string
x = true;          // now x is a boolean
```

🔑 This means the **same variable** can hold different types of values because the type is determined dynamically.

---

## 📊 Array Methods with Examples

---

### 🔹 1) Finding the Length of an Array

✔ `length` → Returns the number of elements.
✔ Does **not** modify the original array.

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits.length); // 3
```

---

### 🔹 2) Converting an Array to String

✔ `toString()` → Converts into comma-separated string.
✔ Does **not** modify original array.

```js
let fruits = ["Apple", "Banana"];
console.log(fruits.toString()); // Apple,Banana
```

---

### 🔹 3) Accessing an Element

✔ `at(index)` → Returns element at given index.
✔ Supports **negative indexing**.
✔ Does **not** modify original array.

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits.at(1));   // Banana
console.log(fruits.at(-1));  // Cherry
```

---

### 🔹 4) Joining Elements

✔ `join(separator)` → Joins elements with custom separator.
✔ Does **not** modify array.

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits.join(" - ")); // Apple - Banana - Cherry
```

---

### 🔹 5) Adding / Removing Elements

i) `pop()` → Removes last element ✅ Modifies array.

```js
let fruits = ["Apple", "Banana"];
fruits.pop();
console.log(fruits); // ["Apple"]
```

ii) `push(value)` → Adds element at end ✅ Modifies array.

```js
let fruits = ["Apple"];
fruits.push("Mango");
console.log(fruits); // ["Apple", "Mango"]
```

iii) `shift()` → Removes first element ✅ Modifies array.

```js
let fruits = ["Apple", "Banana"];
fruits.shift();
console.log(fruits); // ["Banana"]
```

iv) `unshift(value)` → Adds element at beginning ✅ Modifies array.

```js
let fruits = ["Banana"];
fruits.unshift("Apple");
console.log(fruits); // ["Apple", "Banana"]
```

v) `delete arr[index]` → Removes element but leaves `undefined`. ⚠️ Not recommended.

```js
let fruits = ["Apple", "Banana", "Cherry"];
delete fruits[1];
console.log(fruits); // ["Apple", undefined, "Cherry"]
```

---

### 🔹 6) Merging Arrays

✔ `concat()` → Combines arrays.
✔ Returns **new array** (does not modify original).

```js
let a = [1, 2];
let b = [3, 4];
console.log(a.concat(b)); // [1,2,3,4]
```

---

### 🔹 7) Copying & Flattening

i) `copyWithin(target, start, end)` → Copies part within same array ✅ Modifies array.

```js
let nums = [1, 2, 3, 4, 5];
nums.copyWithin(1, 3);
console.log(nums); // [1,4,5,4,5]
```

ii) `flat()` → Flattens nested arrays.
✔ Returns **new array**.

```js
let arr = [1, [2, 3], [4, [5]]];
console.log(arr.flat(2)); // [1,2,3,4,5]
```

---

### 🔹 8) Splicing & Slicing

i) `splice(start, deleteCount, item1, ...)`
✔ Add/remove elements. ✅ Modifies array.

```js
let fruits = ["Apple", "Banana", "Cherry"];
fruits.splice(1, 1, "Mango");
console.log(fruits); // ["Apple","Mango","Cherry"]
```

ii) `slice(start, end)`
✔ Extracts portion.
✔ Returns **new array**.

```js
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits.slice(0, 2)); // ["Apple","Banana"]
```

---

### 🔹 9) Searching

i) `indexOf(value)` → First index.
ii) `lastIndexOf(value)` → Last index.
iii) `includes(value)` → Boolean check.
✔ None modify array.

```js
let nums = [10, 20, 30, 20];
console.log(nums.indexOf(20)); // 1
console.log(nums.lastIndexOf(20)); // 3
console.log(nums.includes(30)); // true
```

---

### 🔹 10) Sorting

i) `sort()` → Sorts array ✅ Modifies array.
⚠️ Converts to string (need compare function for numbers).

```js
let nums = [10, 1, 20];
nums.sort();
console.log(nums); // [1,10,20] (works fine as numbers)
```

ii) `reverse()` → Reverses order ✅ Modifies array.

```js
let fruits = ["Apple","Banana"];
fruits.reverse();
console.log(fruits); // ["Banana","Apple"]
```

---

## 📋 Comparison Table – Modify vs Not Modify

| Method        | Modifies Array  | Returns New Array |
| ------------- | --------------- | ----------------- |
| length        | ❌               | Value             |
| toString()    | ❌               | String            |
| at()          | ❌               | Value             |
| join()        | ❌               | String            |
| pop()         | ✅               | Removed element   |
| push()        | ✅               | New length        |
| shift()       | ✅               | Removed element   |
| unshift()     | ✅               | New length        |
| delete        | ✅ (leaves hole) | ❌                 |
| concat()      | ❌               | ✅                 |
| copyWithin()  | ✅               | ✅ (same array)    |
| flat()        | ❌               | ✅                 |
| splice()      | ✅               | ✅ (removed part)  |
| slice()       | ❌               | ✅                 |
| indexOf()     | ❌               | Value             |
| lastIndexOf() | ❌               | Value             |
| includes()    | ❌               | Boolean           |
| sort()        | ✅               | ✅ (same array)    |
| reverse()     | ✅               | ✅ (same array)    |

---

## 🎯 Challenges

1️⃣ Create an array of 5 fruits.

* Print its length.
* Convert it to string.
* Access last fruit using `at(-1)`.

2️⃣ Ask user for 3 favorite numbers and merge them into one array.

3️⃣ Remove the last element using `pop()`, then add a new fruit using `push()`.

4️⃣ Flatten a nested array like `[1,[2,[3,[4]]]]` into `[1,2,3,4]`.

5️⃣ Sort an array of numbers `[50, 5, 100, 1]` correctly.

---

## 📝 Assignment (Arrays + Previous Topics)

Solve all:

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

---