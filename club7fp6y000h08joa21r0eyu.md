---
title: "Python for Machine Learning"
datePublished: Thu Mar 28 2024 12:22:13 GMT+0000 (Coordinated Universal Time)
cuid: club7fp6y000h08joa21r0eyu
slug: python-for-machine-learning
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1711627490149/55667be8-6f2f-4011-ae25-c9b8d71ddf4b.jpeg
tags: python, data-science, machine-learning, python-beginner, machine-learning-with-python-course, machine-learning-models

---

## Introduction

---

Python's significance in the realm of machine learning stems from its straightforwardness, adaptability, and rich library support. As we venture into Python programming for machine learning, it's crucial to grasp the fundamental principles that underpin Python's functionality.

This article embarks on an exploration of the core elements of Python programming crucial for comprehending and implementing machine learning algorithms. It commences with variables, which serve as containers for data storage. Proficiency in utilizing variables is paramount for effectively managing data in Python programs.

Subsequently, the discussion extends to data types, which dictate the types of data Python can handle. Python accommodates diverse data types such as integers, floats, strings, and more. Proficiency in working with these data types is indispensable for processing and analyzing data in machine learning endeavors.

Control statements enable the regulation of program flow based on specific conditions. Python offers constructs like if statements, loops (for and while), and conditional expressions. Mastery of these control statements is crucial for integrating decision-making logic into machine learning algorithms.

Lastly, data structures play a pivotal role in organizing and managing data efficiently. Python provides built-in data structures such as lists, tuples, sets, and dictionaries. The article discusses how these structures can be employed to store and manipulate data effectively, thereby enhancing the performance of machine learning algorithms.

By addressing these foundational topics—variables, data types, data structures, and control statements—you will develop a solid comprehension of Python programming essential for embarking on the journey into machine learning. This exploration elucidates Python's capabilities and demonstrates how they empower individuals to tackle intricate machine learning tasks with confidence and clarity.

---

## Variables

Variables serve as containers for storing data in programming. Much like their counterparts in mathematics, variables derive their name from the fact that their values can vary. They act as placeholders, allowing us to store items for future use, with the flexibility to replace, update, or delete them as needed.

In mathematics, variables are typically represented by English alphabets such as x, y, a, b, and so on. Similarly, in programming, we use variables to hold values that may change during the execution of a program.

For instance, consider the assignment statement `x = 2`. Here, the variable `x` is assigned the value '2'. It's crucial to note that the symbol '=' in programming is not an equation symbol but an assignment symbol, indicating that the value '2' is being stored in the variable `x`.

## Data Types

Just like in math, programming deals with different types of numbers, including decimals, whole numbers, real numbers, and even complex numbers. Each piece of data stored in a variable has its own type. Python, known for its flexible nature, doesn't require you to declare the type of data explicitly in your code. However, Python recognizes basic data types like integers (for whole numbers), floats (for decimals), and booleans (which represent true/false values, often as 0 and 1).

In Python, when you perform basic math operations like addition, subtraction, multiplication, and division, it's important that the types of the values you're operating on match. Just like in math class, Python follows the standard order of operations (BODMAS/BIDMAS), where calculations inside brackets are done first, followed by multiplication, division, addition, and subtraction. This principle is known as the order of precedence in Python.

Here's how the mathematical operations translate into Python

```python
| operator |    Python      |Example| 
|----------|----------------|-------| 
|     x    |      *         | 3 * 5 | 
|     /    |      /         | 6 / 4 | 
|   mod    |      %         | 5 % 3 | 
|     +    |      +         | 3 + 5 | 
|     -    |      -         | 6 - 4 |
|     =    |     ==         | 6== 4 | 
|     ≠    |     !=         | 6!= 4 | 
|     >    |      >         | 5 > 3 | 
|     <    |      <         | 1 < 4 | 
|     ≤    |     <=         | 6<= 4 |
|     ≥    |     >=         | 6>= 4 |
```

## Control Statements

Control statements in programming regulate the sequence of events. They require validation before executing any action. Control can take on three forms: sequential, selection, and repetitive (iterative).

Sequential control involves executing actions in the order they appear in the program. Selection statements utilize keywords such as `if`, `if-else` (or `elif`), and `else` to evaluate conditions before executing an action. In Python, the third form of control is the repetitive or iterative process, which employs keywords like `for` or `while` to validate conditions before executing actions within their bodies.

It's important to note that the `for` loop is typically used when the number of repetitions is known in advance, while the `while` loop is employed for an indefinite number of repeated actions.

Let's explore their demonstration below.

*Question : Print the first 10 even numbers*

```python

#use for loop to produce number between 0 and 10 included
for number in range(0, 11):
    if number % 2 == 0: #use modulus operate to check if the number is divisible by 2
        print('even number: ', number) #if condition is true print number

#prints: 0, 2, 4, 6, 8, 10
```

The provided code utilizes a for loop to generate numbers ranging from 0 to 10. Notably, the upper bound specified in the range function is 11, not 10. This discrepancy arises because the upper bound in the range function is exclusive; thus, it generates numbers up to, but not including, the specified value.

Within each iteration of the loop, a conditional structure is employed to verify if the current number is divisible by 2. If this condition holds true, the number is printed; otherwise, no action is taken. Therefore, for each iteration facilitated by the for loop, the code evaluates the condition using an if statement before deciding whether to print the number or take no action.

Let's consider two more examples below.

*Question : write a program that will that will request for two numbers from user then compare these two numbers to implement all the logical operations like &gt;, &gt;=, &lt;, &lt;=, ==, and !=. and return the comparison at each loop*

```python
#request input from user 
number1 = int(input('enter the first number: '))
number2 = int(input('enter the second number: '))


#check for equality then print result
if number1 == number2:
        print(f'{number1} and {number2} are equal')
if number1 > number2:
        print(f'{number1} > {number2} ')
if number1 < number2:
        print(f'{number1} < {number2}')
```

```python
#Another example is building a calulator to 
#return the minimum of three given digits

#request user input
number1 = int(input('enter the first number: '))
number2 = int(input('enter the second number: '))
number3 = int(input('enter the third number: '))

#assign the first number as minimum
minimum = number1

#check if the second number is smaller both current number in minimum and third number
if number2 < minimum and number2 < number3: #if true
  minimum = number2 #reassign number in minimum variable

#print out the minimum
print(f'{minimum} is the minimum ')
```

## Data Structure

In Python, variables serve as containers for holding primitive or basic data types, allowing storage of one item at a time. However, when tackling machine learning projects involving extensive datasets, effective organization and management of data become imperative for efficient access and utilization. Python offers built-in data structures like Lists, Tuples, Sets, and Dictionaries, tailored to facilitate the organization and manipulation of data in such projects. Mastery of these data structures is fundamental to the success of machine learning endeavors, emphasizing their pivotal role in optimizing data management processes.

## List

A list is a data structure capable of storing elements of various data types. This implies that a list can hold integers, floats, strings, and other data types simultaneously. Elements within a list maintain their order according to their index values, starting from 0. Similar to arrays in other programming languages like Java, lists in Python serve the purpose of organizing and manipulating collections of data.

![Last Index In Python List - Catalog Library](https://www.askpython.com/wp-content/uploads/2022/03/Indexing-in-lists.png align="left")

Let's consider some examples below.

*Question : Some investment advisors say that it's reasonable to expect a 7% #return over the long term in the stock market. Assumming that you begin with $1000 and leave your money invested, calculate and display how much you'll have after 10, 20, and 30 years #Use the following formula : a = p(1 + r)^n*

```python
number_of_years = [10, 20,30] #store the numerber of years in a list 
principal = 1000 #initialize your first deposit
rate = 0.07 #interest rate 

#since its a repeative action, use loop
for year in number_of_years:
    #use compound formula to get amount for each year
    amount = principal * (1 + rate) ** year
    #print amount for each year
    print(f'Amount in {year} years is: { amount:.2f}')
```

The provided code utilized a list to store the given years, enabling iteration through them prior to their utilization in our calculation of amounts. Within each loop iteration, each number within the index is stored in the variable 'year' and subsequently used in the calculation.

*Question : Implement a Python program that takes the number of rows and columns as input from the user and generates a multiplication table with the specified dimensions. The program should display the multiplication table without including row and column numbers, ensuring that each cell contains the correct product of the corresponding row and column numbers.*

```python
my_list = [] #create an empty list to hold the dimension

row = int(input('enter the number of rows: ')) #prompt user for row dimension
col = int(input('enter the number of columns: ')) #prompt user for col dimension


#a loop to create table based on user dimension
for i in range(row):
  my_list.append([None] * col) # [[None, None, None]]

#loop to populate the table with product of (row + 1) and (col + 1)
for i in range(row):
  for j in range(col):
    #store each product in each index of the list
    my_list[i][j] = (i + 1) * (j + 1) #take the next number after zero since will not be having table of zero


#loop to print each element in the list based on the dimension the user gave
for i in range(row):
  for j in range(col):
    #print each item in the list index and separate it with a tab
    print(my_list[i][j], end = '\t')
  print()
```

This code is a comprehensive example that employs various concepts in list data structure, including:

* Initializing an empty list
    
* Appending elements to a list
    
* Accessing elements from a two-dimensional list
    
* Iterating through a list using the 'range' function
    

In the initial step of the code, the user-provided dimensions are used to create an empty list with the specified row and column dimensions. This is achieved by initializing the list with 'None' references since no values have been added yet.

Next, the code populates the two-dimensional list with the product of each row and column.

Finally, the last code snippet is used to print out each element in the list based on their position in the row and column.

## Dictionary

In a dictionary, one value is designated as the "key" while the other is termed the "value," and they are separated by a colon (":"). Keys in a dictionary can be any immutable (unchangeable) data types such as strings and numbers, and they must be unique; you cannot use the same key for different values. However, different keys can hold the same value since values are accessed using their corresponding keys. Dictionaries are created using curly braces '{}' as opposed to lists, which use square brackets '\[\]'.

![](https://user.oc-static.com/upload/2020/11/23/16061291084126_1C5_1.png align="left")

Let's see this in action below!

Question : Given a grade book containing the names and scores of each student in three, create a calculator #that will be used to evaluate the following

1\. Total score of each student

2\. Average score of each student

3\. Average score of the whole class

```python
"""crating a program that stores/compute and summarize 
the grades of students in an exam"""

# a dictionary with names of each student and their list of 
#scores as values
grade_book = {
             'Ayodele':[23, 67, 77],
             'Kayode': [12, 89, 99],
             'Bolanle':[56, 98, 45],
             'Ridwan':[100,34,69]
            }

#define a global variable that will keep track of total 
#score and number of grades 
total_score = 0
grade_count = 0


#loop through the diction using the key, value pair 
#syntax to access the key and value of the 
#dictionary using items function
for key, value in grade_book.items():
  #to avoid using loop for the value in the 
#dictionary since it's a list itself, we used the in-built 
#sum function to add all the element in the list
  student_score = sum(value)
  #now print the student score
  print(f'total score for {key} = {student_score:.2f}\n')
  #store the student scores in total score variable
  total_score += student_score
  #now print the student's average score
  print(f'average score for {key} = {student_score/len(value):.2f}\n ')
  #store the number of grades in the grade count variable
  grade_count += len(value)

#print the class average 
print(f'class average score = {total_score/grade_count:.2f}\n')
```

The code snippets provided above illustrate the implementation of various fundamental operations within a Python dictionary, including:

* Creating a dictionary with key-value pairs
    
* Iterating through a dictionary
    
* Accessing values in the dictionary.
    

With this, we conclude our course, and it is our hope that you will actively engage with the material by practicing with the provided code snippets. Furthermore, to reinforce your understanding of these concepts, I have prepared a complementary [GitHub repository](https://github.com/aljebraschool/Machine-Learning-Tutorial---2024.git) where you can find additional practice questions along with their respective solutions in case you encounter difficulties.

Feel free to explore, contribute, and share the repository with your peers. Your continuous support is greatly appreciated!

Remember to **Follow, Like, Share, and Subscribe** for future updates. Until next time, happy coding!