---
title: "Week 3:  Chatting with Python"
datePublished: Tue Mar 25 2025 10:43:35 GMT+0000 (Coordinated Universal Time)
cuid: cm8odb7ls003v09ih5dpye2w5
slug: week-3-chatting-with-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1742899322590/7cb8165d-0435-4c9e-8422-8b0755864961.jpeg
tags: programming-blogs, python, coding

---

---

## **Welcome, Future Coders!**

In Week 3, we're going to learn how to **chat with our computer**. Just like using a walkie-talkie, your computer can talk back to you! We'll learn how to **show messages** on the screen and ask for answers from the user. This makes your programs interactive and super fun!

---

## **1\. What is Input and Output?**

### **Concept:**

* **Output** is how a computer **talks to you** by displaying text, numbers, and other cool stuff on the screen.
    
* **Input** is how **you talk to the computer** by typing a response.
    

### **Analogy:**

Imagine you have a **walkie-talkie**:

* **When you speak**, your friend hears you (that’s like **input**).
    
* **When they reply**, you hear them (that’s like **output**).
    

### **In Python:**

* We use `print()` to show output on the screen.
    
* We use `input()` to get information from the user.
    

---

## **2\. Exploring Output with** `print()`

### **What Does** `print()` Do?

`print()` tells Python to display what’s inside the parentheses on the screen.

### **Example 1: Simple Message**

```python
pythonCopyEditprint("Hello, World!")
```

*This shows the message "Hello, World!" on your screen.*

### **Example 2: Multiple Items**

```python
pythonCopyEditname = "Emma"
age = 12
print("Hello, my name is", name, "and I am", age, "years old.")
```

*Notice how Python automatically adds spaces between words when you use commas!*

### **Bonus Tip: f-strings**

For a cleaner look, you can use an **f-string**:

```python
pythonCopyEditprint(f"Hello, my name is {name} and I am {age} years old.")
```

*This makes your message easier to read, especially when you're putting lots of things together.*

---

## **3\. Exploring Input with** `input()`

### **What Does** `input()` Do?

`input()` lets the user type something into your program. Whatever they type gets saved in a variable so you can use it later!

### **Example 1: Asking for a Name**

```python
pythonCopyEditname = input("What is your name? ")
print("Nice to meet you, " + name + "!")
```

*If the user types "Emma", the computer will say "Nice to meet you, Emma!"*

### **Handling Numbers with Input**

By default, `input()` treats everything as text. If you need a number, you have to change it!

```python
pythonCopyEditage = int(input("How old are you? "))  # Converts the input to a number
print("Next year, you will be", age + 1)
```

*Remember: Use* `int()` for whole numbers and `float()` for decimal numbers.

---

## **Recap & Reflection**

### **Key Takeaways:**

* `print()` is like the computer talking to you—it shows messages and numbers on the screen.
    
* `input()` is how you tell the computer your answer—like chatting with a friend.
    
* Always convert your input to a number (using `int()` or `float()`) when you need to do math.
    
* By combining **input** and **output**, you can make really interactive and fun programs!
    

### **Discussion Prompt:**

* If you were designing a friendly chatbot, what fun question would you ask people? Write it down and share it in our next class!
    

---

## **What’s Next?**

In our next lesson, we’ll dive even deeper into Python and learn about **variables**—the special boxes where you can store information for your computer. Get ready to unlock more coding secrets!

---

**Happy Coding, Future Coders!**  
*Keep experimenting, have fun, and see you next week for more Python adventures!*

---