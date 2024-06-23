# [Java Programming Masterclass updated to Java 17](https://www.udemy.com/course-dashboard-redirect/?course_id=533682)

# Table of contents:

[Section 2: Programming tools setup](#section-2:-programming-tools-setup)


* Comments are done in java with `//` to ignore until the EOL.

# Section 2: Programming tools setup

* Installation of OpenJDK version 17 and JShell, confirmation with this command shell

```shell
$java -version
openjdk version "11.0.19" 2023-04-18 LTS
OpenJDK Runtime Environment Corretto-11.0.19.7.1 (build 11.0.19+7-LTS)
OpenJDK 64-Bit Server VM Corretto-11.0.19.7.1 (build 11.0.19+7-LTS, mixed mode)
```

* Confirming installation and intro JShell: JShell is an REPL interactive program. JShell documentation is in [Introduction to JShell](https://docs.oracle.com/en/java/javase/17/jshell/introduction-jshell.html)

```java
jshell> /help intro # a short help
jshell> /help # The whole help

# List all the code include in the environment
# At the start-up includes the initial imported modules by JShell
# They're pretty similar to Python imports
	
jshell> /list -all

# This explicitely includes only the start-up modules imported
jshell> /list -start
```

* A code writing can be canceled with Ctrl+C, and exit of jshell with `/exit` or Ctrl-Z in Linux.
* Declared variables can be seen with `/var`
* Executing multiple lines of code can be done enclosing it in curly braces *{ }*, and it will behave like the normal run of the program (doesn't show variable assignation)

# Section 3: First Steps

* Hello World: String literals must be enclosed in " " and not in ' ' , the second is used only for character. `System.out.print("Hello World!")` in jshell and with that is sufficient there, not wrapping everything in the weird
* Variables: First, don't use [Java Language Keywords](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html) for variable names. Only the initial declaration statement need a data type specified, the other variable assignments don't need it, **jshell** admits multiple type declarations to a variable *but the Java program block don't, will throw an error*. Expressions with operators (mathematical - logical) can be used in the variable assignment.
* Starting with expressions: nothing different than usual

## Primitive types
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

If the ranges are not respected an overflow / underflow happens.

* Wrapper classes for each primitive: **int is the default the Java compiler assumes**.

|Primitive|Wrapper Class|
|---------|-------------|
|byte	|Byte|
|short	|Short|
|char	|**Character**|
|int	|**Integer**|
|long	|Long|
|float	|Float|
|double	|Double|
|boolean	|Boolean|

* Also this a valid expression `int myvalue = 2_375_235;` and easier to read.

* **How to find which methods have a (wrapper) Class in Java? Can't be done interactively like Python.** Maybe this one [Retrieving class objects](https://docs.oracle.com/javase/tutorial/reflect/class/classNew.html)
* Cast of variables is done like this  `byte b_value2 = (byte) (b_value1 / 2)` is necessary because Java doesn't know if the variable can really fit in the byte type with only the variable name
* double is the default floating-type number, isn't woth the memory to use anything else.
* BigDecimal is used for precise calculations, instead of the other floating points.
* For the **char** type, this is the representation in unicode `'D' = '\u0044' = 68` The last one is because the way Java store the char type.
	* If you do `'A' + 'B' = 131` because the way Java store *char*. You can force the concatenation with `"" + 'A' + 'B' = "AB"`
* **boolean** are *true* and *false*
* `String myString = "This is a string";`  the string can't be altered after is created, is immutable. So appending to a strin is *inefficient*.
* Formal definition of *expression* (variables and operators together)
* Remainder or modulus operator is `%`
* Shorthand operators, all of these are equivalent, and can be done also with * and / operators:
```java
result = result + 1;
result++;
result+=1;
```
* The compound operator cast (coerce) to the type of the first assignation so `int result = 10; result -= 5.5;` is equal to `4` because it casts to type *int*.
* So if this is done with `double result = 10; result -= 5.5;` this is really equal to `4.5`
