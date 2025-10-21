

### 1. How do you select elements in the DOM?

You use JavaScript to grab things from your HTML. Think of it like pointing to something on the page.

- `getElementById("taskInput")` → grabs an element with that ID.
- `querySelector(".className")` → grabs the first thing with that class.
- `querySelectorAll("li")` → grabs all `<li>` items.

---

### 2. What are event listeners?

They’re like ears for your webpage. You tell it: “Hey, listen for a click!” and it reacts.

```js
button.addEventListener("click", () => {
  alert("You clicked me!");
});
```

---

### 3. What is event delegation?

Instead of adding a click to every item, you add one to the parent and check what was clicked.

```js
list.addEventListener("click", (e) => {
  if (e.target.tagName === "LI") {
    e.target.classList.toggle("done");
  }
});
```

It’s cleaner and works even for new items you add later.

---

### 4. How do you prevent default behavior?

Sometimes a form tries to submit or a link wants to reload the page. You can stop that:

```js
form.addEventListener("submit", (e) => {
  e.preventDefault();
});
```

---

### 5. What’s the difference between var, let, and const?

- `var` is old-school. It works everywhere but can be messy.
- `let` is modern and flexible. Use it when the value might change.
- `const` is for things that won’t change.

```js
let score = 10;
const name = "Alanwoko";
```

---

### 6. What is bubbling and capturing?

When you click something, the event travels:

- **Capturing**: from the top down.
- **Bubbling**: from the clicked thing back up.

Most of the time, bubbling is used. You can stop it with `e.stopPropagation()`.

---

### 7. How do you add or remove classes?

You can style things by adding or removing classes:

```js
element.classList.add("active");
element.classList.remove("active");
element.classList.toggle("active");
```

---

### 8. What is closure?

It’s when a function remembers stuff from where it was created.

```js
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}

const counter = outer();
counter(); // 1
counter(); // 2
```

Even though `outer()` is done, `inner()` still remembers `count`.

---

### 9. What are arrow functions?

They’re a shorter way to write functions:

```js
const greet = (name) => `Hello, ${name}`;
```

They don’t have their own `this`, so they behave differently inside objects.

---

### 10. What’s the difference between `==` and `===`?

- `==` checks if values are equal but can convert types.
- `===` checks if values and types are equal.

```js
"5" == 5   // true
"5" === 5  // false
```

Always use `===` to be safe.