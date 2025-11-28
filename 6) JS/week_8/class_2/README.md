# ⭐ **Synchronous & Asynchronous JavaScript**

---

## 🥗 **Analogy: Restaurant Example**

Imagine you visit a restaurant where **there is only one chef**.

### **Synchronous Analogy**

You place an order → <br> 
Chef starts cooking your food → <br>
You wait → <br>
Then you get your food.

Chef handles **ONE task at a time**, in **order**, without skipping anything.

This means:

✔ You wait for previous work <br>
✔ No other work starts until the current task finishes

This is exactly how **Synchronous JavaScript** works.

---

### **Asynchronous Analogy**

After some days, the chef becomes smart.

Now he can do:

* Start boiling water for one customer
* Grill chicken for another
* Take a new order
* Serve someone else’s food

Tasks still execute in **one main thread**, but long tasks run **outside** the chef’s kitchen.

This is **Asynchronous JavaScript**.

---

# 🔥 **JavaScript: By Nature Synchronous & Single-Threaded**

✔ JavaScript executes **one line at a time** <br>
✔ Only **one call stack** <br>
✔ Only **one main thread** <br>

Example:

```js
console.log("Start");
console.log("Middle");
console.log("End");
```

Output:

```
Start
Middle
End
```

Every line waits for the previous one.

---

# ⚡ Asynchronous → “Non-blocking”

If a task takes time (API calls, timers, file read), JS says:

**“Start the task… while it finishes, I will do something else.”**

This is Non-Blocking Behavior.

Real-life example:

When you upload a picture on Instagram or Facebook:

✔ Upload in background <br>
✔ You continue using the app <br>
✔ When upload finishes → App notifies you <br>

---

# ⚙ **Asynchronous Example using Web APIs**

```js
console.log("Start");

setTimeout(() => {
  console.log("Waiting Done...!");
}, 2000);

console.log("End");
```

Output:

```
Start
End
Waiting Done...!
```

**Why?**
`setTimeout` is NOT part of JavaScript.
It is part of **Browser Web APIs** (or Node.js APIs).

JS offloads it → continues execution → gets result later → event loop inserts result back.

---

# 🧩 **Callback Functions**

**Definition:**
A callback is a function passed as an argument to another function, to be executed **later**.

### Example (simple & synchronous):

```js
function greet(name, callBack){
  console.log(`Hello ${name}`);
  callBack();
}

greet("John", () => {
  console.log("Goodbye");
});
```

This is **still synchronous** because callback runs immediately.

---

### **Callbacks with Asynchronous Behavior**

```js
function greet(name, callBack){
  console.log(`Hello ${name}`);

  setTimeout(() => {
      callBack();
  }, 2000);

  console.log("I am still hanging here");
}

greet("John", () => {
  console.log("Goodbye");
});
```

Now callback executes **after 2 seconds → truly asynchronous**.

---

# 🌐 **Real Example: API Calls with Callbacks**

```js
function getProductsList() {
    query('https://fakestoreapi.com/products', function (result, error) {
        if (!error) {
            console.log('All products:', result);

            const product1ID = result[0].id;
            const product2ID = result[1].id;

            query(`https://fakestoreapi.com/products/${product1ID}`, function (result, error) {
                if (!error) {
                    console.log('Single product 1:', result);

                    query(`https://fakestoreapi.com/products/${product2ID}`, function (result, error) {
                        if (!error) {
                            console.log('Single product 2:', result);
                        } else {
                            console.log('Error fetching single product:', error);
                        }
                    });

                } else {
                    console.log('Error fetching single product:', error);
                }
            });

        } else {
            console.log('Error fetching products:', error);
        }
    });
}

getProductsList();

function query(url, callback) {
    fetch(url)
        .then(response => response.json())
        .then(data => {
            setTimeout(() => {
                callback(data, null);
            }, 2000)
        })
        .catch(error => callback(null, error));
}
```

---

# 😵 **The Problem: Callback Hell**

### 🧱 What is Callback Hell?

Callback Hell (also called **Pyramid of Doom**) happens when:

* We have multiple nested callbacks
* The code becomes deeply indented
* Hard to read
* Hard to debug
* Hard to maintain

```
callback(
   function() {
       callback(
          function() {
              callback(
                 function() { ... }
              )
          }
       )
   }
)
```

This is why JavaScript introduced:

✔ Promises <br>
✔ async/await <br>
✔ Error handling <br>
✔ Cleaner asynchronous flow <br>

---

# 🏠 **HOME TASK (NO Solutions — Only Questions)**

### **1. Pass a function to greet a user and then thank them**

Write a function that greets a user, then calls a callback that prints a thank-you message.

---

### **2. Implement a calculator function with callback**

```js
function calculator(a, b, operationCallback) {
  // Complete this function
}

function add(x, y) {
  return x + y;
}
```

Test with:

* add
* subtract
* multiply
* divide

---

### **3. delayedMessage(message, delay, callback)**

Use `setTimeout` to show the message after delay, then call callback.

---

### **4. filterNumbers(arr, conditionCallback)**

Return numbers based on a condition using a callback.

Example:

```js
filterNumbers([1, 2, 3, 4], n => n > 2) 
// returns [3, 4]
```

---

### **5. Execute tasks in sequence using callbacks**

```js
function task1(callback) {
  console.log("Task 1 done");
  callback();
}

function task2(callback) {
  console.log("Task 2 done");
  callback();
}

function task3() {
  console.log("Task 3 done");
}
```

Call them in sequence using nested callbacks:

task1 → task2 → task3

---