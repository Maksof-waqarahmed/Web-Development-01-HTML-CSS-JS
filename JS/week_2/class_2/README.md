# 📝 JavaScript Strings & Methods

---

## 🔹 1. Length Property

The `.length` property returns the **number of characters** in a string, including spaces.

```javascript
let message = "Hello World!";
console.log(message.length); // Output: 12
```

---

## 🔹 2. Accessing Characters in a String

### i. `charAt(index)`

Returns the character at the specified index (0-based).

```javascript
let str = "JavaScript";
console.log(str.charAt(0)); // Output: "J"
console.log(str.charAt(4)); // Output: "S"
```

### ii. `at(index)`

Works like `charAt()` but supports **negative indexing**.

```javascript
console.log(str.at(0));  // "J"
console.log(str.at(-1)); // "t" (last character)
```

### iii. Bracket Notation: `string[index]`

Access characters like an array.

```javascript
console.log(str[1]);  // "a"
console.log(str[5]);  // "c"
```

---

## 🔹 3. Extracting a Substring

### i. `slice(start, end)`

Extracts part of a string and returns a **new string**. Supports **negative indexes**.

```javascript
let text = "Hello JavaScript";
console.log(text.slice(6, 16));   // "JavaScript"
console.log(text.slice(-10, -1)); // "JavaScrip"
```

### ii. `substring(start, end)`

Similar to `slice()` but **does not support negative indexes**.

```javascript
console.log(text.substring(6, 16)); // "JavaScript"
```

### iii. `substr(start, length)` (Deprecated)

Extracts part of a string based on **starting index** and **length**.

```javascript
console.log(text.substr(6, 10)); // "JavaScript"
```

---

## 🔹 4. Changing Case

### i. `toUpperCase()`

```javascript
console.log("hello".toUpperCase()); // "HELLO"
```

### ii. `toLowerCase()`

```javascript
console.log("HELLO".toLowerCase()); // "hello"
```

---

## 🔹 5. Combining & Modifying Strings

### i. `concat()`

Joins two or more strings.

```javascript
let first = "Hello";
let second = "World";
console.log(first.concat(" ", second)); // "Hello World"
```

### ii. `trim()`

Removes whitespace from both ends.

```javascript
let messy = "   Hello   ";
console.log(messy.trim()); // "Hello"
```

### iii. `trimStart()` / `trimEnd()`

```javascript
console.log(messy.trimStart()); // "Hello   "
console.log(messy.trimEnd());   // "   Hello"
```

---

## 🔹 6. Replacing Content

### i. `replace(searchValue, newValue)`

Replaces **first occurrence**.

```javascript
let sentence = "I love JavaScript";
console.log(sentence.replace("JavaScript", "JS")); // "I love JS"
```

### ii. `replaceAll(searchValue, newValue)`

Replaces **all occurrences**.

```javascript
let repeat = "JS is fun. JS is popular.";
console.log(repeat.replaceAll("JS", "JavaScript")); 
// "JavaScript is fun. JavaScript is popular."
```

---

## 🔹 7. Splitting Strings

### i. `split(separator)`

Splits string into an array.

```javascript
let fruits = "apple,banana,orange";
console.log(fruits.split(",")); 
// ["apple", "banana", "orange"]
```

---

## 🔹 8. Finding & Searching

### i. `indexOf(substring)`

```javascript
let phrase = "I love JavaScript";
console.log(phrase.indexOf("love")); // 2
```

### ii. `lastIndexOf(substring)`

```javascript
let text2 = "JS JS JS";
console.log(text2.lastIndexOf("JS")); // 6
```

---

## 🔹 9. Matching & Checking

### i. `includes(substring)`

```javascript
console.log(phrase.includes("Java")); // true
```

### ii. `startsWith(substring)`

```javascript
console.log(phrase.startsWith("I love")); // true
```

### iii. `endsWith(substring)`

```javascript
console.log(phrase.endsWith("JavaScript")); // true
```

---

## 🏆 Challenge Time!

Try these exercises to practice:

1. Find the **length** of `"Hello World!"`.
2. Get the **first and last characters** of `"JavaScript"`.
3. Extract `"Script"` from `"JavaScript"` using `slice` and `substring`.
4. Convert `"javascript"` to uppercase.
5. Combine `"Hello"` and `"World"` using both `concat()` and `+`.
6. Remove extra spaces from `"   JS Rocks!   "`.
7. Replace `"JS"` with `"JavaScript"` in `"I love JS"`.
8. Split `"a,b,c,d,e"` into an array.
9. Check if `"I love JS"` **includes** `"love"`.
10. Check if `"Hello"` **startsWith** `"He"` and **endsWith** `"lo"`.

---

# 🏠 **Home Task – JavaScript Strings Practice**

---

## 🔹 **Task 1: Custom Greeting Generator**

Create a program that:

1. Takes a user’s first name and last name in two variables.
2. Combines them using **`concat()`** or **template literals**.
3. Converts the final message to **uppercase**.
4. Displays it using `console.log()`.

🧩 **Example Output:**

```
HELLO, JOHN DOE! WELCOME TO JAVASCRIPT.
```

---

## 🔹 **Task 2: Word Counter**

Write a JS program that counts how many words are in the sentence:

`"JavaScript is an amazing programming language"`

🧩 **Output:**

```
Total Words: 5
```

---

## 🔹 **Task 3: Extract Domain from Email**

Given:

```js
let email = "student@example.com";
```

Write code to extract only the domain name (`example.com`) using string methods (`slice`, `indexOf`).

🧩 **Output:**

```
Domain: example.com
```

---

## 🔹 **Task 4: Mask a Secret Word**

You have:

```js
let secret = "password123";
```

Replace all characters except the first and last with `*`.

🧩 **Output:**

```
p********3
```

💡 **Hint:** Combine `slice()`, `replace()`, and `.length`.

---

## 🔹 **Task 5: Sentence Formatter**

Given:

```js
let sentence = "   javascript is FUN!   ";
```

Perform the following:

1. Remove extra spaces.
2. Capitalize first letter only (Output: `"Javascript is fun!"`).
3. Log the clean sentence.

💡 **Hint:** Use `trim()`, `toLowerCase()`, `charAt()`, and string concatenation.

---

## ⭐ **Bonus Challenge (Creative Task)**

Make a program called **"Text Analyzer"**:

1. Take a sentence.
2. Show:

   * Total characters (`length`)
   * Total words
   * Whether it contains `"JavaScript"`
   * Same text in uppercase

🧩 **Example Output:**

```
Sentence: I love JavaScript
Characters: 17
Words: 3
Contains "JavaScript": true
Uppercase: I LOVE JAVASCRIPT
```

---

## 🏠 **Home Task – JavaScript Strings Practice (Set 2)**

---

## 🔹 **Task 1: Initials Generator**

Create a program that takes a **full name** like `"John Doe"` and prints only the **initials**.

🧩 **Example Output:**

```
Initials: J.D
```

---

## 🔹 **Task 2: Hide Email Address**

Given:

```js
let email = "username@example.com";
```

Display only the first 3 letters of the username, followed by `***` and the domain.

🧩 **Example Output:**

```
Email: use***@example.com
```

---

## 🔹 **Task 3: Reverse a String**

Take a string like `"JavaScript"` and print it in reverse order.

🧩 **Example Output:**

```
tpircSavaJ
```

---

## 🔹 **Task 4: Replace Word and Format**

You have this sentence:

```
"I am learning js at my own pace"
```

Convert `"js"` to `"JavaScript"` and capitalize the first letter of the sentence.

🧩 **Example Output:**

```
I am learning JavaScript at my own pace
```

---
