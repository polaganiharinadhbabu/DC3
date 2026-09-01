# Daily Developer Challenge — Day 3

**Name:** Hari Polagani  
**Date:** 01-09-2026  
**Day:** 3  

---

## 1. CODING PROBLEM — CHARACTER FREQUENCY

### My Approach

Create an empty dictionary.  
Check every character in the string.  
Ignore spaces and count each character.

### My Code

```python
def character_frequency(text):
    d = {}

    for c in text:
        if c != " ":
            d[c] = d.get(c, 0) + 1

    return d
```

### Test Case 1

```python
print(character_frequency("hello"))
```

```python
{'h': 1, 'e': 1, 'l': 2, 'o': 1}
```

### Test Case 2

```python
print(character_frequency("programming"))
```

```python
{'p': 1, 'r': 2, 'o': 1, 'g': 2, 'a': 1, 'm': 2, 'i': 1, 'n': 1}
```

### Test Case 3

```python
print(character_frequency("hi all"))
```

```python
{'h': 1, 'i': 1, 'a': 1, 'l': 2}
```

### Time Complexity

**O(n)**

### Bonus

```python
def most_frequent(text):
    d = character_frequency(text)
    return max(d, key=d.get)


print(most_frequent("success"))
```

```python
s
```

---

## 2. CONCEPT QUESTION — FUNCTIONS

### What is a function?

A function is a reusable block of code that performs one task.

### Why do we use functions?

Functions reduce repeated code and make programs easy to read and test.

### Parameter vs Argument

```python
def greet(name):
    print("Hello", name)


greet("Ravi")
```

- Function name: `greet`
- Parameter: `name`
- Argument: `"Ravi"`

### Return vs Print

`print()` displays the value.

`return` sends the value back so it can be stored and used again.

```python
def add(a, b):
    print(a + b)
```

```python
def add(a, b):
    return a + b
```

### Interview Follow-up

```python
def test():
    x = 10


result = test()
print(result)
```

```python
None
```

The function has no `return`, so Python returns `None`.

---

## 3. DEBUGGING CHALLENGE

### What was the problem?

The function printed the total but did not return it.

### Why did it happen?

`result` became `None`.  
`None` cannot be multiplied by `0.10`.

### My Corrected Code

```python
def calculate_total(price, quantity):
    total = price * quantity
    return total


result = calculate_total(100, 3)
print(result)

discount = result * 0.10
print("Discount:", discount)
```

### Output

```python
300
Discount: 30.0
```

### Why does this code work?

The function returns the total.  
That returned value is stored in `result`.  
Then `result` is used to calculate the discount.

### Bonus

```python
def order(price, quantity):
    total = price * quantity
    return price, quantity, total


print(order(100, 3))
```

### Output

```python
(100, 3, 300)
```

The function returns three values: price, quantity, and total.

---

## 4. MINI PROBLEM — PASSWORD VALIDATOR

### My Approach

Check the password length.  
Then check for uppercase, lowercase, and digit.

### My Code

```python
def validate_password(password):
    up = False
    low = False
    num = False

    for c in password:
        if c.isupper():
            up = True
        elif c.islower():
            low = True
        elif c.isdigit():
            num = True

    if len(password) >= 8 and up and low and num:
        return "Valid Password"

    return "Invalid Password"
```

### Test Cases

```python
print(validate_password("Hello123"))
print(validate_password("hello"))
print(validate_password("Python12"))
```

### Output

```python
Valid Password
Invalid Password
Valid Password
```

### Bonus

```python
def validate_password(password):
    up = False
    low = False
    num = False
    sp = False

    for c in password:
        if c.isupper():
            up = True
        elif c.islower():
            low = True
        elif c.isdigit():
            num = True
        elif c in "@#$%!":
            sp = True

    if len(password) >= 8 and up and low and num and sp:
        return "Valid Password"

    return "Invalid Password"
```

---

## 5. MINI INTERVIEW

### Q1. What happens when a function has no return statement?

It returns `None`.

### Q2. Can a function return multiple values?

Yes.

```python
def calc(a, b):
    return a + b, a - b
```

### Q3. Local variable vs Global variable

A local variable is created inside a function.

A global variable is created outside a function.

### Q4. What does `def calculate(a, b=10):` mean?

`b=10` is a default parameter.

### Q5. Purpose of `if __name__ == "__main__":`

It runs the code only when the file is executed directly.

---

## 6. THINK LIKE A DEVELOPER

Separate functions improve readability, reusability, debugging, testing, and maintenance.

```python
def add_student():
    pass


def delete_student():
    pass


def search_student():
    pass


def update_student():
    pass


def display_students():
    pass
```

---

## 7. REFLECTION

### What did I learn today?

I learned functions, return values, strings, dictionaries, and password validation.

### What was difficult?

Understanding the difference between `print()` and `return`.

### What mistake did I make?

I used `print()` where I needed `return`.

### What will I practice again?

Functions, return values, and test cases.
