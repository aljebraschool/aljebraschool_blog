---
title: "Week 15 - Debugging: Becoming a Code Detective"
datePublished: Tue Jul 01 2025 10:30:52 GMT+0000 (Coordinated Universal Time)
cuid: cmcke0chm000w02jo5cceh77h
slug: week-15-debugging-becoming-a-code-detective
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1751365717425/81569912-7911-415c-9dce-5d5d967011bf.jpeg
tags: python, debugging, coding, python-beginner

---

Hello Future Coders!

Welcome to **Week 15** of our Python Adventures! This week, we're becoming **code detectives** who solve mysterious bugs in our programs. Every programmer writes code that doesn't work perfectly the first time—and that's totally normal! The secret is knowing how to find and fix these sneaky little problems. Ready to put on your detective hat? Let's go!

---

## **Objective**

* Learn what **bugs** and **debugging** mean in programming.
    
* Discover the most common types of **errors** that happen in Python.
    
* Master **detective techniques** to find and fix problems in code.
    
* Practice using **try/except** to handle errors gracefully.
    
* Solidify your understanding with fun bug-hunting challenges.
    

---

## 1\. What Is a Bug?

### **Explanation**

A "bug" is just a mistake in your code that makes it not work the way you want. Bugs are like puzzles—once you solve them, your code works perfectly!

### **Analogy**

Imagine you're following a **recipe to bake cookies**:

1. **Spelling mistake**: "Add 1 cup of flwor" (typo!)
    
2. **Wrong amount**: "Add 10 cups of salt" (too much!)
    
3. **Missing step**: Forgot to mention "Turn on the oven"
    
4. **Wrong order**: "Eat the cookies, then bake them"
    

Just like cooking, coding has similar mistakes. Good detectives know how to spot and fix them!

---

## 2\. The Most Common Bug Types

### **Type 1: Syntax Errors (Spelling Mistakes)**

```python
# BROKEN CODE - Can you spot the problem?
print("Hello World"  # Missing something?

# FIXED CODE
print("Hello World")  # Added closing parenthesis!

```

### **Type 2: Name Errors (Using Wrong Names)**

```python
# BROKEN CODE
my_name = "Alice"
print(myname)  # Wrong variable name!

# FIXED CODE
my_name = "Alice"
print(my_name)  # Correct variable name!

```

### **Type 3: Type Errors (Wrong Data Types)**

```python
# BROKEN CODE
age = "10"  # This is text, not a number!
next_year = age + 1  # Can't add text and number!

# FIXED CODE
age = 10  # This is a number!
next_year = age + 1  # Now it works!

```

---

## 3\. Interactive Bug Hunt #1

Find and fix the bugs in these codes:

### **Bug Hunt A: The Broken Greeting**

```python
def greet_friend(name)  # (1) What's missing here?
    print("Hello, " + name + "!"
    print("Nice to see you!")  # (2) What's missing here?

greet_friend("Sam")

```

*Hints: (1) Look at the end of the function line, (2) Count the parentheses*

### **Bug Hunt B: The Confused Calculator**

```python
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")
result = num1 + num2  # This will give a weird result!
print("Sum:", result)

```

*Hint: What type of data does* `input()` give you?

---

## 4\. Detective Tools: Reading Error Messages

### **Understanding Python's Error Messages**

```python
# Let's make an error on purpose
print(hello)  # Variable doesn't exist

```

**Python tells us:**

```python
NameError: name 'hello' is not defined

```

**Detective Translation:**

* **NameError**: "I don't know what 'hello' is"
    
* **Solution**: Define the variable or fix the spelling
    

### **More Error Examples:**

```python
# SyntaxError Example
print("Hello"  # Missing closing parenthesis
# Python says: SyntaxError: unexpected EOF while parsing

# TypeError Example
"5" + 3  # Can't add text and number
# Python says: TypeError: can only concatenate str (not "int") to str

```

---

## 5\. Hands-On Bug Fixing Practice

### **Exercise A: Fix the Pet Story**

```python
# BROKEN CODE - Find all 4 bugs!
def pet_story():
    pet_name = input("What's your pet's name? ")
    pet_type = input("What kind of pet? ")
    pet_age = input("How old? ")

    print("My pet " + pet_name + " is a " + pet_type)
    print("They are " + pet_age + " years old.")  # Bug 1: Type issue

    if pet_age > 5:  # Bug 2: Comparing text to number
        print("That's an older pet!")

    print("I love my pet!"  # Bug 3: Missing something

pet_story(  # Bug 4: Missing something

```

### **Exercise B: The Shopping Calculator**

```python
# BROKEN CODE - Find the bugs!
def calculate_total():
    item1 = float(input("Price of item 1: $"))
    item2 = float(input("Price of item 2: $"))
    item3 = float(input("Price of item 3: $"))

    total = item1 + item2 + item3
    tax = total * 0.08
    final_total = total + tax

    print("Subtotal: $" + total)  # Bug: Wrong data type
    print("Tax: $" + str(tax))
    print("Total: $" + str(final_total))

calculate_total()

```

---

## 6\. Safe Coding with Try/Except

### **What is Try/Except?**

Sometimes we know our code might have problems (like when users type the wrong thing). We can use `try/except` to handle these problems nicely!

### **Basic Try/Except Example:**

```python
# Without try/except - program crashes!
def unsafe_division():
    num1 = int(input("Enter first number: "))
    num2 = int(input("Enter second number: "))
    result = num1 / num2
    print("Answer:", result)

# With try/except - program stays friendly!
def safe_division():
    try:
        num1 = int(input("Enter first number: "))
        num2 = int(input("Enter second number: "))
        result = num1 / num2
        print("Answer:", result)
    except ZeroDivisionError:
        print("Oops! You can't divide by zero!")
    except ValueError:
        print("Please enter valid numbers only!")

safe_division()

```

---

## 7\. Interactive Challenge: Build a Bug-Proof Age Calculator

Fill in the blanks to create a safe age calculator:

```python
def age_calculator():
    try:
        birth_year = _____(input("What year were you born? "))  # (a) Convert to number
        current_year = 2024

        age = current_year - birth_year

        if age < 0:
            print("You can't be born in the future!")
        elif age > 150:
            print("Wow, that's very old! Are you sure?")
        else:
            print(f"You are {age} years old!")

    except _____:  # (b) What error happens with bad input?
        print("Please enter a valid year (like 2010)!")
    except Exception:
        print("Something went wrong. Try again!")

age_calculator()

```

*Hints: (a) int, (b) ValueError*

---

## 8\. Detective Techniques: Step-by-Step Debugging

### **Technique 1: Print Statements (Code Detectives' Magnifying Glass)**

```python
def mystery_function(x, y):
    print(f"DEBUG: x = {x}, y = {y}")  # See what we're working with

    result = x * 2 + y
    print(f"DEBUG: result = {result}")  # Check our calculation

    if result > 10:
        print("DEBUG: result is greater than 10")
        return "Big number!"
    else:
        print("DEBUG: result is 10 or less")
        return "Small number!"

# Test it:
answer = mystery_function(3, 5)
print("Final answer:", answer)

```

### **Technique 2: Check One Thing at a Time**

```python
# Instead of writing everything at once:
def check_grade(score):
    # Step 1: Make sure we got a number
    print(f"Step 1: Score is {score}")

    # Step 2: Check if it's a valid grade
    if score < 0 or score > 100:
        return "Invalid score"

    # Step 3: Determine letter grade
    if score >= 90:
        return "A"
    elif score >= 80:
        return "B"
    elif score >= 70:
        return "C"
    else:
        return "F"

```

---

## 9\. Fun Bug Hunt Games

### **Game 1: Spot the Syntax Errors**

Each line has exactly one syntax error. Can you find them all?

```python
# Line 1
print("Hello World"

# Line 2
my_list = [1, 2, 3, 4, 5

# Line 3
if 5 > 3
    print("Math works!")

# Line 4
def my_function()
    return "Hello"

# Line 5
my_dict = {"name": "Alice", "age": 12

```

### **Game 2: Logic Detective**

This code should ask for your favorite color and respond, but something's wrong:

```python
def color_game():
    color = input("What's your favorite color? ")

    if color = "blue":  # Problem here!
        print("Blue is cool like the ocean!")
    elif color = "red":  # And here!
        print("Red is warm like fire!")
    else:
        print("That's a nice color!")

color_game()

```

---

---

## 11\. Quiz Time!

1. **What is a bug in programming?**
    
    * A) An insect in your computer
        
    * B) A mistake in your code
        
    * C) A virus
        
2. **Which error happens when you forget a colon?**
    
    * A) NameError B) SyntaxError C) TypeError
        
3. **What does try/except do?**
    
    * A) Finds bugs automatically
        
    * B) Handles errors gracefully
        
    * C) Makes code run faster
        
4. **True or False?**
    
    All programmers write perfect code the first time.
    
    * A) True B) False
        
5. **What's the best way to debug code?**
    
    * A) Guess what's wrong
        
    * B) Read error messages and test step by step
        
    * C) Start over completely
        

---

## 12\. Recap & Reflection

* **Bugs** are normal mistakes that all programmers make.
    
* **Error messages** are Python's way of helping you find problems.
    
* **Try/except** blocks help your programs handle errors gracefully.
    
* **Print statements** are like a detective's magnifying glass.
    
* **Good detectives** check one thing at a time and stay patient!
    

**Discussion Prompt:**

Think of a time when you had to solve a puzzle or fix something that was broken. How did you figure out what was wrong? How is debugging code similar to solving real-world problems?

**Next Week Preview:**

Get ready for **Complex Functions**! We'll learn how to build powerful functions that can work with lists and dictionaries, making our programs even more amazing. You'll be like a master chef creating recipes that work with any ingredients!