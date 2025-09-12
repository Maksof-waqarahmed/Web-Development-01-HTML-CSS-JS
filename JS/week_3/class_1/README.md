# ⚡ Operators and Operands in JavaScript

## 📌 What are Operators and Operands?

* **Operators** → Symbols or keywords that perform an operation.
* **Operands** → The values or variables on which the operator acts.

👉 Example:

```js
let a = 10, b = 5;
let result = a + b;  // Here, + is the operator, and a & b are operands.
```

---

## 🛠️ Types of Operators in JavaScript

1. **Arithmetic Operators**
2. **Relational (Comparison) Operators**
3. **Logical Operators**
4. **Compound Assignment Operators**
5. **Increment/Decrement Operators**
6. **Bitwise Operators (Extra)**

---

## 1️⃣ Arithmetic Operators

These are used for basic mathematical operations:

| Operator | Description         | Example  | Output |
| -------- | ------------------- | -------- | ------ |
| `+`      | Addition            | `5 + 3`  | `8`    |
| `-`      | Subtraction         | `5 - 3`  | `2`    |
| `*`      | Multiplication      | `5 * 3`  | `15`   |
| `/`      | Division            | `10 / 2` | `5`    |
| `%`      | Modulus (Remainder) | `10 % 3` | `1`    |
| `**`     | Exponentiation      | `2 ** 3` | `8`    |

📌 Example:

```js
console.log(10 + 5);   // 15
console.log(10 - 5);   // 5
console.log(10 * 2);   // 20
console.log(10 / 2);   // 5
console.log(10 % 3);   // 1
console.log(2 ** 4);   // 16
```

---

# 🎯 Order of Precedence in JavaScript

When multiple operators are used in an expression, **JavaScript follows precedence rules**.

---

### 📌 Order of Execution

1. **Parentheses `()`** → Highest priority.
2. **Exponentiation `**`** → Right to left.
3. **Multiplication `*`, Division `/`, Modulus `%`** → Left to right.
4. **Addition `+`, Subtraction `-`** → Left to right.
5. **Comparison `>, <, >=, <=`**
6. **Equality `==, ===, !=, !==`**
7. **Logical AND `&&`**
8. **Logical OR `||`**
9. **Assignment `=, +=, -=` etc.** → Lowest priority.

---

### 📊 Example

```js
let result = 10 + 5 * 2;   // Multiplication happens first
console.log(result);       // 20

let result2 = (10 + 5) * 2; // Parentheses first
console.log(result2);       // 30

let result3 = 2 ** 3 ** 2;  // Right to left: 2 ** (3 ** 2)
console.log(result3);       // 512
```

---

# ✅ Key Notes

* Always use **parentheses `()`** to make expressions **clear and readable**.
* Without parentheses, JavaScript strictly follows **operator precedence**.
* Precedence helps avoid unexpected results in complex calculations.

---

# 📝 Challenges: Operators

1. Predict the output:

   ```js
   console.log(10 + 5 * 2);
   console.log((10 + 5) * 2);
   console.log(2 ** 3 ** 2);
   ```

2. Write a program that calculates the **area of a rectangle** using variables `length` and `width`.

3. Write a program to find the **remainder** when `37` is divided by `6`.

4. Use compound operators (`+=`, `-=`, `*=`) to update a variable `x` starting from `10`.

5. Swap two numbers using arithmetic operators only (without using a third variable).

---

# 🔄 Implicit Type Conversion (Type Coercion) in JavaScript

## 📌 What is Implicit Type Conversion?

* **Implicit type conversion** (also called **type coercion**) happens when JavaScript **automatically converts one data type into another** while evaluating an expression.
* It ensures that operations involving **different data types** can still be executed.
* JavaScript follows certain **rules** for type conversion.

---

## 1️⃣ String Conversion

When the **`+` operator** is used with a **string**, other operands are automatically converted to **strings**.

📌 Example:

```js
console.log("5" + 2);     // "52"  (number → string)
console.log("Hello" + true);  // "Hellotrue"
console.log("Value: " + null); // "Value: null"
```

👉 Rule:

* If **one operand is a string** → The whole expression becomes a **string**.

---

## 2️⃣ Number Conversion

When using **arithmetic operators** (`-`, `*`, `/`, `%`, `**`) with a **string containing numeric values**, JavaScript tries to convert the string into a **number**.

📌 Example:

```js
console.log("10" - 5);  // 5  ("10" → number)
console.log("6" * "2"); // 12 ("6" & "2" → numbers)
console.log("20" / "5"); // 4
console.log("5" - "abc"); // NaN ("abc" cannot convert to number)
```

👉 Rule:

* Works **only when the string is numeric**.
* Non-numeric strings → `NaN`.

---

## 3️⃣ Boolean Conversion

JavaScript converts **boolean values** into **numbers** in arithmetic operations:

* `true → 1`
* `false → 0`

📌 Example:

```js
console.log(true + 1);   // 2  (true → 1)
console.log(false + 10); // 10 (false → 0)
console.log(true * 5);   // 5
```

### ✅ Truthy vs Falsy Values

JavaScript automatically converts values into `true` or `false` in conditions:

* **Falsy values** → `0, "", null, undefined, NaN, false`
* **Truthy values** → Everything else

📌 Example:

```js
if ("") console.log("This won't run");
if ("Hello") console.log("This will run");  // Truthy
```

---

## 4️⃣ Null and Undefined

JavaScript treats `null` and `undefined` differently in numeric contexts.

📌 Example:

```js
console.log(null + 5);      // 5  (null → 0)
console.log(undefined + 5); // NaN (undefined → NaN)
```

👉 Rule:

* `null` → converted to **0**
* `undefined` → converted to **NaN**

---

## 5️⃣ Unary `+` Operator

The **unary plus (`+`)** explicitly tries to **convert its operand into a number**.

📌 Example:

```js
console.log(+"100");   // 100 (string → number)
console.log(+"true");  // NaN  ("true" is not numeric)
console.log(+true);    // 1
console.log(+false);   // 0
console.log(+null);    // 0
console.log(+undefined); // NaN
```

---

# 🎯 Summary Table

| Expression      | Result | Explanation                     |
| --------------- | ------ | ------------------------------- |
| `"5" + 2`       | `"52"` | Number converted to string      |
| `"10" - 5`      | `5`    | String converted to number      |
| `true + 1`      | `2`    | Boolean true → 1                |
| `false + 10`    | `10`   | Boolean false → 0               |
| `null + 5`      | `5`    | null → 0                        |
| `undefined + 5` | `NaN`  | undefined → NaN                 |
| `+"100"`        | `100`  | Unary plus converts to number   |
| `+"abc"`        | `NaN`  | Cannot convert string to number |

---

# ✅ Key Notes

* `+` with a string → Converts everything to **string**.
* Arithmetic operators (`-`, `*`, `/`, `%`, `**`) → Convert values to **numbers**.
* `true → 1`, `false → 0`.
* `null → 0`, `undefined → NaN`.
* Use **unary +** for quick type conversion to number.

---

# 📝 Challenges: Implicit Type Conversion

1. What will be the output?

   ```js
   console.log("5" + 2);
   console.log("10" - "2");
   console.log(true + false);
   console.log(null + 10);
   console.log(undefined + 10);
   ```

2. Predict the result of:

   ```js
   console.log("5" * "yes");
   console.log("7" * "3");
   console.log("100" / "10");
   ```

3. Create a variable `x = "20"`. Add `10` using:

   * String concatenation
   * Numeric addition (force conversion).

4. Use **unary plus** to convert:

   * `"500"` → number
   * `false` → number
   * `null` → number

5. Write a condition using a variable that contains an **empty string**. Check whether it runs or not (Falsy test).

---