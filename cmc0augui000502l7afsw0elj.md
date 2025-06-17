---
title: "Week 14 - Dictionaries: Your Personal Phone Book"
datePublished: Tue Jun 17 2025 09:06:55 GMT+0000 (Coordinated Universal Time)
cuid: cmc0augui000502l7afsw0elj
slug: week-14-dictionaries-your-personal-phone-book
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1750151172625/8df1602d-1737-4c13-9ac8-2845b890a521.jpeg
tags: programming-blogs, python, coding, dictionary

---

Hello Future Coders!

Welcome to **Week 14** of our Python Adventures! This week, we're exploring **dictionaries**—those super smart containers that let you find things by name instead of numbers. Think of them as your personal phone book where you look up someone's name to find their number. Ready to become a dictionary master? Let's go!

---

## **Objective**

* Learn what a **dictionary** is and how it's different from lists.
    
* Discover how to **create** dictionaries with **keys** and **values**.
    
* Master adding, changing, and finding information using **keys**.
    
* Practice using dictionaries with simple, fun examples.
    
* Solidify your understanding with fill‑in‑the‑blank exercises and debugging challenges.
    

---

## 1\. What Is a Dictionary?

### **Explanation**

A dictionary is like a special container where every item has a **name tag** (called a **key**) and the **actual item** (called a **value**). Instead of using numbers like lists, you use names to find what you want!

### **Analogy**

Imagine your **phone book**:

1. You look up a **name** (the key) like "Mom".
    
2. You find the **phone number** (the value) like "555-1234".
    
3. You don't need to remember position numbers.
    
4. You can **add** new contacts easily.
    
5. You can **change** numbers when people move.
    

That's exactly how Python dictionaries work—they're your digital phone book!

---

## 2\. Creating Your First Dictionary

### **Syntax**

```python
dictionary_name = {"key1": "value1", "key2": "value2"}

```

* **Curly braces** `{}` create the dictionary.
    
* **Colons** `:` connect keys to values.
    
* **Commas** `,` separate each pair.
    

### **Example: My Family's Phone Numbers**

```python
phone_book = {"Mom": "555-1234", "Dad": "555-5678", "Sister": "555-9999"}
print("My phone book:", phone_book)

# Finding someone's number
print("Mom's number:", phone_book["Mom"])
print("Dad's number:", phone_book["Dad"])

```

**What happens?**

Python creates a dictionary with 3 contacts, and you can find anyone's number by typing their name!

---

## 3\. Interactive Fill‑in‑the‑Blanks

1. **Pet Information**
    
    Complete the blanks to create a dictionary about pets:
    
    ```python
    my_pet = {"name": "Fluffy", "type": ______, "age": ______}  # Add "cat" and 3
    print("My pet info:", my_pet)
    
    # Get pet's name
    pet_name = my_pet[______]  # What key gets the name?
    print("My pet's name is", pet_name)
    
    ```
    
    *(Hint: Use the key names exactly as written!)*
    
2. **Favorite Things**
    
    ```python
    favorites = {"color": "blue", "food": "pizza"}
    
    # Add a new favorite
    favorites[______] = "soccer"  # What key for favorite sport?
    
    print("My favorites:", favorites)
    
    ```
    
    *(Hint: Think of a good key name for sports!)*
    

---

## 4\. Adding and Changing Information

### **Adding New Items**

```python
student_grades = {"Math": 85, "Science": 92}
print("Original grades:", student_grades)

# Adding a new subject
student_grades["English"] = 88
print("After adding English:", student_grades)

# Adding more subjects
student_grades["Art"] = 95
print("All grades:", student_grades)

```

### **Changing Existing Items**

```python
game_scores = {"Level1": 100, "Level2": 150, "Level3": 200}
print("Original scores:", game_scores)

# Beat your high score!
game_scores["Level2"] = 180  # New high score!
print("Updated scores:", game_scores)

```

---

## 5\. Checking What's Inside

```python
backpack_items = {"pencils": 5, "erasers": 2, "rulers": 1}

# Check if we have something
if "pencils" in backpack_items:
    print("Great! I have", backpack_items["pencils"], "pencils")

# Safe way to check
pencil_count = backpack_items.get("pencils", 0)  # Returns 0 if not found
print("Pencil count:", pencil_count)

# Get all keys (names) and values (amounts)
print("All items:", list(backpack_items.keys()))
print("All amounts:", list(backpack_items.values()))

```

---

## 6\. Debugging Challenge

Fix the errors in this code so it runs without mistakes:

```python
# Create a dictionary of favorite movies
movies = ["Action": "Avengers", "Comedy": "Toy Story"]  # What's wrong here?
print("My movies:", movies)

# Add a new movie
movies{"Horror"} = "Monster Movie"  # How do we add to dictionaries?

# Check a movie
if "Action" in movies:
    print("I love action movies!")

```

*(Hint: Check the dictionary creation and how to add new items.)*

---

## 7\. Hands‑On Mini‑Projects

### **A. Student Report Card**

```python
# Create a simple report card
report_card = {"Math": 90, "English": 85, "Science": 88}

# Add a new subject
report_card["History"] = 92

# Show all grades
for subject in report_card:
    grade = report_card[subject]
    print(f"{subject}: {grade}")

```

### **B. Pet Profile**

```python
# Create your pet's profile
pet_profile = {"name": "Buddy", "animal": "dog", "age": 3}

# Update age (birthday!)
pet_profile["age"] = 4

# Add new info
pet_profile["color"] = "brown"

print("Pet Profile:")
for key in pet_profile:
    print(f"{key}: {pet_profile[key]}")

```

### **C. Simple Store**

```python
store_prices = {"apple": 1, "banana": 2, "orange": 3}

# Customer wants to buy something
item = "apple"
if item in store_prices:
    price = store_prices[item]
    print(f"{item} costs ${price}")
else:
    print("Sorry, we don't have that!")

```

---

## 8\. Interactive Challenge: Magic Contact Book

Fill in the blanks to create a simple contact manager:

```python
contacts = {}  # Start empty

# Add first contact
name = "Alice"
phone = "555-1111"
contacts[____] = ____  # (a) How do we add name and phone?

# Add second contact
contacts["Bob"] = "555-2222"

# Look up someone
search_name = "Alice"
if search_name ___ contacts:  # (b) How do we check if key exists?
    phone_number = contacts[search_name]
    print(f"{search_name}'s number is {phone_number}")

# Show all contacts
print("All contacts:")
for name ___ contacts:  # (c) How do we loop through keys?
    print(f"{name}: {contacts[name]}")

```

*(Hints: (a) name, phone, (b) in, (c) in)*

---

## 9\. Simple Dictionary Functions

```python
def add_score(score_dict, player, points):
    score_dict[player] = points
    print(f"Added {player} with {points} points!")

def get_score(score_dict, player):
    if player in score_dict:
        return score_dict[player]
    else:
        return 0

# Test it:
game_scores = {}
add_score(game_scores, "Player1", 100)
add_score(game_scores, "Player2", 85)

print("Player1 score:", get_score(game_scores, "Player1"))
print("Player3 score:", get_score(game_scores, "Player3"))

```

---

## 10\. Homework & Practice

* **Task 1:** Create a `favorite_foods` dictionary with 3 friends' names and their favorite foods. Write code to ask for a friend's name and show their favorite food.
    
* **Task 2:** Make a simple "English-Spanish" translator dictionary with 5 English words as keys and Spanish words as values. Let users type English words to get translations.
    
* **Task 3:** Create a "Birthday Calendar" dictionary where keys are months and values are lists of friends with birthdays in that month.
    

### **Challenge: Fix the Shopping Cart**

Debug this code:

```python
shopping_cart = ("milk": 2, "bread": 1, "eggs": 12)  # Error 1

# Add new item
shopping_cart."cheese" = 1  # Error 2

# Check total items
total = length(shopping_cart)  # Error 3
print("Total different items:", total)

```

---

## 11\. Quiz Time!

1. **Which symbol creates a dictionary in Python?**
    
    * A) `[]` B) `{}` C) `()`
        
2. **What connects keys to values in a dictionary?**
    
    * A) `=` B) `:` C) `>`
        
3. **Fill in the blank to get a value:**
    
    `value = my_dict[____]`
    
    * A) 0 B) "key\_name" C) 1
        
4. **True or False?**
    
    Dictionary keys must be unique (no duplicates).
    
    * A) True B) False
        
5. **Which method safely gets a value without errors?**
    
    * A) `dict[key]` B) `dict.get(key)` C) `dict.find(key)`
        

---

## 12\. Recap & Reflection

* **Dictionaries** store pairs of keys and values, like a phone book.
    
* **Curly braces** `{}` create dictionaries, **colons** `:` connect pairs.
    
* **Keys** are the names you use to find values (like contact names).
    
* **Values** are the information you store (like phone numbers).
    
* **Square brackets** `[]` access values: `my_dict["key"]`.
    

**Discussion Prompt:**

If you could create a magical dictionary that knew everything about your favorite video game, what keys would you use and what information would you store?

**Next Week Preview:**

Get ready to become **debugging detectives**! We'll learn how to find and fix errors in our code like real programmers. Every coder makes mistakes—the good ones know how to fix them!