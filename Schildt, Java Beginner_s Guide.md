# Table of contents

[Chapter 1 Java Fundamentals](#chapter-1-java-fundamentals)

[Chapter 2 Introducing Data Types and Operators](#chapter-2-introducing-data-types-and-operators)

[Additional references](#additional-references)

# Chapter 1 Java Fundamentals

Java started like language to be embedded in electronic devices (LOL). This is because compilers need to be specific to a CPU. The problems of portability were worsen by the advent of the internet, and Java was the only one with a solution, mainly with the creation of *applet*. An *applet* is a program run on the client's side.

Java syntax was created to imitate C and C++. Microsoft created C# to be similar to Java. That the java code is compiled to a **bytecode** is what allows portability: the *J*ava *R*untime *E*nvironment (JRE) have inside a *J*ava *V*irtual *M*achine (JVM) that is the one that converts the bytecode to a compiled code to an specific machine. Configuration in the JVM also make it secure. But that was removed a
long time ago, now instead of *applets* there is *jlink*.

The semicolon is important because is always signal the end of the statement, Java never assumes the statement has ended with the end of the line, like in R.

There is a list a **Java keywords**, pretty important because there are no functions like R/Python. This is before the **Identifiers in Java**.
Identifiers can start with \$, alphabetc characters and '\_' , are case-sensitive and numbers can be used on the middle of the identifier.

Java has standard classes, with the *println* functionality, for example. There are I/0, string handling, networking, graphics, GUI.

## First Java program

The important thing is, the comments like SQL *\* \** and // , that everything needs to be wrapped in a class (**Example** in this case). The **main** method is preceded by a lot of jargon (describing a few things for the OOP type of programming) *public* because it needs to be accesed by other parts of the code *static* to be created before an object of the class is created, *void* because the class should return any value. The things in parenthesis are arguments *()datatype argname\[\])*.

The part of the code that really do something is *System.out.println("Java drives the Web.");* only the last part before the parenthesis is the method(function) that does the work and all the previous words are the classes where *println* is located and where to pick data, in this case are always loaded in Java at the start.

```java
/*
  This is a simple Java program.

  Call this file Example.java.

*/
class Example {
    // A java program begins with a call to main().
    public static void main(String args[]) {
      System.out.println("Java drives the Web.");
    }
}
```

## Second Java program

This programs introduces **variables**, they need to be declared with a type before being used. In this case *int* type in both variables before being assigned later.

```java
  /*
  This demonstrates a variable.

  Call this file Example2.java
  */
    class Example2 {
  public static void main(String args[]){
      int myVar1;   // this declares a variable
      int myVar2;   // this declares another variable

      myVar1 = 1024; // this assigns 1024 to myCar1

      System.out.println("myVar1 contains " + myVar1);

      myVar2 = myVar1 / 2;

      System.out.print("myVar2 contains myVar1 / 2: "); // doesn't create a new line
      System.out.println(myVar2);
  }
    }
```

## Third Java program

This 3rd program shows the difference in operations between *int* and *double* types, basically is expected that *int* can't do fractions like the last one.

```java
  /*
  This demonstrates a variable.program illustrates he differences
  between int and double

  Call this file Example3.java
*/
 class Example3 {
    public static void main(String args[]){
  int v;    // this declares an int variable
  double x; // this declares a floating-point variable

  v = 10;
  x = 10.0;

  System.out.println("Original value of v: " + v);
  System.out.println("Original value of x: " + x);
  System.out.println();

  // now, divide both by 4
  v = v / 4;
  x = x / 4;

  System.out.println("Original value of v: " + v);
  System.out.println("Original value of x: " + x);
    }
}
```

## First use of variables

This is a more useful program but not really different than others.

```java
 /*
 Try this 1-1

 This program converts gallons to liters.

 Call this program GalToLit.java.
 */

 /**

 @author edin
 */
 class GalToLit {

   /**
    * @param args the command line arguments
    */
   public static void main(String args[]) {
      double gallons; // holds the number of gallons
      double liters; // holds conversion to liters

      gallons = 10; // start with 10 gallons

      liters = gallons * 3.7854; // convert to liters

      System.out.println(gallons + " gallons is " + liters + " liters.");
   }
}
```

## if statement

This code is a demostration of an **if(condition) statement;**. I don't really know if the **statement** can span several other statements or, if they're allowed, if they need to be grouped in some way.

```java
  /*
 Demonstrate the if.

 Call this file IfDemo.java.
 */

  /**
 *
 * @author edin
 */
  class IfDemo {
    public static void main(String args[]) {
  int a, b, c;

  a = 2;
  b = 3;

  if (a < b) System.out.println("a is less than b");
  // this won't display anything
  if (a == b) System.out.println("you won't see this");

  System.out.println();

  c = a - b; // c contains -1

  System.out.println("c contains -1");
  if(c >= 0) System.out.println("c is non-negative");
  if(c < 0) System.out.println("c is negative");

  System.out.println();

  c = b - a; // c now contains -1

  System.out.println("c contains 1");
  if(c >= 0) System.out.println("c is non-negative");
  if(c < 0) System.out.println("c is negative");
    }
}
```

## for statement and code block

This an example of a **for(initialization; condition; iteration) statement;** same doubts as the previous if statement and is mentioned that this is the simplest form.

```java
/*
 Demonstrate the for loop

Call this file ForDemo.java
 */

/**
 *
 * @author edin
 */
class ForDemo {

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
  int count;

  for(count = 0; count < 5; count++)
      System.out.println("This is count: " + count);

  System.out.println("Done!");

    }
}
```

This program answer one of my questions above, if several statements are needed after an **if** or **for** statements, they need to be surrounded by **{ }**.

```java
  /*
 Demonstrate a block of code.

 Call this file BlockDemo.java
 */

/**
 *
 * @author edin
 */
class BlockDemo {

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
  double i, j, d;

  i = 5;
  j = 10;

  // the target of this if is a block
  if(i != 0) {
      System.out.println("i does not equal zero");
      d = j / i;
      System.out.println("j / i is " + d);                    
  }
    }
}
```

A better version of GalToLitTable.

```java
/*
 Try this 1-2

 This program displays a conversion
 table of gallons to liters.

 Call this program GalToLitTable.java.
 */

 /**

 @author edin
 */
 class GalToLitTable {

   public static void main(String args[]) {
       double gallons, liters;
       int counter;

       counter = 0; // initialize counter for loop

       for(gallons = 1; gallons <= 100; gallons++){
	   liters = gallons * 3.7854;
           System.out.println(gallons + " gallons is " +
			      liters + " liters.");
	   counter++;

	   // every 10th line, print a blank line
	   if(counter == 10) {
	       System.out.println();
	       counter = 0;
	   };
       }

   }
```

+ And then there is a list of [Java Language Keywords](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html), this link is the last versiom Oracle.
+ [The Essential Java Classes](https://docs.oracle.com/javase/tutorial/essential/index.html) is a place to review.
+ The **Chapter 1 Self-test** looks boring.

### [Return to table of contents](#table-of-contents)

# Chapter 2 Introducing Data Types and Operators

Java is a strongly typed language. Below there is the table with the
primitive data types.

| Primitive | Wrapper Class | Meaning                         |
|-----------|---------------|---------------------------------|
| byte      | Byte          | 8-bit integer                   |
| short     | Short         | Short integer                   |
| char      | **Character** | Character                       |
| int       | **Integer**   | Integer number                  |
| long      | Long          | Long integer                    |
| float     | Float         | Single-precision floating point |
| double    | Double        | Double-precision floating point |
| boolean   | Boolean       | Represents true/false values    |

## Showcase of numeric data types

This is the range of primitive types:

* Whole number: byte, short, int, long
* Real number: float, double
* Single character: char
* Boolean value: boolean
* Range of whole/real number data types with methods *.MIN_VALUE* and *.MAX_VALUE*
	* Byte	-128 to 127
	* Short -32768 to 32767
	* Integer -2147483648 to 2147483647
	* Long -9223372036854775808 to 9223372036854775807
	* Float 1.4E-45 to 3.4028235E38
	* Double 4.9E-324 to 1.7976931348623157E308

This program showcase different data types.

```java
  /*
 Compute the number of cubic inches
 in 1 cubic mile
 */

 /*

  @author edin
 */
class Inches {

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
  long ci;
  long im;

  im = 5280 * 12;
  ci = im * im * im;

  System.out.println("There are " + ci +
      " cubic inches in cubic mile.");
    }
}
```

This uses the [Math class in Java 17](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Math.html). Important to note that this is inside the Module: java.base, Package java.lang. Like several levels deep in the standard class.

```java
  /*
 Use the Pythagorean theorem to 
 find the lenght of the hypotenuse
 given the lenghts of the two opposing sides.
 */

  /*

  @author edin
 */
  class Hypot {

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
  double x, y, z;

  x = 3;
  y = 4;

  z = Math.sqrt(x*x + y*y);

  System.out.println("Hypotenuse is " + z);             

    }
}
```

Characters data types are the ones that work with single quotes `char ch; ch = 'X'`. This data can be printer like the string, 


``` java
/*
 Character variables can be handled like integers.
 */

/**
 *
 * @author edin
 */
class CharArithDemo {
    public static void main(String args[]) {
        char ch;
        
        ch = 'X';
        System.out.println("ch contains " + ch);
        
        ch++; // increment ch
        System.out.println("ch is now " + ch);
        
        ch = 90; // give ch an integer value, equal to char "Z"
        System.out.println("ch is now " + ch);
    }
}
```


The boolean values returned by Java are in lower-case: `true` and `false`.

```java
// Demonstrate boolean values.
class BoolDemo {
    public static void main(String args[]) {
        boolean b;
        
        b = false;
        System.out.println("b is " + b);
        b = true;
        System.out.println("b is " + b);
        
        // a boolean value can control the if statement
        if(b) System.out.println("This is executed.");
        
        b = false;
        if(b) System.out.println("This is not executed.");
        
        // outcome of a relational operator is a boolean value
        // +  has precedence over >, parenthesis are necessary
        System.out.println("10 > 9 is " + (10 > 9)); 
    }
}
```

This is a quick project to do a calculation with of speed of sound.

```java
/*
 Try This 2-1
Compute the distance to a lightning 
strike whose sound takes 7.2 seconds to reach you
 */

class Sound {
    public static void main(String args[]) {
        double dist;
        
        dist = 7.2 * 1100;
        
        System.out.println("The lightning is " + dist +
                " feet away.");
    }
}
```

*Literals are fixed values that are represented in their human-readable form*: constants.

```java
int myvalue = 2_375_235; // the underscores are removed in the compilation
'D' = '\u0044' = 68; // different way to represent unicode
hex = 0xFF; // 255 in decimal
oct = 011; // 9 in decimal
```

There are character escape sequences for printing:

| Escape Sequence | Description                 |
|-----------------|-----------------------------|
| \'              | Single quote                |
| \"              | Double quote                |
| \\              | Backslash                   |
| \r              | Carriage return             |
| \n              | New line                    |
| \f              | Form Feed                   |
| \t              | Horizontal tab              |
| \b              | Backspace                   |
| \ddd            | Octal constant 'ddd'        |
| \uxxxx          | Hexadecimal constant 'xxxx' |

This is an example, of having fun with escape sequences.

```java
/*
 Demonstrate escape sequences in strings
 */

class StrDemo {
    public static void main(String args[]) {
        System.out.println("First line\nSecond line");
        System.out.println("A\tB\tC");
        System.out.println("D\tE\tF");
    }
}
```

And this is the result:

```shell
$ java StrDemo
First line
Second line
A	B	C
D	E	F
```

Java has **strict type checking**, and needs to be provided an initial value prior to using it: `int a, b = 8, c = 19, d;` here b and c are initialized.

Now, *dynamic initialization* is like assigning a variable with extra steps:

```java
/*
 Demonstrate dynamic initialization
 */

class DynInit {
    public static void main(String args[]) {
        double radius = 4, height = 5;
        
        // dynamically initialize volume
        
        double volume = 3.1416 * radius * radius * height;
        
        System.out.println("Volume is " + volume);
    }
}

```

The scope is inside a block of code: *{...}*. The visibility and lifetime of objects are determined by the method body (*block of code*) where they were created, and that allows the famous **encapsulation**.

```java
/*
Demonstrate block scope.
 */

class ScopeDemo {
    public static void main(String args[]) {
        int x; // known to all code within main
        
        x = 10;
        if(x == 10) { //start new scope
            
            int y = 20; // known only to this block
            
            // x and y both known here.
            
            System.out.println("x and y: " + x + " " + y);
            
            x = y * 2;
        }
        //y = 100; // Error! y not known here
        
        // x is still known here.
        System.out.println("x is " + x);
    }
}
```



### [Return to table of contents](#table-of-contents)


## Additional references

### [Java Platform, Standard Edition & Java Development Kit Version 17 API Specification](https://docs.oracle.com/en/java/javase/17/docs/api/index.html)

A list of interest modules to check:

+ [java.base](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/module-summary.html)
+ [java.logging](https://docs.oracle.com/en/java/javase/17/docs/api/java.logging/module-summary.html)
+ [java.desktop](https://docs.oracle.com/en/java/javase/17/docs/api/java.desktop/module-summary.html)
+ [java.sql](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/module-summary.html)
+ [jdk.javadoc](https://docs.oracle.com/en/java/javase/17/docs/api/jdk.javadoc/module-summary.html)
+ [jdk.jshell](https://docs.oracle.com/en/java/javase/17/docs/api/jdk.jshell/module-summary.html)
+ [](https://docs.oracle.com/en/java/javase/17/docs/api/jdk.zipfs/module-summary.html)
