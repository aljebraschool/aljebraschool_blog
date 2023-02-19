# How to write basic Java application

<mark>This is the first article in the series of write-ups that will be used to teach us java programming from the beginner level to the intermediate level of proficiency</mark>

# Introduction

Communication is an essential tool used by humans to exchange ideas and skills which has helped in their advancement since the beginning of time. Also, the creation of communication patterns between humans and their natural endowment has helped them to create sophisticated tools like computers.

Humans communicate with a computer using programming languages which can be understood by the computer and the trained speaker called a programmer. They communicate with the computer using machine language, assembler language or high-level language.

Out of the three means of communication listed above, high-level language is the most efficient as this is very close to our natural language like English. Java is an example of a high-level language which can be used to model everything in nature. It is an object-oriented language (OOL), that is, it represents every concept in nature using "Object".

Java is undoubtedly one of the most populous and widely used programming languages for more than 3 decades. Its uniqueness of portability, platform-independent, vast libraries and its ever-growing community support made it the irresistible language of choice by programmers. It can be used to develop mobile, web and enterprise applications.

## Components of Java Program

Although writing programs in Java will give you the needed solid background in Object-oriented programming (OOP) and this must be done following the standard guidelines to have efficient and optimal Java programs.

**In this article, I will break down the needed components in your first Java program and work you through the steps following the standard guidelines with an emphasis on clarity using code snippets with examples.**

<mark>Declaring Java class</mark>

Java is an object-oriented language, that is, it treats every concept as something inside a container (class) and this container is where all Java codes "live". A valid java class must begin with the access modifier (public, private or protected), the "class" keyword all in lowercase then the class name which can begin with anything except a digit. That is, "5button" is not allowed because it starts with the digit "5".

`public class JavaClass`

*public - access modifier*

*class - reserved or keyword*

*JavaClass - class name (written in camel case)*

<mark>Class enclosing braces</mark> `{}`

The enclosing braces (`{}`) is the wrapper housing the class declaration. It signifies the beginning and the end of a class declaration. Without it, a class is not properly defined.

`public class JavaClass{}`

<mark>Declaration of "main" method</mark>

After defining a class with a unique name, there is a need for you to start giving instructions to the computer. Java virtual machine (JVM) which interprets Java code in computer language only start interpreting within the "main" method of the Java class. So there's a need to create such a method.

`public class JavaClass{`

`public static void main(String[] args){`

`}`

`}`

It follows the pattern of the class declaration but has some extra keywords.

*A "static" keyword shows that the method is a property of the class, this is, it can be used without creating an "instance(Object)" of such class.*

*The "void" keyword means the type of data to be returned when the method is done with its work. There are different data types; int, float, String and so on. In this case, "void" will return nothing to its caller.*

"main" is the exact name of the class. This must be spelt exactly as "main" all in lowercase.

Every method must have enclosed brackets `()` to take information used in performing their task. Inside these brackets we have;

`String[] args` : This is a declaration of a "String" array with the name "args" of course you can change the name but it's conventional to use "args".

<mark>Printing your first statement in Java</mark>

After setting up the main method, the Java Virtual Machine (JVM) is now ready to start interpreting your Java programs.

To print strings of statements in Java, we use the following keyword:

`public class JavaClass{`

`public static void main(String[] args){`

`System.out.print("This is first java application");`

`System.out.println("This is aljebra school");`

`System.out.printf("This is my first java course");`

`}`

`}`

`System.out.print("This is first java application");`

This "print" statement will output the string as it is: `This is first java application` without the quotation mark ("") and also keep the cursor on the same line.

`System.out.println("This is aljebra school");`

This print statement will output the string as it is: `This is aljebra school` without the quotation mark ("") but takes the cursor on the next line.

`System.out.printf("This is my first java course");`

This is a formatted string, it will also print the string as it is: `This is my first java course` but it is specifically used to format and print complex strings which cannot be printed with the previous two mentioned above.

Notice that every printed statement ends with a semi-colon (;) which signifies a full stop just like normal English. Without it, your code will not run.

We have come to the end of the first series and we hope to continue exploring how to develop Java applications in our subsequent writings. Kindly give a thumbs-up and follow me for more explicit content on programming.