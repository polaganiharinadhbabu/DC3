# Daily Developer Challenge — Day 3

**Name:** Hari Polagani  
**Date:** 26-08-2026  
**Day:** 3  

---

## 1. CODING PROBLEM — CHARACTER FREQUENCY

### My Approach

Create an empty dictionary.  
Check every character in the string.  
Ignore spaces and count each character.

### My Code

def character_frequency(text):
    d = {}
    for i in text:
        if i != " ":
            d[i] = d.get(i, 0) + 1
    return d
### Test Case 1
print(character_frequency("hello"))
{'h': 1, 'e': 1, 'l': 2, 'o': 1}

### Test Case 2
print(character_frequency("programming"))
{'p': 1, 'r': 2, 'o': 1, 'g': 2, 'a': 1, 'm': 2, 'i': 1, 'n': 1}

### Test Case 3
print(character_frequency("hi all"))
{'h': 1, 'i': 1, 'a': 1, 'l': 2}

### Time Complexity

**O(n)**

## 2. CONCEPT QUESTION — FUNCTIONS

### What is a function?

A function is a reusable block of code that performs one task.

### Why do we use functions?

Functions reduce repeated code and make programs easy to read and test.

### Parameter vs Argument
def greet(name):
    print("Hello", name)
greet("Ravi")

- Function name: `greet`
- Parameter: `name`
- Argument: `"Ravi"`

### Return vs Print

`print()` displays the value.

`return` sends the value back so it can be stored and used again.

def add(a, b):
    print(a + b)

def add(a, b):
    return a + b

### Interview Follow-up

def test():
    x = 10
result = test()
print(result)

output:
None - The function has no `return`, so Python returns `None`.

## 3. DEBUGGING CHALLENGE

### What was the problem?

The function printed the total but did not return it.

### Why did it happen?

`result` became `None`.  
`None` cannot be multiplied by `0.10`.

### My Corrected Code
def calculate_total(price, quantity):
    total = price * quantity
    return total
result = calculate_total(100, 3)
print(result)
discount = result * 0.10
print("Discount:", discount)

### Output

300
Discount: 30.0


### Why does this code work?

The function returns the total.  
That returned value is stored in `result`.  
Then `result` is used to calculate the discount.

## 4. MINI PROBLEM — PASSWORD VALIDATOR

### My Approach

Check the password length.  
Then check for uppercase, lowercase, and digit.

### My Code

def validate_password(password):
    up = False
    low = False
    num = False

    for i in password:
        if i.isupper():
            up = True
        elif i.islower():
            low = True
        elif i.isdigit():
            num = True

    if len(password) >= 8 and up and low and num:
        return "Valid Password"
else:
    return "Invalid Password"


### Test Cases

print(validate_password("Hello123"))
print(validate_password("hello"))

### Output

Valid Password
Invalid Password

## 5. MINI INTERVIEW

### Q1. What happens when a function has no return statement?

It returns `None`.

### Q2. Can a function return multiple values?

Yes.

def calc(a, b):
    return a + b, a - b


### Q3. Local variable vs Global variable

A local variable is created inside a function.

A global variable is created outside a function.

### Q4. What does `def calculate(a, b=10):` mean?

`b=10` is a default parameter.

### Q5. Purpose of `if __name__ == "__main__":`

It runs the code only when the file is executed directly.

## 6. THINK LIKE A DEVELOPER

Separate functions improve readability, reusability, debugging, testing, and maintenance.

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

## 7. REFLECTION

### What did I learn today?

I learned functions, return values, strings, dictionaries, and password validation.

### What was difficult?

Understanding the difference between `print()` and `return`.

### What mistake did I make?

I used `print()` where I needed `return`.

### What will I practice again?

Functions, return values, and test cases.
