# Day 1 — Python Syntax & Data Types

## Goal
Write Python confidently without second-guessing syntax.

---

## 3 Things Different from JS

### 1. No `const`, `let`, or `var` — Just Assign
In JS you declare variables with keywords:
```javascript
const name = "Achille";
let age = 20;
```
In Python, just assign directly — no keywords, no semicolons:
```python
name = "Achille"
age = 20
is_active = True  # note: True/False capitalized, not true/false like JS
```
Python figures out the type automatically just like JS, but the syntax is cleaner.

---

### 2. F-strings Instead of Template Literals
In JS you use backticks and `${}`:
```javascript
console.log(`Hello ${name}, you are ${age}`);
```
In Python you prefix the string with `f` and use `{}`:
```python
print(f"Hello {name}, you are {age}")  # Hello Achille, you are 20
```
Same idea, different syntax. F-strings also support expressions inside `{}`:
```python
print(f"In 10 years you'll be {age + 10}")  # In 10 years you'll be 30
```

---

### 3. Negative Indexing on Lists
In JS, to get the last element:
```javascript
items[items.length - 1]  // tedious
```
In Python, you can go backwards directly:
```python
items = ["a", "b", "c", "d"]
print(items[-1])   # d  ← last element
print(items[-2])   # c  ← second to last
print(items[0])    # a  ← still works normally
```
This is a Python superpower — no equivalent in vanilla JS.

---

### 4. Lists vs Arrays
Python lists work like JS arrays but with different method names:
```python
items = ["a", "b", "c"]
items.append("d")      # JS: items.push("d")
print(len(items))      # JS: items.length  ← len() is a function, not a property!
```
Key difference: `length` in JS is a property, `len()` in Python is a built-in function.

---

### 5. Dicts vs Objects
Python dicts are like JS objects but accessed with `[]` not `.`:
```python
user = {"name": "Achille", "age": 20}
print(user["name"])                      # Achille  ← must use brackets
print(user.get("email", "no email"))     # no email ← safe access with default
```
In JS, accessing a missing key gives `undefined`. In Python, `user["email"]` throws a `KeyError` — use `.get()` to be safe!

---

### 6. Tuples — Immutable Lists
JS has no direct equivalent. Tuples are like frozen arrays:
```python
coords = (1.94, 30.06)
print(coords[0])   # 1.94
coords[0] = 5      # ❌ throws TypeError — tuples are read-only!
```
Use tuples when data should never change — like coordinates, RGB values, or fixed configs.
JS equivalent would be `Object.freeze([1.94, 30.06])` but that's rarely used.

---

## Quick Cheat Sheet

| Concept | JavaScript | Python |
|--------|-----------|--------|
| Declare variable | `let x = 5` | `x = 5` |
| String interpolation | `` `Hello ${name}` `` | `f"Hello {name}"` |
| Array/List length | `items.length` | `len(items)` |
| Add to array/list | `items.push("d")` | `items.append("d")` |
| Last element | `items[items.length-1]` | `items[-1]` |
| Safe key access | `obj?.key ?? "default"` | `dict.get("key", "default")` |
| Boolean values | `true / false` | `True / False` |
| Immutable array | `Object.freeze([])` | `tuple = (1, 2, 3)` |

---

## Commit
```
docs: add day 1 python syntax notes
```