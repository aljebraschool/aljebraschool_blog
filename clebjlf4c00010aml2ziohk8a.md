# How to write basic Java applications - 02

*The* [*first episode*](https://aljebraschool.hashnode.dev/how-to-write-basic-java-applications) *of this series introduces us to the basic concept of Java programming and how to create basic Java programs.*

In this episode, I will continue with an explanation of how to build basic Java apps by implementing the concepts of <mark>data types, variables, classes and packages</mark>.

As we have pointed out earlier, every Java program is built from a house called *'class'.* So to illustrate the concepts listed above let's consider this problem statement:

Write an application that takes two numeric inputs from the user, then use these inputs to compute

* Addition of the numbers
    

<mark>Creating classes</mark>

We start by creating our *'house'* which is class Addition and Multiplication respectively and its '*main'* method inside the class.

```java
public class NumberAddition{
public static void main(String[] args){

}
}
```

<mark>Collect user input</mark>

This is a type of application that requires input from the user via the keyboard. To get such input, a special class must be used to read user input. The class named, '*Scanner'* is used to read input from the keyboard. see the code below.

```java
import java.util.Scanner;        //import Scanner class 
public class NumberAddition{
public static void main(String[] args){

/* creates Scanner object with  keyword 'new' and 
     stores it in variable 'input' */
Scanner input = new Scanner(System.in);  

            
    }
}
```

The code above starts with the keyword `import` this is a special word used in making an external package and class usable in your current class. The 'import' declaration must precede every other declaration in java and it must all be in lowercase. The code `java.util.Scanner` imports from the package (which is like a folder or directory where similar classes are stored ) `java.util`, the class `Scanner`. This made it usable in our current class.

To use a `nonstatic` class in a `static` method like 'main', a representation of such class called <mark>Object of the class </mark> has to be created. This was done above using the keyword `new`. `system.in` is a standard input object which enables java applications to read information from the user via the keyboard. The left-hand side of the assignment operator `=` is then stored in the variable (input), which is a variable that references(points to) the Scanner class memory location. So this means that I can access the class Scanner via its pointer called 'input'.

<mark>Prompt the user for input</mark>

The next line of our program is to request input from the user and then process it! This is done below using this syntax

```java
//A program that adds two numeric values given by the user
import java.util.Scanner;        //import Scanner class 
public class NumberAddition{
public static void main(String[] args){

Scanner input = new Scanner(System.in);  
/* creates Scanner object with  keyword 'new' and 
     stores it in variable 'input' */

//prompt user for numeric input
System.out.print("please enter the first numeric value")      
int myFirstNumber = input.nextInt();    //reads the first number

System.out.print("please enter the second numeric value")      
int mySecondNumber = input.nextInt();    //reads the second number
      
    }
}
```

The program above prints to the screen the prompt message `please enter the first/second numeric value` respectively, using the `System.out.print` method which was explained in the [previous episode](https://aljebraschool.hashnode.dev/how-to-write-basic-java-application).

<mark>Variable declaration</mark>

For every program that takes input from the user, such input has to be remembered by the computer before being used for computation. An input can be stored in '<mark>variable</mark>'. A variable can be compared with a container box which can hold only one item at a time. It's also similar to the concept of variables in mathematics, for example;

`if x = 3:` we can say that 'x' is a variable that stores the number '3'. The names 'myFirstNumber' and 'mySecondNumber' are the two variables used in this program. Based on our previous episode, the standard rule for choosing a variable name is that

* it can start with any letter or symbol but not digits (numbers)
    
* it must be written in camel case like this 'myFirstName' - every word is capitalized except the first word.
    
* it must be descriptive - it must describe its usage. As we have above, 'myFirstNumber' will store the first input from the user.
    

<mark>Data types</mark>

Java is a statistically typed programming language, that is, there must be clear and detailed declarations of the type of data to be stored before storing such data. Data in Java can be categorized as primitive (int, float, double, char, boolean) and referenced (class, array, String).

Using primitive data type we can store the following;

* `int`: it is a short form of integer, and it can be used to store positive or negative whole numbers
    
* `float/double:` any of these can be used to store positive or negative decimal numbers but double can take longer precisions(decimal) than float.
    
* `boolean`: it is used to store the binary value of '1' and '0' that is, the keywords true or false respectively.
    
* `char:` it is used to store a single capital or small letter within a single inverted comma; such as name = 'a'.
    

*<mark>The referenced data types will be covered in our successive series.</mark>*

The right-hand-side `input.nextInt()` access the `nextInt() method` in class Scanner, using its reference point (input) which is the object Scanner class. This method `(nextInt()),` reads the user input as an integer (int) and stores whatever it reads in the first and second variables respectively. Don't forget that the data type for 'myFirstNumber' and 'mySecondNumber' variables are integers so we stored each returned type as an integer(int) value.

<mark>Compute and display your results</mark>

The last stage of this program is to evaluate your result and display it back to the user. This is implemented below.

```java
//A program that adds two numeric values given by the user
import java.util.Scanner;        //import Scanner class 
public class NumberAddition{
public static void main(String[] args){

Scanner input = new Scanner(System.in);  
/* creates Scanner object with  keyword 'new' and 
     stores it in variable 'input' */

//prompt user for numeric input
System.out.print("please enter the first numeric value")      
int myFirstNumber = input.nextInt();    //reads the first number

System.out.print("please enter the second numeric value")      
int mySecondNumber = input.nextInt();    //reads the second number
    
//evaluating your result
int sumOfNumbers = myFirstNumber + mySecondNumber;

//display the result
System.out.printf("The sum of the numbers entered is: %d", sumOfNumbers);  
    }
}
```

The code above computes the sum of the first integer and the second integer stored in 'myFirstNumber' and 'mySecondNumber' respectively before storing its result in the variable 'sumOfNumbers'.

The code `System.out.printf("The sum of the numbers entered is: %d", sumOfNumbers);` used the formatted string with ''%d'' as the placeholder for 'decimal integer' to store the returned integer result from variable 'sumOfNumbers'. This program can be implemented for every basic operation in mathematics.

Below is the equivalent of mathematics operations in Java

```java
| operator |Java equivalent |Example| 
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

The operators listed have the same interpretations as we use them in mathematics but they are just written differently in Java.

Let's call it a day for now and continue in my next episode. kindly implement the same problem statement using

* subtraction
    
* multiplication
    
* division
    

I'll provide solutions to this question on my GitHub repo if requests are made. Contact me for corrections and advice via my email and don't forget to subscribe to my newsletter for quick updates on my next episodes.