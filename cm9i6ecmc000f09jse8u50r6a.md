---
title: "Week 6 – Loops: Repeating the Story"
datePublished: Tue Apr 15 2025 07:23:09 GMT+0000 (Coordinated Universal Time)
cuid: cm9i6ecmc000f09jse8u50r6a
slug: week-6-loops-repeating-the-story
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1744701334690/b1653071-1eaf-4913-b1df-a243b3c4205f.jpeg
tags: python, python3, for-loop, python-beginner, while-loop, loops-in-python

---

Hello Future Coders!

Welcome to Week 6 of our Python Adventures! This week, we’re going to explore **loops**—the magic tool that lets us repeat actions without writing the same code over and over. Loops help our programs do things like repeat a chorus in your favorite song or a dance move at a party!

---

## **Objective**

* Learn what **for loops** and **while loops** are and why we use them.
    
* Understand how loops can help you repeat parts of your story.
    
* Practice writing loops with interactive fill-in-the-blank challenges and debugging exercises.
    
* Complete extra challenges to strengthen your understanding of loops.
    

---

## **1\. What Are Loops?**

### **Explanation:**

A **loop** is a way to tell your computer to repeat a block of code many times. Instead of writing the same command over and over, you write it once and let the loop do the work.

### **Analogy:**

Imagine you’re dancing to your favorite song. You repeat the same move every time the chorus comes on. That repeating move is like a loop!

* **For Loops:**
    
    Use these when you know exactly how many times to repeat something.
    
* **While Loops:**
    
    Use these when you want to keep repeating until something changes.
    

---

## **2\. Using For Loops**

### **Example:**

```python
for i in range(5):
    print("The adventure continues!")
```

* This for loop repeats the message **5 times**.
    
* **Interactive Challenge:**
    
    Fill in the blank to make the loop print "Step X: Onward!" 4 times:
    
    ```python
    for i in range(__):
        print("Step", i+1, ": Onward!")
    ```
    
    *(Hint: The blank should be replaced with the number 4.)*
    

---

## **3\. Using While Loops**

### **Example:**

```python
counter = 1
while counter <= 5:
    print("Step", counter, ": Keep moving!")
    counter = counter + 1
```

* This while loop continues until `counter` becomes 6.
    
* **Interactive Debug Challenge:**
    
    Look at this code and fix the bug:
    
    ```python
    count = 1
    while count < 5:
        print("Count is", count)
        count = count  # What should we do here?
    ```
    
    *(Hint: We need to update* `count` by adding 1 each time.)
    

---

## **4\. Extended Interactive Challenges**

### **Challenge 1: The Summing Loop**

Write a program that asks the user for a number and then uses a for loop to calculate the sum of all numbers from 1 up to that number.

**Skeleton Code (Fill-in-the-Blanks):**

```python
# Ask the user for a number
n = int(input("Enter a number: "))

total = 0
for i in range(1, _______):
    total = total + i
print("The sum from 1 to", n, "is", total)
```

*(Hint: Fill in the blank with the appropriate end value using the variable n.)*

### **Challenge 2: Pattern Printing**

Write a program that uses a while loop to print numbers 1 through 5 on separate lines.

**Skeleton Code:**

```python
number = 1
while number <= 5:
    print(number)
    ___________  # What should we do here?
```

*(Hint: Increase the value of* `number` by 1 each time.)

---

## **5\. Additional Homework / Practice**

### **Task 1: Adventure Game Enhancement**

Enhance your existing adventure game (from a previous week) by adding a loop. For example, after a decision is made, use a for loop to repeat a suspenseful message:

```python
for i in range(3):
    print("The mysteries of the forest continue to unfold...")
```

Try changing the number of repetitions and see how it changes the tension in your story!

### **Task 2: Create Your Own Looping Song**

Write a program that prints out the lines of a song or chant repeatedly. For instance:

```python
for i in range(4):
    print("We are the Python coders, hear us code!")
```

Then, modify it to use a while loop instead.

### **Task 3: Debug Challenge**

Below is a piece of buggy code. Find and fix the error so that it prints numbers 1 to 5:

```python
number = 1
while number < 5:
    print(number)
```

*(Hint: The code never updates* `number`!)

---

## **6\. Quiz Time!**

1. **What is the main purpose of a loop?**
    
    * A) To repeat a set of instructions multiple times.
        
    * B) To make decisions.
        
    * C) To print messages on the screen.
        
2. **How many times will this loop run?**
    
    ```python
    for i in range(5):
        print("Coding is fun!")
    ```
    
    * A) 4 times.
        
    * B) 5 times.
        
    * C) 6 times.
        
3. **In a while loop, what must you include to prevent an endless loop?**
    
    * A) A print statement.
        
    * B) An update to the condition (like incrementing a counter).
        
    * C) A comment explaining the loop.
        
4. **Fill in the blank:**
    
    To print numbers 1 to 5 using a while loop, we update the counter with:
    
    ```python
    number = number _______ 1
    ```
    
    * A) +
        
    * B) -
        
    * C) \*
        

---

## **7\. Recap & Reflection**

### **Key Takeaways:**

* **Loops** are a tool that let you repeat tasks without writing them multiple times.
    
* **For loops** repeat actions a set number of times, while **while loops** repeat until a condition changes.
    
* By using loops, you can create patterns, build interactive stories, and even enhance your games!
    

**Discussion Prompt:**

Imagine you’re choreographing a dance for your robot. How many times do you want it to repeat its favorite move? Write your idea down!

---

## **What's Next?**

Next week, we’ll learn about **Functions (writing simple, reusable code),** which will help your programs make decisions, like a smart robot choosing what to do next based on different conditions. Get ready to add even more interactivity to your coding adventures!

---

**Happy Coding, Future Coders!**

Keep practicing these loops, experiment with the challenges, and have fun on your quest for the magic treasure of coding!

---