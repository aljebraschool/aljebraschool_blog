---
title: "Introduction to classes, Objects, Methods and Strings"
datePublished: Sun Mar 05 2023 16:03:43 GMT+0000 (Coordinated Universal Time)
cuid: clevl2603000109mcbpwe2lkr
slug: introduction-to-classes-objects-methods-and-strings
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/cckf4TsHAuw/upload/4bfa8a37e438bba5c0e6e0f5fa55defa.jpeg
tags: programming-blogs, java, classes, methods, java-beginner

---

### **Introduction**

In the [first part](https://aljebraschool.hashnode.dev/how-to-write-basic-java-applications) of this write-up, the concept of classes was introduced, and in this series, I will delve deeper into this topic by explaining the various components that make up a class. Java is an object-oriented programming (OOP) language, which enables us to represent real-world objects as 'objects' belonging to a specific class. For example, a Ford car can be represented as an object that belongs to the "car" class, which is made up of various components that enable it to function properly. One of these components is its method, which is a function that performs a specific task behind the scenes. To make a car move, the gas pedal must be pressed, which sends a message to the car to call a method that initiates the movement. The methods used in implementing the tasks of a car class will differ from those used in a house class because they serve different purposes.

### **Implementing Components of a Class**

To illustrate the implementation of the key components of a class, let's examine the following scenario.

Develop a program that allows users to access information on a bookshelf. This program will define a "book" class, which will contain methods for naming the book(s) on the shelf, retrieving the book name, and displaying the message within the book. Additionally, a driver class will be created to implement the functionalities of this book class.

<mark>Create the book class</mark>

Let's call our bookshelf class 'BookShelf'.

```java
/* A bookshelf class without main method used to store and retrieve a book information
*/
public class BookShelf{

} 
```

<mark>Store a book in the BookShelf</mark>

Once the shelf has been created, we can proceed to store book items on it. However, to facilitate easy retrieval of the books, each book must be labelled. This can be accomplished by defining a variable of the class to store the books. This type of variable is known as a <mark>'field'</mark>, <mark>'instance variable',</mark> or '<mark>class variable</mark>' since it is declared only in the class and not in any of its members (methods). Typically, these variables are assigned a '<mark>private</mark>' access modifier to prevent unauthorized access from external sources, as they can only be accessed and modified within the class. Below is an example code snippet for implementing this concept.

```java
/* A bookshelf class without main method used to store and retrieve a book information
*/
public class BookShelf{
//declare an instance variabe to store a book name
private String bookName;
} 
```

<mark>Creating the Set Method</mark>

The next component required for this class is the 'set method' which will be utilized to assign a name to the book before storing it in the bookshelf class. The code for this method is shown below.

```java
/* A bookshelf class without main method used to store and retrieve a book information
*/
public class BookShelf{
//declare an instance variabe to store a book name
private String bookName;

//creat a set method to set the book name
public void setBookName(String nameOfBook){

bookName = nameOfBook;
}
} 
```

The 'setBookName' method created above has a 'public' access modifier since we will need to access this method from outside the class to assign a value to the class variable (bookName), which is a private variable of the class. We achieve this by calling the method 'setBookName' with the required value, which is referred to as an <mark>'argument'</mark>. In the method declaration above, we included 'String nameOfBook' in parentheses. This 'String nameOfBook' is a <mark>'parameter'</mark> that is required for the method to carry out its function of setting the book name. Without it, the method will not be able to perform its task, similar to how a driver presses the gas pedal to accelerate their car on the highway. The gas pedal is the method being called, while the depth of the pedal, which is declared in the parameter list of the method declaration, determines how fast the car accelerates. Additionally, you may notice that the word <mark>'void'</mark> appears after the 'public' access modifier. This specifies the type of data that will be returned when the method completes its task. In this scenario, since its data type is labelled as <mark>'void'</mark>, the method will not return anything to its caller.

<mark>Creating the Get Method</mark>

Once the book has been labeled with a name using the method described above, we need to create a method that can be used to retrieve its value when necessary. The following code implements this method.

```java
/* A bookshelf class without main method used to store and retrieve a book information
*/
public class BookShelf{
//declare an instance variabe to store a book name
private String bookName;

//creat a set method to set the book name
public void setBookName(String nameOfBook){

bookName = nameOfBook;
}

//method used to access the class bookName variable
public String getBookName(){
return bookName;
}
} 
```

In order to retrieve the name of the book that has been stored on the shelf, a separate method needs to be created to perform this task. **<mark>It is not advisable for a single method to carry out multiple actions at once</mark>**. The 'getBookName' method above is designed to return a 'String' data type since its only purpose is to provide the name of the book that has already been stored in the 'bookName' class variable back to its caller.

<mark>Retrieve the Book Contents</mark>

The problem statement requires the implementation of a method to retrieve the information that has been stored in a book on the bookshelf. Let's now see how this can be achieved.

```java
/* A bookshelf class without main method used to store and retrieve a book information
*/
public class BookShelf{
//declare an instance variabe to store a book name
private String bookName;

//creat a set method to set the book name
public void setBookName(String nameOfBook){

bookName = nameOfBook;
}

//method used to access the class bookName variable
public String getBookName(){
return bookName;
}

//creating the book contents 
public void getBookContent(){
System.out.print("This is Java Programming language\nIt is an object programming language used in a wide range of applications like\nAndroid apps development\nDesktop Applications\nWeb Application\nEnterprise Applications"
}
} 
```

The structure of this method is the same as the 'setBookName' method discussed earlier, except that it has empty parentheses. This is because this method does not require any additional information to perform its task when it is called.

### **Now let's create the driver's class**

We are aware that the 'bookShelf' class we created earlier lacks the 'main' method, which is essential for the Java virtual machine (JVM) to execute every Java program. Therefore, in order to execute the functionality of this class, we need to create another class in the same directory(folder) as the previous class, with the 'main' method. This new class will be named 'BookShelfTest'.

```java
//A driver class to use the functionality of the bookShelf class

public class BookShelfTest {

//main method
public static void main(String[] args ){

}
}
```

<mark>Create a 'BookShelf' class Object</mark>

In order to access the 'BookShelf' class from another class, we will have to create its 'blueprint' called its '<mark>object'</mark>. Let's see that below.

```java
//A driver class to use the functionality of the bookShelf class

public class BookShelfTest {

//main method
public static void main(String[] args ){

BookShelf myBookShelf = new BookShelf();    //object declaration
}
}
```

The object declaration above utilizes the <mark>'new'</mark> keyword to instantiate an object of the 'BookShelf' class with an empty parenthesis indicating a default constructor. The resulting object is then assigned to the 'myBookShelf' variable which points to the 'BookShelf' class. Through the 'myBookShelf' variable, the public members of the 'BookShelf' class can be accessed and used to manipulate the private members.

<mark>List a new Book on the Shelf</mark>

In order to add a new book to the bookshelf, we need to give it a name by requesting the preferred name from the user and setting this name in the class variable 'bookName' using the 'setBookName' method. To receive input from the user using the keyboard, we need to import the 'Scanner' class from the 'java.util' package. The 'Scanner' class is used to read values typed in from the keyboard, as explained in the [second series](https://aljebraschool.hashnode.dev/how-to-write-basic-java-applications-02). The implementation is shown below.

```java
//A driver class to use the functionality of the bookShelf class

import java.util.Scanner;        //import Scanner class for input

public class BookShelfTest {

//main method
public static void main(String[] args ){

BookShelf myBookShelf = new BookShelf();    //object declaration

//create Scanner class object to access its public method
Scanner input = new Scanner(System.in);

//Then ask user to set the name of the book on the shelf
System.out.println("Kindly enter the name of the book you want");

//use scanner method 'nextLine' to read user's input then store it in the variable 'bookName'
String bookName = input.nextLine();    

}
}
```

<mark>Set the Book's Name and Get its Contents</mark>

Finally, we need to call the methods in the 'BookShelf' class to set the input name and retrieve the book's contents. The code for this is shown below.

```java
//A driver class to use the functionality of the bookShelf class

import java.util.Scanner;        //import Scanner class for input

public class BookShelfTest {

//main method
public static void main(String[] args ){

BookShelf myBookShelf = new BookShelf();    //object declaration

//create Scanner class object to access its public method
Scanner input = new Scanner(System.in);

//Then ask user to set the name of the book on the shelf
System.out.println("Kindly enter the name of the book you want");

//use scanner method 'nextLine' to read user's input then store it in the variable 'bookName'
String bookName = input.nextLine();    

//set the name of the book
myBookShelf.setBookName(bookName);

//display book's content
myBookShelf.getBookContent();
}
}
```

Each method mentioned above utilizes the dot (.) operator with the object of the 'BookShelf' class (myBookShelf) to access its public methods. The set method assigns a value to the class variable, while the get method retrieves its contents.

**<mark>Test Arena!!!</mark>**

Create a program to calculate Body Mass Index (BMI) that prompts the user to input their weight in pounds and height in inches. Then, using the given formula below, calculate and display the user's BMI:

BMI = (weightInPounds / (heightInInches *height in inches))* 703

* underweight: less than 18.5
    
* normal: between 18.5 and 24.9
    
* overweight: between 25 and 29.9
    
* obese: 30 or greater
    

<mark>Hint:</mark> Please bear in mind that conditional statements in Java should be used to implement the different options mentioned above.

In case you need the solutions to this question, they will be available on my GitHub repository upon request. You can contact me for feedback, suggestions, or clarifications through my email address. Also, remember to like, share, and subscribe to my newsletter for timely updates on my upcoming episodes.