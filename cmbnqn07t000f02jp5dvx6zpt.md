---
title: "Week 13 - Lists: Your Digital Backpack"
datePublished: Sun Jun 08 2025 14:08:01 GMT+0000 (Coordinated Universal Time)
cuid: cmbnqn07t000f02jp5dvx6zpt
slug: week-13-lists-your-digital-backpack
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1749391567190/2ecb61de-a9ab-433c-a255-81f3cd120f08.jpeg
tags: programming-blogs, python, coding, list

---

Hello Future Coders!

Welcome to **Week 13** of our Python Adventures! This week, we're diving into **lists**—those amazing containers that can hold multiple items at once. Think of them as your digital backpack where you can store, organize, and manage collections of things. Ready to pack your coding backpack? Let's go!

---

## **Objective**

* Learn what a **list** is and why it's incredibly useful for storing multiple items.
    
* Discover how to **create** lists and **access** items inside them.
    
* Master adding and removing items with **append()**, **remove()**, and **pop()**.
    
* Practice using lists with **loops** and **conditionals** from previous weeks.
    
* Solidify your understanding with fill‑in‑the‑blank exercises and debugging challenges.
    

---

## 1\. What Is a List?

### **Explanation**

A list is like a container that can hold multiple items in order. Unlike a single variable that holds one value, a list can store many values that you can access, change, or organize.

### **Analogy**

Imagine your **school backpack**:

1. You can **pack** different items (pencils, books, snacks).
    
2. You can **check** what's inside without emptying everything.
    
3. You can **add** new items when you need them.
    
4. You can **remove** items you don't need anymore.
    
5. Everything stays **organized** in the order you put them.
    

That's exactly how Python lists work—they're your digital backpack!

---

## 2\. Creating Your First List

### **Syntax**

```python
list_name = [item1, item2, item3]

```

* **Square brackets** `[]` create the list.
    
* **Commas** `,` separate each item.
    
* Items can be **strings**, **numbers**, or even **mixed**!
    

### **Example: My Favorite Snacks**

```python
favorite_snacks = ["cookies", "apples", "chips", "candy"]
print("My snack list:", favorite_snacks)

# Accessing items by position (starting from 0)
print("First snack:", favorite_snacks[0])    # cookies
print("Second snack:", favorite_snacks[1])   # apples
print("Last snack:", favorite_snacks[-1])    # candy (negative counts from end!)

```

**What happens?**

Python creates a list with 4 snacks, and you can pick any snack by its position number!

---

## 3\. Interactive Fill‑in‑the‑Blanks

1. **Creating a Pet List**
    
    Complete the blanks to create a list of pets:
    
    ```python
    my_pets = [______, "cat", ______]  # Add "dog" and "hamster"
    print("I have these pets:", my_pets)
    
    # Access the first pet
    first_pet = my_pets[___]  # What number goes here?
    print("My first pet is a", first_pet)
    
    ```
    
    *(Hint: Lists start counting from 0!)*
    
2. **List Length**
    
    ```python
    colors = ["red", "blue", "green", "yellow"]
    
    # How many colors do we have?
    total_colors = _____(colors)  # Which function tells us the length?
    print("We have", total_colors, "colors")
    
    ```
    
    *(Hint: Remember the function that counts things?)*
    

---

## 4\. Adding and Removing Items

### **Adding Items with append()**

```python
shopping_list = ["milk", "bread"]
print("Original list:", shopping_list)

# Adding one item at the end
shopping_list.append("eggs")
print("After adding eggs:", shopping_list)

# Adding more items
shopping_list.append("cheese")
shopping_list.append("apples")
print("Final list:", shopping_list)

```

### **Removing Items**

```python
game_inventory = ["sword", "shield", "potion", "map", "key"]
print("Starting inventory:", game_inventory)

# Remove a specific item
game_inventory.remove("potion")  # Removes "potion"
print("After using potion:", game_inventory)

# Remove the last item
last_item = game_inventory.pop()  # Removes and returns "key"
print("Removed item:", last_item)
print("Current inventory:", game_inventory)

# Remove item at specific position
first_item = game_inventory.pop(0)  # Removes "sword" at position 0
print("Removed first item:", first_item)
print("Final inventory:", game_inventory)

```

---

## 5\. Debugging Challenge

Fix the errors in this code so it runs without mistakes:

```python
# Create a list of favorite movies
movies = "Toy Story", "Finding Nemo", "Up"  # What's missing here?
print("My movies:", movies)

# Add a new movie
movies.add("Cars")  # Is this the right method?

# Check if a movie exists
if "Up" in movies:
    print("I love Up!")

```

*(Hint: Check the list creation and the method for adding items.)*

---

## 6\. Hands‑On Mini‑Projects

### **A. Classroom Roster**

1. **Task:** Create a list called `students` with 5 student names.
    
2. **Add:** Two more students using `append()`.
    
3. **Remove:** One student who transferred schools.
    
4. **Display:** The final roster with total count.
    

```python
# Your code here:
students = ["Alice", "Bob", "Charlie", "Diana", "Eve"]
# Continue building this...

```

### **B. Daily Task Manager**

1. **Create** a `tasks` list with 3 things you need to do today.
    
2. **Add** 2 more tasks as you remember them.
    
3. **Complete** tasks by removing them from the list.
    
4. **Check** how many tasks are left.
    

### **C. Number Collection Game**

1. **Start** with an empty list called `numbers`.
    
2. **Use a loop** to ask the user for 5 numbers.
    
3. **Add** each number to the list.
    
4. **Display** all numbers and find the biggest one.
    

```python
numbers = []
for i in range(5):
    # Your code to get input and add to list
    pass

```

---

## 7\. Lists with Loops and Conditionals

### **Looping Through Lists**

```python
fruits = ["apple", "banana", "orange", "grape"]

# Method 1: Loop through items directly
print("I like these fruits:")
for fruit in fruits:
    print("- " + fruit)

# Method 2: Loop through positions
print("\\nNumbered list:")
for i in range(len(fruits)):
    print(f"{i+1}. {fruits[i]}")

```

### **Finding Items in Lists**

```python
def find_item_in_backpack(backpack, item):
    if item in backpack:
        position = backpack.index(item)  # Find where it is
        return f"Found {item} at position {position}!"
    else:
        return f"Sorry, {item} is not in your backpack."

# Test it:
my_backpack = ["notebook", "pen", "calculator", "lunch"]
print(find_item_in_backpack(my_backpack, "pen"))
print(find_item_in_backpack(my_backpack, "phone"))

```

---

## 8\. Interactive Challenge: Build Your Own Adventure Inventory

Fill in the blanks to create an adventure game inventory system:

```python
def manage_inventory():
    inventory = []  # Start with empty inventory

    print("Welcome to Adventure Inventory Manager!")

    while True:
        print("\\nOptions: 'add', 'remove', 'list', 'quit'")
        action = input("What do you want to do? ").lower()

        if action == "add":
            item = input("What item do you want to add? ")
            inventory.______(item)  # (a) Which method adds items?
            print(f"Added {item} to inventory!")

        elif action == "remove":
            if len(inventory) ___ 0:  # (b) What comparison checks if list is empty?
                item = input("What item do you want to remove? ")
                if item in inventory:
                    inventory.______(item)  # (c) Which method removes specific items?
                    print(f"Removed {item} from inventory!")
                else:
                    print("You don't have that item!")
            else:
                print("Your inventory is empty!")

        elif action == "list":
            if len(inventory) > 0:
                print("Your inventory contains:")
                for i, item in enumerate(inventory):
                    print(f"{___}. {item}")  # (d) What shows the position number?
            else:
                print("Your inventory is empty!")

        elif action == "quit":
            print("Thanks for playing!")
            break

# Call the function
manage_inventory()

```

*(Hints: (a) append, (b) &gt;, (c) remove, (d) i+1)*

---

## 9\. Homework & Practice

* **Task 1:** Create a `favorite_books` list with 3 books. Write a function `add_book(book_list, new_book)` that adds a book only if it's not already in the list.
    
* **Task 2:** Make a `high_scores` list with 5 numbers. Write code to find and print the highest and lowest scores without using `max()` and `min()` functions.
    
* **Task 3:** Create a simple "To-Do List" program where users can:
    
    * Add tasks
        
    * Mark tasks as complete (remove them)
        
    * See all remaining tasks
        
    * Count how many tasks are left
        

### **Challenge: List Detective**

Debug this code that's supposed to manage a class pet list:

```python
pets = ["hamster", "fish", "turtle"]

# Add new pets
pets.add("rabbit")  # Error 1
pets.append("bird")

# Remove a pet that graduated
pets.remove("hamster")

# Check if we have specific pets
if "fish" in pets:
    print("We still have our fish!")

if pets[5]:  # Error 2
    print("Position 5 has a pet")

print("Total pets:", length(pets))  # Error 3

```

---

## 10\. Quiz Time!

1. **Which symbol creates a list in Python?**
    
    * A) `()` B) `[]` C) `{}`
        
2. **What does** `my_list.append("item")` do?
    
    * A) Removes an item
        
    * B) Adds "item" to the beginning
        
    * C) Adds "item" to the end
        
3. **Fill in the blank to get the first item:**
    
    `first_item = my_list[___]`
    
    * A) 1 B) 0 C) -1
        
4. **True or False?**
    
    `len(my_list)` tells you how many items are in the list.
    
    * A) True B) False
        
5. **Which method removes a specific item from a list?**
    
    * A) `delete()` B) `remove()` C) `pop()`
        

---

## 11\. Recap & Reflection

* **Lists** store multiple items in order, like a digital backpack.
    
* **Square brackets** `[]` create lists, and **commas** separate items.
    
* `append()` adds items to the end, `remove()` removes specific items.
    
* **Index numbers** start from 0 to access items: `list[0]` is the first item.
    
* **Loops** help you go through all items in a list easily.
    

**Discussion Prompt:**

If you could create a magical list that automatically organized itself, what would you put in it? How would you want it to behave differently from regular lists?

**Next Week Preview:**

Get ready for **dictionaries**—they're like lists, but instead of using numbers to find items, you use special keys (like a real-life dictionary where you look up words to find their meanings)!