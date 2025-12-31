# C#-ProgressTracker

> [!CAUTION]
>
> Following the **C# Player's Guide of RB**, With the **Solutions Appended**
>
> Official Solutions: https://csharpplayersguide.com/solutions/

## PART 1: Basics

### **The C# Programming Language**

​	C# is a general-purpose programming language. 

​	C# runs on .NET.



#### **• What is C#?**

​	(1) C# is a general-purpose programming language.

​	(2) C# is a statically typed, garbage collected, object- oriented programming language with imperative, functional, and event-driven aspects. It also allows for dynamic typing and unmanaged code in small doses when needed.



####  **• What is .NET?**

​	(1) .NET is often called a framework or platform, but .NET is the entire ecosystem surrounding C# programs and the programmers that use it. For example, .NET includes a **runtime**, which is the environment your C# program runs within.

​	(2) .NET also includes a pile of code that you can use in your program directly. This collection is called the **Base Class Library (BCL)**.	

​	(3) .NET includes a broad set of tools called a **Software Development Kit (SDK)** that makes programming life easier.

------

### **Hello World: Your first Program**

####  **• Creating a new project**

​	C# **source code** files use the **.cs extension**. A project’s **configuration** uses the **.csproj** extension. Because these are both simple text files, we could handcraft them ourselves if needed.

> [!TIP]
>
> **Place solution and project in the same directory**. For small projects, I recommend checking this box. Larger programs (solutions) may be formed from many projects. For those, putting projects in their own directory (folder) under a solution directory makes sense. But for small programs with a single project, it is simpler just to put everything in a single folder.



#### • **Strings and Literals**

```c#
Console.WriteLine("Hello, World!");
```

​	"Hello, World!" This is called a **literal**, or specifically, a **string literal**. A **literal** is a chunk of code that defines some **specific value**, precisely as written. Any text in double quotes will be a string literal. 



#### **• Hierarchical Organization**

​	Between Console and WriteLine, there is a **period (.) character**. This is called the **member access operator** or the **dot operator**. Code elements like Console and WriteLine are organized hierarchically.

​	The compiler must determine which code element an identifier refers to. This process is called **name binding.** It really is as simple as, “When the code says, WriteLine, what exactly is that referring to?”



#### **• Classes and Methods**

​	Specifically, **Console** is a class, while **WriteLine** is a method. 

​	For now, think of classes as entities that solve a single problem or perform a specific job or role. It is like a person on a team.

​	**Classes** are primarily composed of **two** things: (1) the data they need to do their job and (2) tasks they can perform.

​	A **method** is a named, reusable block of code that you can request to run. 



#### **• Namespaces**

​	All methods live in containers like a **class**, but even most classes live in other containers called **namespaces**.	

​	The Console class lives in a namespace called **System**.

> [!NOTE]
>
> <img src="/Users/adminkino/Library/Application Support/typora-user-images/image-20251208201455680.png" alt="image-20251208201455680" style="zoom:25%;" />

```c#
using System;
```

> [!CAUTION]
>
> But with C# 10, the compiler will automatically search System and a handful of other extremely common namespaces without you needing to call it out.



#### **• The Base Class Library**

​	System, Console, and WriteLine are only a tiny slice of the entire collection of code called the **Base Class Library (BCL)**.	



#### **• Program and Main**

> [!NOTE]
>
> <img src="/Users/adminkino/Library/Application Support/typora-user-images/image-20251208202212166.png" alt="image-20251208202212166" style="zoom:25%;" />



#### **• Statements**

​	The entire Console.WriteLine("Hello, World!"); line is called a **statement**.



#### **• Expressions**

​	Expressions are bits of code that your **program must process or evaluate** to determine their value. C# programs use expressions heavily.

​	The **+** symbol is one of many tools that can be used to build expressions.	



#### **• Variables**

​	Variables are **containers** for data. Before using a variable, we must indicate that we need one. This is called **declaring the variable.**



#### **• Reading Text from the Console**

​	Console has a **ReadLine** method that retrieves text that a person types until they hit the **Enter key.**

```c#
string name;
Console.WriteLine("What is your name?");
name = Console.ReadLine();
Console.WriteLine("Hi " + name);
```

> [!TIP]
>
> **Challenge: Consolas and Telim**

```c#
Console.WriteLine("Bread is ready,");
Console.WriteLine("Who is the bread for?"); 
string recceiver = Console.ReadLine();
Console.WriteLine("Noted: " +  recceiver + " got bread.");
```



#### **• COMPILER ERRORS, DEBUGGERS, AND CONFIGURATIONS**

​	**(1) Compiler Errors and Warnings**

​		For example, when we do something like string name = Console.ReadLine();, you may have noticed that you get a warning that states, “**Converting null literal or possible null value to a non-nullable type.**”

​	**(2) Debugging**

​		Trying to figure out why a program does not do what you expected and then **adjusting** it is called debugging.

​	**(3) Build Configurations**

​		In the C# world, configuration data is organized into **different build configurations**. Each configuration provides different information to the compiler about **how to build things**. There are **two configurations** defined by default, the **Debug** configuration and the **Release** configuration.

​	The main difference is that the **Release configuration** has **optimizations** turned on which allow the compiler to make certain adjustments so that your code can **run faster without changing what it does**. For example, if you declare a variable and never use it, optimized code will strip it out. **Unoptimized code will leave it in**. The **Debug configuration has this turned off**. When debugging your code, these optimizations can make it harder to hunt down problems. **As you are building your program, it is usually better to run with the Debug configuration**. When you’re ready to share your program with others, you compile it with the Release configuration instead.



------

### Variables

​	A variable is a named location in memory for storing data.

#### **• What is a variable?**

​	When we talk about memory and variables, we are talking about “**volatile**” memory (or **RAM**) that sticks around while your program runs but is wiped out when your program closes or the computer is rebooted.

​	Each memory location has a **unique numeric memory address**, which can be used to access any specific location’s contents.

​	The first step in using a variable is to **declare** it. Declaring a variable allows the computer to reserve a spot for it in **memory** of the appropriate size.



#### **• CREATING AND USING VARIABLES IN C#**	

```c#
string username; // Declaring a variable

username = Console.ReadLine(); // Assigning a value to a variable

Console.WriteLine("Hi " + username); // Retrieving its current value
```



#### **• INTEGERS**

```c#
int a, b, c;
a = b = c = 10;
c = 10; // The same to uppers
b = c;
a = b;
```

​	Two **convention**s among C# programmers are **camelCase** (or lowerCamelCase) and **PascalCase** (or UpperCamelCase), which are illustrated by the way their names are written. Most C# programmers use **lowerCamelCase** for **variables** and **UpperCamelCase** for other things.



------

### **THE C# TYPE SYSTEM**

​	Types of variables and values matter in C#. They are not interchangeable.

​	There are **eight integer types** for storing integers of differing sizes and ranges: **int**, **short**, **long**, **byte**, **sbyte**, **uint**, **ushort**, and **ulong**. These **eight types** are called **integer types** or **integral types**.

​	There are **three** types for storing **real numbers**: **float**, **double**, and **decimal**.

​	Using **var** for a variable’s type tells the compiler to **infer its type** from the surrounding code, so you do not have to type it out. (But it still has a specific type.)

​	The **Convert** class helps convert one type to another.

​	The **int type** uses **4 bytes** and can represent numbers between roughly **-2 billion** and **+2 billion**. 

​	The **short type** uses **2 bytes** and can represent numbers between about **-32,000**

and **+32,000**.

​	The **long type** uses **8 bytes** and can represent numbers between about **-9 quintillion** and **+9 quintillion** (a quintillion is a billion billion).

​	Thus **ushort**’s range is 0 to about 65,000, **uint**’s range is 0 to about 4 billion, and **ulong**’s range is 0 to about 18 quintillion.

​	The **char** type uses two bytes to allow for **65,536** distinct characters. The number assigned to each character follows a widely used standard called **Unicode**.

​	If you know the **hexadecimal Unicode** number for a symbol and would prefer to use that, you can write that out after a **\u**:

```c#
char aLetter = '\u0061'; // An 'a'
```

​	The **float** type uses **4 bytes**, while **double** uses twice that many (hence the “double”) at **8 bytes**. The **decimal** type uses **16 bytes**.

```c#
double number1 = 3.5623;
float number2 = 3.5623F;
decimal number3 = 3.5623M;
double avogadrosNumber = 6.022e23;
```



#### **• TYPE INFERENCE**

```c#
var message = "Hello, World!";
```

This only works if you **initialize the variable on the same line** it is declared. Otherwise, there is not enough information for the compiler to infer its type. This won’t work:

```c#
var x; // DOES NOT COMPILE!
```



#### **• THE CONVERT CLASS AND THE PARSE METHODS**

​	The **Convert** class is like the **Console** class—a thing in the system that provides you with a set of tasks or capabilities that it can perform.

```c#
Console.Write("What is your favorite number?");
string favoriteNumberText = Console.ReadLine();
int favoriteNumber = Convert.ToInt32(favoriteNumberText);
Console.Write(favoriteNumber + " is a great number!");
```

![image-20251209165531826](/Users/adminkino/Library/Application Support/typora-user-images/image-20251209165531826.png)

Many of these types have a **Parse method** to convert a string to the type. For example:

```c#
int number = int.Parse("9000");
```

<img src="/Users/adminkino/Library/Application Support/typora-user-images/image-20251209170230886.png" style="transform: rotate(90deg); zoom:35%;">

------

### MATH

#### **• SPECIAL NUMBER VALUES**

​	All 11 define a **MinValue** and a **MaxValue**:

```c#
int aBigNumber = int.MaxValue;
short aBigNegativeNumber = short.MinValue;
```

​	The **double** and **float** types (but **not decimal**) also define a value for positive and negative infinity called **PositiveInfinity** and **NegativeInfinity**:	

```c#
double infinity = double.PositiveInfinity; // ∞
```

​	**double** and **float** also define a weird value called **NaN**, or “not a number.”

```c#
double notAnyRealNumber = double.NaN;
```



#### **• OVERFLOW AND ROUNDOFF ERROR**

```c#
float a = 10000;
float b = 0.00001f;
float sum = a + b;
```

​	The result is rounded to 10000, and sum will still be 10000 after the addition. Roundoff error is not usually a big deal, but occasionally, the lost digits accumulate, like when adding huge piles of tiny numbers. You can sometimes sidestep this by using a more precise type. For example, neither double nor decimal have trouble with this specific situation. **But all three have it eventually, just at different scales.**



#### **• THE MATH AND MATHF CLASSES**

​	**π** and **e**: **Math.E** and **Math.PI**

​	the **Pow** and the **Sqrt**, the **Abs**, **Sin**, **Cos**, and **Tan**

​	**Min**, **Max**, and **Clamp**

> [!NOTE]
>
> **Clamp** allows you to **provide a value and a range**. If the value is within the range, that value is returned. If that value is lower than the range, it produces the low end of the range. If that value is higher than the range, it produces the high end of the range.

```c#
double x = 3.0;
double xSquared = Math.Pow(x, 2);
double y = Math.Sqrt(xSquared);
int x = Math.Abs(-2); // Will be 2.
double y1 = Math.Sin(0);
double y2 = Math.Cos(0);
int smaller = Math.Min(2, 10);
int larger = Math.Max(2, 10);
int health;
health += 10;
health = Math.Clamp(health, 0, 100); // Keep it in the interval 0 to 100.
```

​	**MathF** uses **floats** instead of doubles.

```c#
float x = 3;
float xSquared = MathF.Pow(x, 2);
```



------

### **CONSOLE 2.0**

​	An **@** before a string **ignores** any would-be **escape sequences**: @"C:\Users\Me\File.txt". (**verbatim string literal**)

​	A **$** before a string means **curly braces contain code**: "a:{a} sum:{a+b}".



#### **• The Write Method**

```c#
Console.Write("What is your name, human? "); // Notice the space at the end.
string userName = Console.ReadLine();
```



#### **• The ReadKey Method**

​	The **Console.ReadKey** method waits for only **a single keypress**. 

```c#
Console.WriteLine("Press any key when you're ready to begin.");
Console.ReadKey();
```

**One version**, shown above, **has no inputs**. The other version has an input whose type is **bool**, which indicates whether the text should be “**intercepted**” or not. (Not display on console)

```c#
Console.WriteLine("Press any key when you're ready to begin.");
Console.ReadKey(true);
```



#### **• Changing Colors**

The **Console** class provides variables that store the colors it uses for displaying text.

```c#
Console.BackgroundColor = ConsoleColor.Yellow;
Console.ForegroundColor = ConsoleColor.Black;
```

**ConsoleColor** is an enumeration, **Yellow** and **Black** are the names of two items in the **ConsoleColor collection**. **Console’s Clear** method to wipe out all text on the screen and change the entire background to the newly set background color:

```c#
Console.Clear();
```



#### **• Changing the Window Title**

​	**Console** also has a **Title** variable, which will change the text displayed in the console window's title bar.

```c#
Console.Title = "Hello, World!";
```



#### **• The Beep Method**

​	The Console class can even **beep**!

```c#
Console.Beep();
Console.Beep(440, 1000); //choose both frequency and duration
```



#### **• Escape Sequences**

```c#
Console.WriteLine("""); // ERROR: Bad quotation marks!
Console.WriteLine("\"");
Console.WriteLine("C:\\Users\\RB\\Desktop\\MyFile.txt");
// C:\Users\RB\Desktop\MyFile.txt
Console.WriteLine(@"C:\Users\RB\Desktop\MyFile.txt"); // verbatim string literal
```



#### **• String Interpolation**

```c#
Console.WriteLine($"My favorite number is {myFavoriteNumber}.");
```

​	You can combine **string interpolation** and **verbatim strings** by using **$** and **@** in either order.



#### • Alignment and formatting

​	**Alignment** lets you display a string with a specific preferred width.

​	Alignment is useful if you structure text in a table and need things to **line up horizontally**.

```c#
string name1 = Console.ReadLine();
string name2 = Console.ReadLine();
Console.WriteLine($"#1: {name1,20}");
Console.WriteLine($"#2: {name2,20}");
```

​	If you want the whitespace to be **after the word**, use a **negative number**:

```c#
Console.WriteLine($"{name1,-20} - 1");
Console.WriteLine($"{name2,-20} - 2");
```

```c#
Console.WriteLine($"{Math.PI:0.000}"); // It even rounds!
```

​	Using a format string of **000.000** with the number 42 will display **042.000**

​	In **contrast**, a **#** will leave a place for a digit but will not display a non-significant 0 (a leading or trailing 0):

```c#
Console.WriteLine($"{42:#.##}");// Displays "42"
Console.WriteLine($"{42.1234:#.##}");// Displays "42.12"
```

​	You can also use the **%** symbol to make a number be represented as **a percent** instead of a fractional value. 

```c#
float currentHealth = 4;
float maxHealth = 9;
Console.WriteLine($"{currentHealth/maxHealth:0.0%}"); // Displays "44.4%"
```

​	Several shortcut formats exist. For example, using just a **simple P** for the format is equivalent to **0.00%**, and **P1** is equal to **0.0%**. Similarly, a format string of **F** is the same as **0.00**, while **F5** is the same as **0.00000**.

> [!TIP]
>
> **Challenge: The Defense of Consolas**
>
> ```c#
> Console.Write("Target Row? ");
> int row = Convert.ToInt32(Console.ReadLine());
> Console.Write("Target Column? ");
> int col = Convert.ToInt32(Console.ReadLine());
> Console.BackgroundColor = ConsoleColor.Yellow;
> Console.ForegroundColor = ConsoleColor.Black;
> Console.Title = "Defense of Consolas";
> Console.WriteLine("Deploy to:");
> Console.WriteLine($"({row}, {col - 1})");
> Console.WriteLine($"({row-1}, {col})");
> Console.WriteLine($"({row}, {col + 1})");
> Console.WriteLine($"({row+1}, {col})");
> Console.Beep();
> Console.ResetColor();
> ```



------

### **DECISION MAKING**

> [!TIP]
>
> ##### Challenge: Repairing the Clocktower
>
> ```C#
> int Number = Convert.ToInt32(Console.ReadLine());
> if (Number % 2 == 0)
> {
>     Console.WriteLine("Tick");
> }
> else
> {
>     Console.WriteLine("Tock");
> }
> ```
>
> **Challenge: Watchtower**
>
> ```c#
> int XPos = Convert.ToInt32(Console.ReadLine());
> int YPos = Convert.ToInt32(Console.ReadLine());
> if (XPos == 0 && YPos == 0)
> {
>     Console.WriteLine("The enemy is here!");
> } else if (XPos == 0 && YPos > 0)
> {
>     Console.WriteLine("The enemy is to the north!");
> } else if (XPos == 0 && YPos < 0)
> {
>     Console.WriteLine("The enemy is to the south!");
> } else if (YPos == 0 && XPos > 0)
> {
>     Console.WriteLine("The enemy is to the east!");
> } else if (YPos == 0 && XPos < 0)
> {
>     Console.WriteLine("The enemy is to the west!");
> } else if (XPos < 0 && YPos > 0)
> {
>     Console.WriteLine("The enemy is to the north-west!");
> }else if (XPos > 0 && YPos > 0)
> {
>     Console.WriteLine("The enemy is to the north-east!");
>     
> } else if (XPos < 0 && YPos < 0)
> {
>     Console.WriteLine("The enemy is to the south-west!");
> }
> else
> {
>     Console.WriteLine("The enemy is to the south-east!");
> }
> ```
>
> 



------

### SWITCHES

​	The **statement form**: switch (number) { case 0: DoStuff(); break; case 1: DoStuff(); break; default: DoStuff(); break; }

​	The **expression form**: number switch { 0 => "zero", 1 => "one", _ => "other" }

#### **• SWITCH STATEMENTS**

```c#
switch (choice)
{
	case 1:
		Console.WriteLine("Ye rest and recover your health.");
		break;
	case 2:
		Console.WriteLine("Raiding the port town get ye 50 gold doubloons.");
		break;
	case 3:
		Console.WriteLine("The wind is at your back; the open horizon ahead.");
		break;
	case 4:
		Console.WriteLine("'Tis but a baby Kraken, but still eats toy boats.");
		break;
	default:
		Console.WriteLine("Apologies. I do not know that one.");
		break;
}
```



#### • SWITCH EXPRESSIONS

```C#
string response;
response = choice switch
{
		1 => "Ye rest and recover your health.",
		2 => "Raiding the port town get ye 50 gold doubloons.",
		3 => "The wind is at your back; the open horizon ahead.",
		4 => "'Tis but a baby Kraken, but still eats toy boats.",
		_ => "Apologies. I do not know that one." // wildcard
};
Console.WriteLine(response);
```

​	For starters, in a **switch expression**, the switch’s target **comes before the switch** **keyword** instead of after.



#### **• SWITCHES AS A BASIS FOR PATTERN MATCHING**

> [!TIP]
>
> **Challenge: Buying Inventory**
>
> ```c#
> Console.Write("What number do you want to see the price of?");
> int choice = Convert.ToInt32(Console.ReadLine());
> string response = choice switch
> {
>     1 => "Rope cost 10 golds",
>     2 => "Torches cost 16 golds",
>     3 => "Climbing Equipment costs 24 golds",
>     4 => "Clean Water costs 2 golds",
>     5 => "Machete costs 20 golds",
>     6 => "Canoe costs 200 golds",
>     7 => "Food Supplies cost 2 golds",
>     _ => "We don't sell that thing here.."
> };
> Console.WriteLine(response);
> ```

> [!TIP]
>
> **Challenge: Discounted Inventory**
>
> ```c#
> string[] ItemList = new string[]
> {
>     "Rope",
>     "Torches",
>     "Climbing Equipment",
>     "Clean Water",
>     "Machete",
>     "Machete",
>     "Food Supplies"
> };
> int[] ItemCosts = new int[]
> {
>     10,
>     16,
>     24,
>     2,
>     20,
>     200,
>     2
> };
> Console.Write("What number do you want to see the price of?");
> int choice = Convert.ToInt32(Console.ReadLine().Trim());
> Console.Write("Sorry, what is your name again?");
> string name = Console.ReadLine().Trim();
> if (name == "RB")
> {
>     Console.WriteLine($"{ItemList[choice - 1]} cost {(ItemCosts[choice - 1]) / 2} golds");
> }
> else
> {
>     Console.WriteLine($"{ItemList[choice - 1]} cost {ItemCosts[choice - 1]} golds");
> }
> 
> ```



------

### LOOPING

​	**while** loop: while (condition) { ... }

​	**do/while** loop: do { ... } while (condition);

​	**for** loop: for (initialization; condition; update) { ... }

​	**break** exits the loop. **continue** immediately jumps to the next iteration of the loop.

> [!TIP]
>
> **Challenge:  The Prototype**
>
> ```c#
> Console.Write("User 1, enter a number between 0 and 100: ");
> int GuessNumber = Convert.ToInt32(Console.ReadLine());
> // int GuessNumber2 = int.Parse(Console.ReadLine());
> Console.WriteLine("User 2, guess the number.");
> while (true)
> {
>     Console.Write("What is your next guess? ");
>     int GuessedNumber = Convert.ToInt32(Console.ReadLine());
>     if (GuessedNumber == GuessNumber)
>     {
>         Console.Clear();
>         Console.WriteLine("Your guessed the number!");
>         break;
>     } else if (GuessedNumber > GuessNumber)
>     {
>         Console.WriteLine($"{GuessedNumber} is too high");
>     }
>     else
>     {
>         Console.WriteLine($"{GuessedNumber} is too low");
>     }
> }
> 
> ```
>
> **Challenge: The Magic Cannon**
>
> ```C#
> for (int initial = 1; initial <= 100; initial++)
> {
>     if ((initial % 3 == 0) && (initial % 5 == 0))
>     {
>         Console.BackgroundColor = ConsoleColor.Blue;
>         Console.WriteLine($"{initial}: Electric and Fire");
>         Console.ResetColor(); 
>     } else if (initial % 3 == 0) // Fire gem activates
>     {
>         Console.BackgroundColor = ConsoleColor.Red;
>         Console.WriteLine($"{initial}: Fire");
>         Console.ResetColor(); 
>     } else if (initial % 5 == 0) // Electric blast
>     {   
>         Console.BackgroundColor = ConsoleColor.Yellow;
>         Console.WriteLine($"{initial}: Electric"); 
>         Console.ResetColor(); 
>     }
>     else
>     {
>         Console.WriteLine($"{initial}: Normal");
>     }
> }
> Console.ResetColor();
> ```



------

### **ARRAYS**

​	**Indexing from end**: int last = scores[^1];

[^n]: Index from the end

​	**Getting a range**: int[] someScores = scores[1..3];

​	**1..3 will grab the elements at indexes 0, 1, and 2, but not at 3.**

​	**scores[2..]** creates a copy of the entire array except the first two.

​	Lots of ways to **create arrays**: **new int[3], new int[] { 1, 2, 3 }, new [] { 1, 2, 3 }**

​	**Multi-dimensional arrays**: int[**,**] grid = new int[3, 3];

```c#
int[] scores = new int[10] { 100, 95, 92, 87, 55, 50, 48, 40, 35, 10 };
// Ignore the size
int[] scores = new int[] { 100, 95, 92, 87, 55, 50, 48, 40, 35, 10 }; 
int[] scores = new [] { 100, 95, 92, 87, 55, 50, 48, 40, 35, 10 };
```

> [!TIP]
>
> **Challenge: The Replicator of D’To**
>
> ```c#
> int[] Array = new int[5];
> for (int i = 0; i < Array.Length; i++)
> {
>     Array[i] = int.Parse(Console.ReadLine());
> }
> int[] CopyArray = new int[Array.Length];
> for (int i = 0; i < CopyArray.Length; i++)
> {
>     CopyArray[i] = Array[i];
>     Console.WriteLine(CopyArray[i]);
>     Console.WriteLine(Array[i]);
> }
> ```



#### **• THE FOREACH LOOP**

```c#
int[] scores = new int[10];
foreach (int score in scores)
Console.WriteLine(score);
```

​	A **foreach** loop is typically easier to read than its for counterpart, but a **foreach loop also runs slightly slower than a for loop**. If **performance becomes a problem**, you might rewrite a problematic foreach loop as a for loop to speed it up.

> [!TIP]
>
> **Challenge: The Laws of Freach**
>
> ```c#
> int[] array = new int[] { 4, 51, -7, 13, -99, 15, -8, 45, 90 };
> int total = 0;
> foreach(int i in array)
>     total += i;
> float average = (float)total / array.Length;
> Console.WriteLine(average);
> ```



#### **• MULTI-DIMENSIONAL ARRAYS**

```c#
int[][] matrix = new int[3][];
matrix[0] = new int[] { 1, 2 };
matrix[1] = new int[] { 3, 4 };
matrix[2] = new int[] { 5, 6 };
Console.WriteLine(matrix[0][1]); // Should be 2.
```

```c#
int[,] matrix = new int[3, 2] { { 1, 2 }, { 3, 4 }, { 5, 6 } };
Console.WriteLine(matrix[0, 1]);
```

​	Arrays of this nature are called **multi- dimensional arrays** or **rectangular arrays**. **Multi-dimensional arrays** can have as many dimensions as you need (for example, bool[,,]), and you can have multi-dimensional arrays of regular arrays or regular arrays of multi-dimensional arrays (int[,][], float[][,,,], etc.). These get tough to understand very quickly, so proceed with caution.

​	To loop through all elements in a **multi-dimensional array**, you will probably want to use the **GetLength** method

```c#
int[,] matrix = new int[4,4];
for (int row = 0; row < matrix.GetLength(0); row++)
{
	for (int column = 0; column < matrix.GetLength(1); column++)
		Console.Write(matrix[row, column] + " ");
	Console.WriteLine();
}
```



------

### **METHODS**

​	Methods can produce a result with a **return value**: int GetNumber() { return 2; }

​	**Two methods** can have the same name (an **overload**) if their parameters are different.

​	Some simple methods can be defined with **an expression body**: int GetNumber() => 2;

​	<img src="/Users/adminkino/Library/Application Support/typora-user-images/image-20251211134954044.png" alt="image-20251211134954044" style="zoom:25%;" />

​	For example, **WriteLine** lives in **Console**, and **Main** lives in **Program**. This code map shows that methods can also be defined inside other methods.

​	C# programmers often use the words method and function synonymously. But there are some subtle differences. Formally, **any reusable, callable code block is a function**. **A function is also a method if it is a member of a class.** So technically, Main is a method, but CountToTen is not. Functions that are defined inside of other functions are known as local functions.



#### **• SIMPLE METHODS WITH EXPRESSIONS**

```C#
int DoubleAndAddOne(int value)
{
	return value * 2 + 1;
}
```

```C#
int DoubleAndAddOne(int value) => value * 2 + 1;
```

​	The **=>** is used to indicate that **an expression is coming next**. We saw it with switch expression.



#### **• XML DOCUMENTATION COMMENTS**

​	The simplest way to start using XML Documentation Comments is to go to the line immediately before a method and type three forward slashes: **///**.

```C#
/// <summary>
/// Counts to the given number, starting at 1 and including the number provided.
/// </summary>
void Count(int numberToCountTo)
{
for (int index = 1; index <= numberToCountTo; index++)
Console.WriteLine(index);
}
```

> [!TIP]
>
> **Challenge: Taking a Number**
>
> ```c#
> int AskForNumber(string text)
> {
>     Console.WriteLine(text);
>     int number = int.Parse(Console.ReadLine());
>     return number;
> }
> 
> int AskForNumberInRange(string text, int min, int max)
> {
>     while (true)
>     {
>         Console.WriteLine(text);
>         int number = Convert.ToInt32(Console.ReadLine());
>         if (number >= min && number <= max)
>         {
>             return number;
>         }
>         else
>         {
>             Console.WriteLine("Please enter a number between {0} and {1}.", min, max);
>         }
>     }
>     
> }
> 
> AskForNumber("Which number is your preference?");
> AskForNumberInRange("From 0 to 100, which number is your favorite?", 0, 100);
> ```

> [!TIP]
>
> **Challenge: Countdown**
>
> ```c#
> int CountDownNumber(int number)
> {
>     if (number == 1) return 1;
>     Console.WriteLine(number);
>     return CountDownNumber(number - 1);
> }
> 
> Console.WriteLine(CountDownNumber(10));
> ```



------

### **MEMORY MANAGEMENT**

 	**Value semantics** means two things are equal if their data elements are equal. **Reference semantics** means two things are equal if they’re the same location in memory.



####  **• MEMORY AND MEMORY MANAGEMENT**

​	Modern computers have vast quantities of memory available, but it is not unlimited. Using memory is fine, but you need to clean up after yourself when you finish using it.

​	But two models are almost universal: the **stack** and the **heap**. C#, like many other languages, uses both.

​	

#### **• THE STACK**

​	All stack memory is either reserved for a method we will eventually return to, or it is available for use. As methods are called, the line advances and space is reserved for it. As methods return, the line retreats, leaving the memory available for reuse.



####  **• THE HEAP**

​	When we need memory that can be created in **arbitrary sizes**, we ditch the stack and find another spot.

​	The heap is not as structured as the stack. It is a random assortment of various allocated data with no rigid organizational patterns, hence the name.

​	 **To keep track of items placed on the heap, we capture a reference to the new object when we create it.**



#### **• The Heap as a Graph of Objects**

​	You can think of the heap as a set of objects interconnected by references like a web—what mathematicians would call a **directed graph**.



#### **• Value Types and Reference Types**

​	The first category is **value types**. Variables whose types are value types contain their data right there, in place. **They have a known, fixed size**.

​	The second category is **reference types**. Variables whose types are reference types hold only a reference to the data, and the data is placed somewhere on the heap. **Two pieces of the same type of data are not guaranteed to have the same size in memory, though the references themselves are all the same size.**

​	This single difference has far-reaching consequences, so it is essential to know what category any given type is in. **This is also a way that C# differs from similar languages.** C++ and Java, the two most similar programming languages to C#, handle memory quite differently.



#### **• Value Semantics and Reference Semantics**

​	When two things are equal because their values are equal, they have value semantics. **Value types have value semantics**.

```C#
int a = 88;
int b = 88;
bool areEqual = (a == b); // Will be true
```

​	When two things are equal only if they are the same reference, they have **reference semantics**.

```c#
int[] a = new int[] { 1, 2, 3 };
int[] b = new int[] { 1, 2, 3 };
bool areEqual = (a == b); // Will be false!
```



#### **• CLEANING UP HEAP MEMORY**

​	If our program uses memory and fails to clean it up, it cannot be reused by something else. The memory is unused as it stands but cannot be put back into useful service either. **This is called a memory leak**.

​	Additionally, **if we return memory to the heap too early**, some part of our program is still using it for what it once was. For a time, the rest of the system may just see it as unused memory, and the consequences aren’t high. But eventually, the heap will reuse that section of memory for a second item, and two parts of our program will be using the same memory for two different things. This is called a **dangling reference** or a **dangling pointer**. Part of your program unknowingly uses memory that was already given back to the heap.



#### **• Automatic Memory Management**

​	Within the **.NET runtime**, an element called the **garbage collector** (sometimes abbreviated to the GC) periodically wakes up and scans the system for anything the program can no longer reach.

​	The garbage collector works well for the heap but does nothing for the stack. But the **stack was managing its memory just fine on its own**.

> [!TIP]
>
> **Boss Battle: Hunting the Manticore**
>
> ```c#
> int CityLife = 15, CityRest = 15;
> int ManticoreLife = 10, ManticoreRest = 10;
> int ManticoreDistance;
> int Round = 1;
> while (true)
> {
>     Console.Write("Player 1, how far away from the city do you want to station the Manticore? ");
>     ManticoreDistance = int.Parse(Console.ReadLine());
>     if (ManticoreDistance < 1 || ManticoreDistance > 100)
>     {
>         Console.WriteLine("You are too far away to Consolas");
>     }
>     else
>     {
>         break;
>     }
> }
> 
> while (true)
> {
>     Console.WriteLine("Player 2, it is your turn");
>     CurrentStatus();
>     if (CityRest <= 0)
>     {
>         Console.WriteLine("The Consolas failed...");
>         return;
>     }
> 
>     if (ManticoreRest <= 0)
>     {
>         Console.WriteLine("The Manticore has been destroyed! The city of Consolas has been saved!");
>         return;
>     }
> }
> void CurrentStatus()
> {
>     Console.Write($"""
>                    ------------------------------------
>                    STATUS: Round: {Round}  City: {CityRest}/{CityLife}  Manticore: {ManticoreRest}/{ManticoreLife}
>                    The cannon is expected to deal 1 damage this round.
>                    Enter desired cannon range: 
>                    """);
>     int desireAttack =  int.Parse(Console.ReadLine());
>     if (desireAttack < ManticoreDistance)
>     {
>         Console.WriteLine("That round FELL SHORT of the target.");
>         CityRest--;
>     } else if (desireAttack > ManticoreDistance)
>     {
>         Console.WriteLine("That round OVERSHOT the target.");
>         CityRest--;
>     }
>     else
>     {
>         Console.WriteLine("That round was a DIRECT HIT!");
>         if (Round % 3 == 0 && Round % 5 == 0)
>         {
>             ManticoreRest -= 10;
>         } else if (Round % 3 == 0 || Round % 5 == 0)
>         {
>             ManticoreRest -= 3;
>         }
>         else
>         {
>             ManticoreRest--;
>         }
> 
>         CityRest--;
>     }
> 
>     Round++;
> }
> ```



------

## **PART 2: Object-Oriented Programming**

### **OBJECT-ORIENTED CONCEPTS**

​	Each object has a single responsibility (or perhaps a set of closely related responsibilities), and the objects work together to solve the overall problem.

​	In C#, **every object belongs to a specific class or type**. An object’s class determines the object’s “shape.” All objects of the same class have the **same data elements and methods**. You can think of **classes as categories**; everything in a class is similar in nature and structure.

​	**Use the right type for everything you create. If the right type doesn’t exist, create it first.**



------

### **ENUMERATIONS**

#### **• ENUMERATION BASICS**

​	An **enumeration** or an **enumerated type** is a type whose choices are one of a small list of possible options. The verb enumerate means “**to list off things, one by one**,” hence the name. ( when you can make an **exhaustive list**, not leaving anything out)

​	 They derive from `System.Enum`, which derives from `System.ValueType`, so Enumerations are **value types**.



#### **• Defining an Enumeration**

```c#
enum Season { Winter, Spring, Summer, Fall }
```

<img src="/Users/adminkino/Library/Application Support/typora-user-images/image-20251216221633542.png" alt="image-20251216221633542" style="zoom:25%;" />



#### **• Using an Enumeration**

```c#
Season current = Season.Summer;
if (current == Season.Summer || current == Season.Winter)
	Console.WriteLine("Happy solstice!");
else
	Console.WriteLine("Happy equinox!");
enum Season { Winter, Spring, Summer, Fall } 
// New types MUST go after other code (or in another file).
```

> [!TIP]
>
> **Challenge: Simula’s Test**
>
> ```c#
> LoopChest current = LoopChest.Locked;
> while (true)
> {
>     Console.Write($"""The chest is {current.ToString().ToLower()}. What do you want to do? """);
>     string state = Console.ReadLine();
>     if (state == "unlock") {
>         current = LoopChest.Unlocked;
>     } else if (state == "open")
>     {
>         current = LoopChest.Open;        
>     } else if (state == "close")
>     {
>         current = LoopChest.Unlocked;
>     } else if (state == "lock")
>     {
>         current = LoopChest.Locked;
>     }
> }
> 
> enum LoopChest { Open, Unlocked, Locked};
> ```



#### **• UNDERLYING TYPES**

​	The deep dark secret of **enumerations is that they are integers at heart**, though the compiler will ensure you don’t accidentally misuse them. Each enumeration has an **underlying type**, which is the **integer type** that it builds upon. The default underlying type is int, but you could change that:

```c#
enum Season : byte { Winter, Spring, Summer, Fall }
```

By default, these are given in the order they appear in the definition, **starting with 0**.

```C#
enum Season { Winter = 3, Spring = 6, Summer = 9, Fall = 12 }
enum Season { Winter = 1, Spring, Summer, Fall } 
// Spring = 2, Summer = 3, Fall = 4
```

The default value for an enumeration is **whichever one is assigned the number 0**.

You can also **cast between ints and enumerations**:

```C#
int number = (int)Season.Fall;
Season now = (Season)2;
```





------

### TUPLES

​	Tuples combine multiple elements into a single bundle: **(double, double) point = (2, 4)**;

​	You can give (**ephemeral**) names to tuple elements, which can be used later: (double x, double

y) point = (2, 4);

​	Most C# programmers only use tuples **occasionally**.

​	When **multiple data elements** are combined, it is sometimes referred to as a **composite type** because the larger thing is composed of the smaller pieces. Or you could say that we use **composition** to build the larger element.



#### • THE BASICS OF TUPLES

​	In C#, the simplest tool for creating composite types is called a tuple (pronounced “TOO-ples” or “TUP-ples”).

```c#
(string, int, int) score = ("R2-D2", 12420, 15);
var score = ("R2-D2", 12420, 15);
Console.WriteLine($"Name:{score.Item1} Level:{score.Item3} Score:{score.Item2}");
```

​	Behind the scenes, the names really are **Item1, Item2, and Item3**.

```C#
(string, int, int) score1 = ("R2-D2", 12420, 15);
(string, int, int) score2 = score1; // An exact match works.
(string, int) partialScore = score1; // Not the same number of items.
(int, int, string) mixedUpScore = score1; // Items in a different order.
```

​	**Tuples are value types**, like int, bool, and double. If a tuple has parts that are **value types** themselves, those bytes will get copied. But if an item is a reference type, then the reference is copied.

​	

#### **• TUPLE ELEMENT NAMES**

​	The names of the items in a tuple are **Item1, Item2, etc.** **Behind the scenes, that is precisely how they work.**

```c#
(string Name, int Points, int Level) score = ("R2-D2", 12420, 15);
Console.WriteLine($"Name:{score.Name} Level:{score.Level} Score:{score.Points}");
```

​	Any unnamed item will keep its original ItemN name:

```c#
(string Name, int, int) score = ("R2-D2", 12420, 15);
Console.WriteLine($"Name:{score.Name} Level:{score.Item3} Score:{score.Item2}");

// When use var, the names will be inferred as well.
var score = (Name: "R2-D2", Points: 12420, Level: 15);
Console.WriteLine($"Name:{score.Name} Level:{score.Level} Score:{score.Points}");
// For tuples, names are only cosmetic. 
```

​	

#### **• TUPLES AND METHODS**

```C#
void DisplayScore((string Name, int Points, int Level) score)
{
    Console.WriteLine(
      $"Name:{score.Name} Level:{score.Level} Score:{score.Points}");
}
```

​	**Parameters cannot use var**, so we are obligated to list the tuple item types in this case.

​	You can **return a tuple** from a method by placing its constituent parts in parentheses (names optional) in the spot where we list the return type:

```C#
(string Name, int Points, int Level) GetScore() => ("R2-D2", 12420, 15);

var score = GetScore();
Console.WriteLine($"Name:{score.Name} Level:{score.Level} Score:{score.Points}");
```



```c#
(string One, int Two, int Three) score = GetScore();
DisplayScore(score);
(string N, int P, int L) GetScore() => ("R2-D2", 12420, 15);
void DisplayScore((string Name, int Points, int Level) score)
{
    Console.WriteLine(
    $"Name:{score.Name} Level:{score.Level} Score:{score.Points}");
}
// names are ephemeral and not a part of the tuple.
```

​	Here is a **tuple** with 16 elements to show a much bigger tuple, representing a **4×4 matrix**— something often used in games:

```C#
var matrix = (M11: 1, M12: 0, M13: 0, M14: 0,
              M21: 0, M22: 1, M23: 0, M24: 0,
              M31: 0, M32: 0, M33: 1, M34: 0,
              M41: 0, M42: 0, M43: 0, M44: 1);
```

```C#
(string Name, int Points, int Level)[] CreateHighScores()
{
    return new (string, int, int)[3]
    {
        ("R2-D2", 12420, 15),
        ("C-3PO", 8543, 9),
        ("GONK", -1, 1),
    };
}
```



#### **• DECONSTRUCTING TUPLES**

​	There is a way to take all of the parts of a tuple and place them each into separate variables all at once. This is called **deconstruction or unpacking**.

```c#
string name;
int points;
int level;
(name, points, level) = score;
Console.WriteLine($"{name} reached level {level} with {points} points.");
```

```C#
// The result is x and y have swapped values with only a single line
double x = 4;
double y = 2;
(x, y) = (y, x);
```



#### **• Ignoring Elements with Discards**

```c#
(string name, int points, _) = score;
// The _ is a discard variable.
```



#### **• TUPLES AND EQUALITY**

​	Tuples are value types and thus, use **value semantics** when checking for equality.

```c#
(int, int) a = (1, 2);
(int, int) b = (1, 2);
Console.WriteLine(a == b); // True
Console.WriteLine(a != b); // False

var a = (X: 2, Y: 4);
var b = (U: 2, V: 4);
Console.WriteLine(a == b); // True
```

> [!TIP]
>
> **Challenge: Simula’s Soup**
>
> ```c#
> using System.Diagnostics.Tracing;
> (Food food, Ingredient ingredient, Seasoning seasoning) Special = (Food.Stew, Ingredient.Chicken, Seasoning.Spicy);
> Console.WriteLine($"Today's Special Menu: {Special.seasoning} {Special.ingredient} {Special.food}");
> Console.WriteLine($"""
>                    Hey you! Welcome to Simula's Kitchen, what do you prefer for today?
>                    (1) {(Food)1}? (2) {(Food)2}? (3) {(Food)3}? 
>                    """);
> int food = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""
>                    Well well well... You came to the right place, 
>                    {(Food)food} is what we have today,
>                    then tell me, which ingredient you prefer?...
>                    (1) {(Ingredient)1}? (2) {(Ingredient)2}? (3) {(Ingredient)3}? (4) {(Ingredient)4}
>                    """);
> int ingredient = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""
>                    Perfect! Now would you like a little bit flavor?
>                    (1) {(Seasoning)1} (2) {(Seasoning)2} (3) {(Seasoning)3} 
>                    """);
> int seasoning = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""
>                    All done! Enjoy your 
>                    "{(Seasoning)seasoning} {(Ingredient)ingredient} {(Food)food}"
>                    """);
> enum Food {Soup = 1, Stew, Gumbo};
> 
> enum Ingredient
> {
>     Mushrooms = 1,
>     Chicken,
>     Carrots,
>     Potatoes
> };
> 
> enum Seasoning
> {
>     Spicy = 1,
>     Salty, 
>     Sweet
> }
> ```



------

### **CLASSES**

#### **• DEFINING A NEW CLASS**

​	 **Names** are usually capitalized with **UpperCamelCase**, just like enumerations and methods.

```c#
// <-- Your main method goes here.
Score best = new Score();
best.name = "R2-D2";
best.points = 12420;
best.level = 15;
if (best.EarnedStar())
  Console.WriteLine("You earned a star!");

class Score
{
    public string name; // fields or instance variables
    public int points;
    public int level;
  
    public bool EarnedStar() => (points / level) > 1000;
}
// <-- Other classes and enumerations can go here.
```

​	**Fields** are variables created inside the object’s memory on the **heap**. They live for as long as the object lives and are a part of the object itself.

​	**Object-Oriented Principle #1: Encapsulation—Combining data (fields) and the operations on that data (methods) into a well-defined unit (like a class).**	

​	

#### **• CONSTRUCTORS**

```c#
class Score
{
    public string name;
    public int points;
    public int level;
  
    public Score()	
    {
        name = "Unknown";
        points = 0;
        level = 1;
    }
    public bool EarnedStar() => (points / level) > 1000;
}
```

​	**Constructors** must use the same name as the class, and they cannot list a return type.



#### **• Name Hiding and the this Keyword**

```c#
class Score
{
    public string _name;
    public int _points;
    public int _level;
    
    public Score(string name, int points, int level)
    {
        _name = name;
        _points = points;
        _level = level;
    }
}
```

​	The **underscores** let us use similar names with a clear way to **differentiate fields from local variables and parameters.**

```c#
class Score
{
    public string name;
    public int points;
    public int level;
    
    public Score(string name, int points, int level)
    {
        this.name = name;
        this.points = points;
        this.level = level;
    }
}
```

​	The **this** keyword is like a special variable that always refers to the object you are currently in.



#### **• Calling Other Constructors with this**

```c#
Score first = new();
Score second = new("R2-D2", 12420, 15);

// The compiler can infer that you are creating an instance of the Score class because it is assigned to a Score-typed variable. 
// This feature is most valuable when our type name is long and complex.

class Score
{
    public string _name;
    public int _points;
    public int _level;
    
    public Score() : this("Unknown", 0, 1)
    {
    }
  
    public Score(string name, int points, int level)
    {
        _name = name;
        _points = points;
        _level = level;
    }
}
```

> [!TIP]
>
> **Challenge: Vin Fletcher’s Arrows**
>
> ```c#
> using System.Runtime.CompilerServices;
> Console.WriteLine($"""Which type of the arrowhead you would want? (1) {Arrowhead.Steel}, (2) {Arrowhead.Wood} or (3) {Arrowhead.Obsidian}?""");
> int arrowOrder = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""Then which type of the fletching you would like? (1) {Fletching.Plastic}, (2) {Fletching.GooseFeathers} or (3) {Fletching.TurkeyFeathers}""");
> int fletchingOrder = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""Finally, what would be the length of your choice? Remember between 60 and 100 cm long""");
> float shaftLength = float.Parse(Console.ReadLine());
> 
> Arrow userPick = new Arrow();
> float costs = userPick.GetCost(0f,arrowOrder, fletchingOrder, shaftLength);
> Console.WriteLine($"""Hello adventurer! Your cost will be {costs} golds""");
> enum Arrowhead
> {
>     Steel = 1,
>     Wood,
>     Obsidian
> }
> 
> enum Fletching
> {
>     Plastic = 1,
>     TurkeyFeathers,
>     GooseFeathers
> }
> 
> class Arrow
> {
>     public Arrowhead _Head;
>     public Fletching _Fletching;
>     public float _ShaftLength;
> 
>     public Arrow() : this(Arrowhead.Steel, Fletching.Plastic, 60.0f)
>     {
>         
>     }
> 
>     public Arrow(Arrowhead head, Fletching fletching, float shaftLength)
>     {
>         _Head = head;
>         _Fletching = fletching;
>         _ShaftLength = shaftLength;
>     }
> 
>     public float GetCost(float totalCost, int arrowOrder, int fletchingOrder, float shaftLength)
>     {
>         while (true)
>         {
>             totalCost += arrowOrder switch
>             {
>                 1 => 10,
>                 2 => 3,
>                 3 => 5,
>                 _ => 0
>             };
> 
>             totalCost += fletchingOrder switch
>             {
>                 1 => 10,
>                 2 => 3,
>                 3 => 5,
>                 _ => 0
>             };
> 
>             totalCost += 0.05f * shaftLength;
> 
>             if (totalCost != 0f)
>             {
>                 return totalCost;
>             }
>             else
>             {
>                 Console.WriteLine("Sorry, we don't offer this in our store!");
>             }
>         } 
>     }
> }
> ```



------

### **INFORMATION HIDING**

​	Data (fields) should be **private** in nearly all cases.

​	**Abstraction**: when things are private, they can change **without affecting the outside world**. The outside world depends on the public parts, while anything private can change without problems.

​	A third level is **internal**, which is meant to be used only inside the project.

​	This level covers the next **two fundamental concepts of object-oriented programming**: **information hiding and abstraction**.

​	**Object-Oriented Principle #2: Information Hiding—Only the object itself should directly access its data.**

​	

#### **• THE PUBLIC AND PRIVATE ACCESSIBILITY MODIFIERS**

​	The **public** and **private** keywords are both called accessibility modifiers because they change the accessibility level of the thing they are applied to.

```c#
class Rectangle
{
    private float _width;
    private float _height;
    private float _area;
  
    public Rectangle(float width, float height)
    {
      _width = width;
      _height = height;
      _area = width * height;
     }
}
```

​	**If you don’t specify an accessibility level, members of a class will be private.**

​	**Object-Oriented Principle #3: Abstraction—The outside world does not need to know each object or class’s inner workings and can deal with it as an abstract concept. Abstraction allows the inner workings to change without affecting the outside world.**



#### **• TYPE ACCESSIBILITY LEVELS AND THE INTERNAL MODIFIER**

​	The difference is that things made **public can be accessed everywhere**, including in other projects, while **internal can only be used in the project it is defined in**.

​	There are **three levels** of **share/don’t-share decisions** to make. (1) Do I **share a project or not**? (2) Should this **individual type definition be shared** or not? (3) Should this **member—a field or a method—be shared** or not?  C# programmers usually consider these different levels in isolation.

​	I’m bringing up **internal** here because it is the default accessibility level for a type if none is explicitly written out. **My advice is to always write out your intended accessibility level rather than leave it to the defaults.**

​	By the way, while **type definitions must be either public or internal**, **members of a class can be public, private, or internal**. (For an **enumeration, members are automatically public, and you cannot change that**.)

```c#
public class MyClass { }      // Reference type
public struct MyStruct { }    // Value type
public enum MyEnum { }        // Value type
public interface IMyInterface { } // Reference type
```

> [!TIP]
>
> **Challenge: Vin’s Trouble**
>
> ```c#
> using System.Runtime.CompilerServices;
> Console.WriteLine($"""Which type of the arrowhead you would want? (1) {Arrowhead.Steel}, (2) {Arrowhead.Wood} or (3) {Arrowhead.Obsidian}?""");
> int arrowOrder = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""Then which type of the fletching you would like? (1) {Fletching.Plastic}, (2) {Fletching.GooseFeathers} or (3) {Fletching.TurkeyFeathers}""");
> int fletchingOrder = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""Finally, what would be the length of your choice? Remember between 60 and 100 cm long""");
> float shaftLength = float.Parse(Console.ReadLine());
> 
> Arrow userPick = new Arrow((Arrowhead)arrowOrder, (Fletching)fletchingOrder, shaftLength);
> float costs = userPick.GetCost();
> if (costs == -1.0f)
> {
>     Console.WriteLine("Sorry, we might need you to provide us with correct customized options");
> }
> else
> {
>     Console.WriteLine($"""Hello adventurer! Your cost will be {costs} golds""");
> }
> 
> enum Arrowhead
> {
>     Steel = 1,
>     Wood,
>     Obsidian
> }
> 
> enum Fletching
> {
>     Plastic = 1,
>     TurkeyFeathers,
>     GooseFeathers
> }
> 
> class Arrow
> {
>     private Arrowhead _Head;
>     private Fletching _Fletching;
>     private float _ShaftLength;
> 
>     public Arrow() : this(Arrowhead.Steel, Fletching.Plastic, 60.0f)
>     {
>         
>     }
> 
>     public Arrow(Arrowhead head, Fletching fletching, float shaftLength)
>     {
>         _Head = head;
>         _Fletching = fletching;
>         _ShaftLength = shaftLength;
>     }
> 
>     public float GetCost()
>     {
>         if (GetShaftLength() == -1.0f)
>         {
>             return -1.0f;
>         }
> 
>         float totalCost = 0f;
>         
>         while (true)
>         {
>             totalCost += _Head switch
>             {
>                 Arrowhead.Steel => 10,
>                 Arrowhead.Wood => 3,
>                 Arrowhead.Obsidian => 5,
>                 _ => 0
>             };
> 
>             totalCost += _Fletching switch
>             {
>                 Fletching.Plastic => 10,
>                 Fletching.TurkeyFeathers => 3,
>                 Fletching.GooseFeathers => 5,
>                 _ => 0
>             };
>             
>             totalCost += 0.05f * _ShaftLength;
> 
>             if (totalCost != 0f)
>             {
>                 return totalCost;
>             }
>             else
>             {
>                 Console.WriteLine("Sorry, we don't offer this in our store!");
>             }
>         } 
>     }
> 
>     public Arrowhead GetArrowhead()
>     {
>         return _Head;
>     }
> 
>     public Fletching GetFletching()
>     {
>         return _Fletching;
>     }
> 
>     public float GetShaftLength()
>     {
>         if (_ShaftLength >= 60 && _ShaftLength <= 100)
>         {
>             return _ShaftLength;
>         }
>         else
>         {
>             return -1.0f;
>         }
>     }
> }
> ```



------

### **PROPERTIES**

​	**Properties** give you field-like access while still protecting data with methods: 

​	**public float Width { get => width; set => width = value; }**. To use a property: rectangle.Width = 3;

​	**Auto-properties** are for when no extra logic is needed: **public float Width { get; set; }**

​	<u>Properties can be **read-only**, only settable in a constructor: **public float Width { get; }**</u>

​	Fields can also be **read-only**: private readonly float _width = 3;

​	**With properties, objects can be initialized using object initializer syntax**: new Rectangle() { Width = 2, Height = 3 }.

​	An **init** accessor is like a setter but **only usable in object initializer syntax**. public float Width { get; init; }



#### **• THE BASICS OF PROPERTIES**

​	In C#, there is a tool we can use to get the benefits of both **information hiding and abstraction** while keeping our code simple: **properties**. A property **pairs a getter and setter** under a shared name with **field-like** access.

```c#
// 1. Normal
private float _width;
public float GetWidth() => _width;
public void SetWidth(float value) => _width = value;

// 2. Property using expression bodies
private float _width;
public float Width
{
    get => _width;
    set => _width = value;
} // This defines a property with the name Width whose type is float.
// It is typical to use UpperCamelCase for property names.

// 3. Property using block bodies
public float Width
{
    get
    {
        return _width;
    }
  // We didn’t define a value parameter, bu in essence, one automatically exists in a property setter.
    set
    {
        _width = value;
    }
}

// the field is called the property’s backing field or backing store. 
// Properties do not require both getters and setters.
public float Area
{
    get => _width * _height;
}

// If a property is get-only and the getter has an expression body, we can simplify it further:
public float Area => _width * _height;
```

```c#
public class Rectangle
{
  private float _width;
  private float _height;
  public Rectangle(float width, float height)
  {
      _width = width;
      _height = height;
  }
  public float Width
  {
      get => _width;
      set => _width = value;
  }
  public float Height
  {
      get => _height;
      set => _height = value;
  }
  public float Area => _width * _height;
}
```

​	**Field-like access to the properties instead of method-like access:**

```c#
Rectangle r = new Rectangle(2, 3);
r.Width = 5;
Console.WriteLine($"A {r.Width}x{r.Height} rectangle has an area of {r.Area}.");
```

```C#
public float Width
{
    get => _width;
    private set => _width = value;		
}	
```



#### **• AUTO-IMPLEMENTED PROPERTIES**

```c#
// 1. Without auto-implementation
public class Player
{
    private string _name;
    public string Name
    {
        get => _name;
        set => _name = value;
    }
}

// 2. Auto-implementation property
public class Player
{
		public string Name { get; set; }
}

// Initialize the backing field to a specific starting value
public string Name { get; set; } = "Player";
```

```c#
public class Rectangle // Note how short this code got with auto-properties.
{
    public float Width { get; set; }
    public float Height { get; set; }
    public float Area => Width * Height;
    public Rectangle(float width, float height)
    {
        Width = width;
        Height = height;
    }
}
```



#### **• IMMUTABLE FIELDS AND PROPERTIES**

​	**Read-only properties**. When a property is **immutable**, its behavior is like concrete or a tattoo. **You have complete control when the object is being created, but it cannot be changed again once the object is created.**

​	If you have a field that you don’t want to change after construction, you can apply the **readonly** keyword to it as a modifier:

```c#
public class Player
{
    private readonly string _name;
    public Player(string name)
    {
        _name = name;
    }
}
```

​	**When all of a class’s properties and fields are immutable (get-only auto-properties and readonly fields), the entire object is immutable**.



#### **• OBJECT INITIALIZER SYNTAX AND INIT PROPERTIES**

​	C# provides a simple syntax for **setting properties right as the object is created** called **object initializer** syntax, shown below:	

```c#
// 1. Object Initializer
Circle circle = new Circle() { Radius = 3, X = -4 };
// 2. Parameterless object initializer
Circle circle = new Circle { Radius = 3, X = -4 };
```

​	**You cannot use object initializer syntax with properties that are get-only.** While you can assign a value to them in the constructor, object initializer syntax comes after the constructor finishes. This is a **predicament** because it would mean you must make your properties mutable (have a setter) to use them in object initializer syntax, which is too much power in some situations.

​	The middle ground is an **init** accessor. This is a setter that can be used in limited circumstances, including with an inline initializer (the 0’s below) and in the constructor, but also in object initializer syntax:

```c#
public class Circle
{
    public float X { get; init; } = 0;
    public float Y { get; init; } = 0;
    public float Radius { get; init; } = 0;
}

Circle circle = new Circle { X = 1, Y = 4, Radius = 3 };
// This would not compile if it were not a comment:
// circle.X = 2;
```

> [!TIP]
>
> #### **Challenge: The Properties of Arrows**
>
> ```c#
> using System.Runtime.CompilerServices;
> Console.WriteLine($"""Which type of the arrowhead you would want? (1) {Arrowhead.Steel}, (2) {Arrowhead.Wood} or (3) {Arrowhead.Obsidian}?""");
> int arrowOrder = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""Then which type of the fletching you would like? (1) {Fletching.Plastic}, (2) {Fletching.GooseFeathers} or (3) {Fletching.TurkeyFeathers}""");
> int fletchingOrder = Convert.ToInt32(Console.ReadLine());
> Console.WriteLine($"""Finally, what would be the length of your choice? Remember between 60 and 100 cm long""");
> float shaftLength = float.Parse(Console.ReadLine());
> 
> Arrow userPick = new Arrow((Arrowhead)arrowOrder, (Fletching)fletchingOrder, shaftLength);
> // Arrow userPick = new Arrow 
> //{ 
> //    Head = (Arrowhead)arrowOrder, 
> //    Fletching = (Fletching)fletchingOrder, 
> //    ShaftLength = shaftLength 
> //};
> float costs = userPick.GetCost();
> Console.WriteLine($"""Hello adventurer! Your cost will be {costs} golds""");
> 
> 
> enum Arrowhead
> {
>     Steel = 1,
>     Wood,
>     Obsidian
> }
> 
> enum Fletching
> {
>     Plastic = 1,
>     TurkeyFeathers,
>     GooseFeathers
> }
> 
> class Arrow
> {
>     public Arrowhead Head { get; init; } = Arrowhead.Steel;
>     public Fletching Fletching { get; init; } = Fletching.Plastic;
>     private float ShaftLength = 60.0f;
>     public float ShaftLength { 
>         get => _ShaftLength;
>         // It's a special keyword that C# provides automatically in property setters
>         // and init accessors to represent the incoming value
>         init
>         {
>             if (value < 60 || value > 100)
>             {
>                 throw new ArgumentException("Shaft length must be between 60 and 100 cm");
>             }    
>         }
>         
>     }
> 
>     public Arrow() : this(Arrowhead.Steel, Fletching.Plastic, 60.0f)
>     {
> 
>     }
> 
>     public Arrow(Arrowhead head, Fletching fletching, float shaftLength)
>     {
>         Head = head;
>         Fletching = fletching;
>         ShaftLength = shaftLength;
>     }
> 
>     public float GetCost()
>     {
>         float totalCost = 0f;
>         
>         totalCost += Head switch
>         {
>             Arrowhead.Steel => 10,
>             Arrowhead.Wood => 3,
>             Arrowhead.Obsidian => 5,
>             _ => 0
>         };
> 
>         totalCost += Fletching switch
>         {
>             Fletching.Plastic => 10,
>             Fletching.TurkeyFeathers => 3,
>             Fletching.GooseFeathers => 5,
>             _ => 0
>         };
> 
>         totalCost += 0.05f * ShaftLength;
>         return totalCost;
>     }
> }
> ```

> [!IMPORTANT]
>
> Many classes use both - constructors for required parameters, object initializers for optional ones:
>
> ```c#
> class Email
> {
>     public string To { get; init; }
>     public string Subject { get; init; }
>     public string Body { get; init; }
>     public bool IsHighPriority { get; init; } = false;  // Optional
>     public List<string> Attachments { get; init; } = new();  // Optional
>     
>     public Email(string to, string subject, string body)  // Required params
>     {
>         To = to;
>         Subject = subject;
>         Body = body;
>     }
> }
> 
> // Use constructor for required, initializer for optional:
> var email = new Email("user@example.com", "Hello", "Hi there!")
> {
>     IsHighPriority = true,
>     Attachments = { "file.pdf" }
> };
> ```



#### **• ANONYMOUS TYPES**

```c#
var anonymous = new { Name = "Steve", Age = 34 };
Console.WriteLine($"{anonymous.Name} is {anonymous.Age} years old.");
```



------

### **STATIC**

​	If a **class is marked static**, it can only contain **static members** (Console, Convert, Math).

```c#
public class Score
{
    private static readonly int PointThreshold = 1000;
    private static readonly int LevelThreshold = 4;
    // If they are static, they tend to be UpperCamelCase instead.
  
}
```



#### **• Global State**

​	Static fields have their uses, but a word of caution is in order. If a field is **static**, **public**, and **not read-only**, it creates global state. 



#### **• Static Properties**	

```c#
public class Score
{
    public static int PointThreshold { get; } = 1000;
    public static int LevelThreshold { get; } = 4;
    // ...
}
```



#### **• Static Methods**

​	**Methods** can also be **static**. A static method is not tied to a single instance, so **it cannot refer to any non-static (instance) fields, properties, or methods**.

​	Static methods are most often used for **utility or helper methods** that **provide some sort of service related to the class** they are placed in, but that isn’t tied directly to a single instance.

​	Another common use of static methods is a **factory method**, which **creates new instances for the outside world as an alternative to calling a constructor**. For example, this method could be a factory method in our Rectangle class:

```c#
public static Rectangle CreateSquare(float size) => new Rectangle(size, size);
Rectangle rectangle = Rectangle.CreateSquare(2);
```



#### **• Static Constructors**	

```c#
public class Score
{
    public static readonly int PointThreshold;
    public static readonly int LevelThreshold;
  	
    static Score()
    {
    PointThreshold = 1000;
    LevelThreshold = 4;
      }
// ...
}
```

A **static constructor cannot have parameters**, **nor can you call it directly**. Instead, it **runs automatically the first time you use the class**. Because of this, you cannot place an accessibility modifier like public or private on it.



#### **• STATIC CLASSES**

```c#
public static class Utilities
{
    public static int Helper1() => 4;
    public static double HelperProperty => 4.0;
    public static int AddNumbers(int a, int b) => a + b;
}
```

> [!TIP]
>
> **Challenge: Arrow Factories**
>
> ```c#
> using System.Runtime.CompilerServices;
> Console.WriteLine($"""
>                    Hi adventurer, what brings you to my store? You wanna build a new arrow?
>                    Well well well... We have four types arrows you could choose:
>                    (1) Elite Arrow (2) Beginner Arrow (3) Marksman Arrow (4) Custom Arrow
>                    """);
> int choice = Convert.ToInt32(Console.ReadLine());
> Arrow userPick;
> if (choice == 4)
> {
>     Console.WriteLine($"""Which type of the arrowhead you would want? (1) {Arrowhead.Steel}, (2) {Arrowhead.Wood} or (3) {Arrowhead.Obsidian}?""");
>     int arrowOrder = Convert.ToInt32(Console.ReadLine());
>     Console.WriteLine($"""Then which type of the fletching you would like? (1) {Fletching.Plastic}, (2) {Fletching.GooseFeathers} or (3) {Fletching.TurkeyFeathers}""");
>     int fletchingOrder = Convert.ToInt32(Console.ReadLine());
>     Console.WriteLine($"""Finally, what would be the length of your choice? Remember between 60 and 100 cm long""");
>     float shaftLength = float.Parse(Console.ReadLine());
> 
>     userPick = new Arrow((Arrowhead)arrowOrder, (Fletching)fletchingOrder, shaftLength);
> }
> else
> {
>     userPick = choice switch
>     {
>         1 => Arrow.CreateEliteArrow(),
>         2 => Arrow.CreateBeginnerArrow(),
>         3 => Arrow.CreateMarksArrow(),
>         _ => throw new NotImplementedException(),
>     };
> }
> 
> float costs = userPick.GetCost();
> Console.WriteLine($"""Hello adventurer! Your cost will be {costs} golds""");
> 
> 
> enum Arrowhead
> {
>     Steel = 1,
>     Wood,
>     Obsidian
> }
> 
> enum Fletching
> {
>     Plastic = 1,
>     TurkeyFeathers,
>     GooseFeathers
> }
> 
> class Arrow
> {
>     public Arrowhead Head { get; init; } = Arrowhead.Steel;
>     public Fletching Fletching { get; init; } = Fletching.Plastic;
>     private float _ShaftLength = 60.0f;
>     public float ShaftLength { 
>         get => _ShaftLength;
>         // It's a special keyword that C# provides automatically in property setters
>         // and init accessors to represent the incoming value
>         init
>         {
>             if (value < 60 || value > 100)
>             {
>                 throw new ArgumentException("Shaft length must be between 60 and 100 cm");
>             }    
>         }
>         
>     }
> 
>     public Arrow() : this(Arrowhead.Steel, Fletching.Plastic, 60.0f)
>     {
> 
>     }
> 
>     public Arrow(Arrowhead head, Fletching fletching, float shaftLength)
>     {
>         Head = head;
>         Fletching = fletching;
>         ShaftLength = shaftLength;
>     }
> 
>     public static Arrow CreateEliteArrow()
>     {
>         return new Arrow(Arrowhead.Steel, Fletching.Plastic, 95.0f);
>     }
> 
>     public static Arrow CreateBeginnerArrow()
>     {
>         return new Arrow(Arrowhead.Wood, Fletching.GooseFeathers, 75.0f);
>     }
> 
>     public static Arrow CreateMarksArrow()
>     {
>         return new Arrow(Arrowhead.Steel, Fletching.GooseFeathers, 65.0f);
>     }
> 
>     public float GetCost()
>     {
>         float totalCost = 0f;
>         
>         totalCost += Head switch
>         {
>             Arrowhead.Steel => 10,
>             Arrowhead.Wood => 3,
>             Arrowhead.Obsidian => 5,
>             _ => 0
>         };
> 
>         totalCost += Fletching switch
>         {
>             Fletching.Plastic => 10,
>             Fletching.TurkeyFeathers => 3,
>             Fletching.GooseFeathers => 5,
>             _ => 0
>         };
> 
>         totalCost += 0.05f * ShaftLength;
>         return totalCost;
>     }
> }
> ```



------

### **Null References**

​	Check for null with **x == null**, the **null conditional operators x?.DoStuff()** and **x?[3]**, and use **??** to allow null values to fall back to some other default: **x ?? "empty"**	

```c#
string name = null;
// A null reference indicates the absence of a value

string name = null;
Console.WriteLine(name.Length);
// Crush
```



#### **• NULL OR NOT?**

​	For reference-typed variables, stop and think if null should be an option.

​	Any reference-typed variable can either have a ? at the end or not. A ? means that it may legitimately contain a null value.

```c#
string? name = Console.ReadLine(); // Can return null!
```



#### **• CHECKING FOR NULL**

```c#
string? name = Console.ReadLine();
if (name != null) // null check
	Console.WriteLine("The name is not null.");
```



#### **• Null-Conditional Operators: ?. and ?[]**

```c#
private string? GetTopPlayerName()
{
    if (_scoreManager == null) return null;
  
    Score[]? scores = _scoreManager.GetScores();
    if (scores == null) return null;
  
    Score? topScore = scores[0];
    if (topScore == null) return null;
  
    return topScore.Name;
}
```

There is **another way**: **null-conditional operators**. The **?.** and **?[]** operators can be used in place of . and [] to simultaneously check for null and access the member:

```c#
private string? GetTopPlayerName()
{
		return _scoreManager?.GetScores()?[0]?.Name;
}
```

Both ?. and ?[] evaluate the part before it to see if it is null. If it is, then no further evaluation happens, and the whole expression evaluates to null.



#### **• The Null Coalescing Operator: ??**

```c#
private string GetTopPlayerName() // No longer needs to allow nulls.
{
		return _scoreManager?.GetScores()?[0]?.Name ?? "(not found)";
}
```

If the code before the **?? evaluates to null**, then the **fallback value** of "(not found)" will be used instead.

```c#
private string GetTopPlayerName()
{
    string? name = _scoreManager?.GetScores()?[0]?.Name;
    name ??= "(not found)";
    return name; // No compiler warning. `??=` ensures we have a real value.
}
```



#### **• The Null-Forgiving Operator: !**

we can use the **null-forgiving operator**: !. It tells the compiler, “I know this looks like a potential null problem, but it won’t be. Trust me.”

```c#
string message = MightReturnNullIfNegative(+10)!;
```

**Use ! sparingly, but use it when needed.**



------

### **OBJECT-ORIENTED DESIGN**

Object-oriented design is the part of crafting software where we decide:

​	• which objects should exist in our program,

​	• the classes each of those objects belong to,

​	• what responsibilities each class or object should handle,

​	• when objects should come into existence,

​	• when objects should go out of existence,

​	• which objects must collaborate with or rely upon which other objects,

​	• and how an object knows about the other objects it works with.

Object-oriented design is sometimes referred to by the simpler terms **software design** or **design**.



#### **• REQUIREMENTS**

​	This is sometimes called requirements gathering, though that word has baggage.



#### **• DESIGNING THE SOFTWARE**

##### • Noun Extraction

​	**Concepts** that appear in the requirements will often lead to **classes of objects** in your design.

​	**Jobs or tasks** that appear in the requirements will often lead to responsibilities that your software must be able to do. 

​	You can start this process by **highlighting the nouns** (and **noun phrases**) and **verbs** (and **verb phrases**) that appear in the requirements. This is called noun extraction or noun and verb extraction. 



#####  **• UML**

​	Unified Modeling Language, or UML.



##### **• CRC Cards**

​	CRC cards are a way to think through potential object-oriented designs and flesh out some detail.

​	CRC is short for **Class-Responsibility-Collaborator**.



> [!IMPORTANT]
>
> **P184** This approach is close to an architecture sometimes used in games called the **Entity-Component-System** architecture.
>
> Please review this important part about how to design the classes.



##### **• Evaluating a Design**

​	**Rule #1**: It has to work. 

​	**Rule #2**: Prefer designs that convey meaning and intent.

​	**Rule #3**: Designs should not contain duplication.

​	**Rule #4**: Designs should not have unused or unnecessary elements.

​	

##### **• CREATING CODE**

```c#
public class Asteroid
{
    public float PositionX { get; private set; }
    public float PositionY { get; private set; }
    public float VelocityX { get; private set; }
    public float VelocityY { get; private set; }

    public Asteroid(float positionX, float positionY, float velocityX, float velocityY)
    {
        PositionX = positionX;
        PositionY = positionY;
        VelocityX = velocityX;
        VelocityY = velocityY;
    }

    public void Update()
    {
        PositionX += VelocityX;
        PositionY += VelocityY;
    }
}

public class AsteroidsGame
{
    private Asteroid[] _asteroids;

    public AsteroidsGame()
    {
        _asteroids = new Asteroid[5];
        _asteroids[0] = new Asteroid(100, 200, -4, -2);
        _asteroids[1] = new Asteroid(-50, 100, -1, +3);
        _asteroids[2] = new Asteroid(0, 0, 2, 1);
        _asteroids[3] = new Asteroid(400, -100, -3, -1);
        _asteroids[4] = new Asteroid(200, -300, 0, 3);
    }

    public void Run()
    {
        while (true)
        {
            foreach(Asteroid asteroid in _asteroids)
                asteroid.Update();
        }
    }
}
```



##### **• HOW TO COLLABORATE**

​	**Objects collaborate by calling members (methods, properties, etc.) on the object they need help from.**

 1. **Creating New Objects**

 2. **Constructor Parameters**

    Passing in the object through a constructor parameter is a popular choice **if an object needs another object from the beginning but can’t or shouldn’t just use new to make a new one.**

    ```c#
    public AsteroidsGame(Asteroid[] startingAsteroids)
    {
    		_asteroids = startingAsteroids;
    }
    ```

3. **Method Parameters**

​	On the other hand, if an object **only needs a reference to something for a single method**, it can be passed in as a method parameter.

```c#
public class AsteroidDriftingSystem
{
    public void Update(Asteroid[] asteroids)
    {
    		foreach (Asteroid asteroid in asteroids)
    		{
            asteroid.PositionX += asteroid.VelocityX;
            asteroid.PositionY += asteroid.VelocityY;
    		}
    }
}
```

4. **Asking Another Object**

```c#
public void Update(AsteroidsGame game)
{
    foreach (Asteroid asteroid in game.Asteroids)
    {
        asteroid.PositionX += asteroid.VelocityX;
        asteroid.PositionY += asteroid.VelocityY;
    }
}
```

5. **Supplying the Reference via Property or Method**

   Suppose you can’t supply a reference to an object in the constructor but need it for more than one method.

   ```c#
   public class AsteroidDriftingSystem
   {
       // Initialize this to an empty array, so we know it will never be null.
       public Asteroid[] Asteroids { get; set; } = new Asteroid[0];
     
       public void Update()
       {
       		foreach (Asteroid asteroid in Asteroids)
       		{
               asteroid.PositionX += asteroid.VelocityX;
               asteroid.PositionY += asteroid.VelocityY;
       		}
       }
   }
   ```

6. ##### **Static Members**

   A final approach would be to **use a static property**, **method**, or **field**. If it is public, these can be reached from anywhere.

   ```c#
   AsteroidsGame.Current = new AsteroidsGame();
   // ...
   
   public class AsteroidsGame
   {
   		public static AsteroidsGame Current { get; set;}
     // ...
   } 
   
   // Then AsteroidDriftingSystem can access the game through the static property
   public void Update()
   {
       foreach (Asteroid asteroid in AsteroidsGame.Current.Asteroids)
       {
           asteroid.PositionX += asteroid.VelocityX;
           asteroid.PositionY += asteroid.VelocityY;
   		}
   }
   ```

   Changing the structure of your code without changing what it does is called **refactoring**.



------

### **THE CATACOMBS OF THE CLASS**

> [!TIP]
>
> **Boss: Battle The Point**
>
> ```c#
> 	Point p1 = new Point { X = 2, Y = 3 };
> 	Point p2 = new Point(-4, 0);
> 	Console.WriteLine($""" ({p1.X}, {p1.Y}) """);
> Console.WriteLine($""" ({p2.X}, {p2.Y}) """);
> 
> public class Point
> {
>  public float X { get; init; } = 0f;
>  public float Y { get; init; } = 0f;
> 
>  public Point(float x, float y)
>  {
>      X = x;
>      Y = y;
>  }
> 
>  public Point() : this(0f, 0f)
>  {
>  }
> }
> ```
>
> **Boss Battle: The Color**
>
> ```c#
> Color c1 = new Color(128, 128, 128);
> Color yellow = Color.Yellow;
> Console.WriteLine($"""
>                 The first color is ({c1.Red}, {c1.Green}, {c1.Blue}))
>                 The second color is ({yellow.Red}, {yellow.Green}, {yellow.Blue})
>                 """);
> 
> public class Color
> {
>  public byte Red { get; }
>  public byte Green { get; }
>  public byte Blue { get; }
> 
>  // public Color() : this(255, 255, 255)
>  // {
>  //     
>  // }
>  // Can use object initializer via parameterless constructor
> 
>  public Color(byte red, byte green, byte blue)
>  {
>      Red = red;
>      Green = green;
>      Blue = blue;
>  }
> 
>  public static Color White { get;  } = new Color(255, 255, 255);
> 
>  public static Color Black { get; } = new Color(0, 0, 0);
> 
>  // public static Color Orange = new Color { Red = 999, Green = 999, Blue = 999 };
>  public static Color _Red { get; } = new Color(255, 0, 0);
>  public static Color Orange { get; } = new Color(255, 165, 0);
>  public static Color Yellow { get; } = new Color(255, 255, 0);
>  public static Color _Green { get; } = new Color(0, 128, 0);
>  public static Color _Blue { get; } = new(0, 0, 255);
>  public static Color Purple { get; } = new Color(128, 0, 128);
> }
> 
> // In C#, the convention is to expose data through properties, not fields 
> // Fields should typically be private
> // Properties provide a consistent public interface
> ```
>
> **Boss Battle: The Card**
>
> ```c#
> int ColorCount = 0;
> int RankCount = 0;
> // C# typeof() ≈ Java .class 
> foreach (Colors color in Enum.GetValues(typeof(Colors)))
>  ColorCount++;
> foreach (Ranks rank in Enum.GetValues(typeof(Ranks)))
>  RankCount++;
> 
> Card[] deck = new Card[ColorCount * RankCount];
> 
> int index = 0;
> foreach (Colors color in Enum.GetValues(typeof(Colors)) )
> {
>  foreach (Ranks rank in Enum.GetValues(typeof(Ranks)))
>  {
>      deck[index++] = new Card(color, rank);
>      Console.WriteLine($"""The {color} {rank}""");
>  }
> 
> }
> 
> public class Card
> {
>  // Not use parameterless constructor here, object initializer is suitable for optional fields.
>  public Colors Color { get; }
>  public Ranks Rank { get; }
> 
>  public Card(Colors color, Ranks rank)
>  {
>      Color = color;
>      Rank = rank;
>  }
> 
>  public bool IsSymbol => Rank == Ranks.Ampersand ||  Rank == Ranks.Percent ||   Rank == Ranks.Caret || Rank == Ranks.DollarSign;
>  public bool IsNumber => !IsSymbol;
>  // public bool IsSymbol 
>  // { 
>  //     get 
>  //     { 
>  //         return Rank == Rank.Ampersand || Rank == Rank.Caret || ...;
>  //     }
>  // }
>  // The => syntax is just a shorter way to write a read-only property with a getter
>  // C# convention - Boolean flags are typically properties, not methods
> }
> 
> public enum Colors{
>  Red ,
>  Green,
>  Blue,
>  Yellow
> }
> 
> public enum Ranks
> {
>  One ,
>  Two,
>  Three,
>  Four,
>  Five,
>  Six,
>  Seven,
>  Eight,
>  Nine,
>  Ten,
>  DollarSign,
>  Percent,
>  Caret,
>  Ampersand
> }
> ```
>
> **Boss Battle: The Locked Door**
>
> ```c#
> Console.WriteLine("Set the initial password: ");
> int password = Convert.ToInt32(Console.ReadLine());
> Door door = new Door(password);
> 
> while (true)
> {
> 	Console.WriteLine($"""
> 	                   The door is {door.State}. Now what do you need?
> 	                   (1) Open
> 	                   (2) Close
> 	                   (3) Lock
> 	                   (4) Unlock
> 	                   (5) Change Password
> 	                   """);
> 	int? command = Convert.ToInt32(Console.ReadLine());
> 	switch (command)
> 	{
> 		case 1:
> 			if (door.State == DoorState.Closed)
> 			{
> 				door.Open();
> 			}
> 			else
> 			{
> 				Console.WriteLine("Enter the password: ");
> 				int guessedPassword = Convert.ToInt32(Console.ReadLine());
> 				door.Unlock(guessedPassword);
> 				if (guessedPassword != password)
> 				{
> 					Console.WriteLine("The password is incorrect. Cannot open the door");
> 					door.Lock();
> 				}
> 			}
> 			break;
> 		case 2:
> 			door.Close();
> 			break;
> 		case 3:
> 			door.Lock();
> 			break;
> 		case 4:
> 			Console.WriteLine("Enter the password: ");
> 			int typedPassword = Convert.ToInt32(Console.ReadLine());
> 			door.Unlock(typedPassword);
> 			break;
> 		case 5:
> 			Console.WriteLine("Enter the current password: ");
> 			int currentPassword = Convert.ToInt32(Console.ReadLine());
> 			if (currentPassword == password)
> 			{
> 				int newPassword = Convert.ToInt32(Console.ReadLine());
> 				door.ChangePassword(currentPassword,newPassword);
> 			}
> 			break;
> 		default:
> 			Console.WriteLine("Invalid command, please try again!");
> 			break;
> 	}
> }
> 
> public class Door
> {
> 	private int _Password;
> 	public DoorState State { get; private set; }
> 
> 	public Door(int password)
> 	{
> 		_Password = password;
> 		State = DoorState.Closed;
> 	}
> 
> 	public void Open()
> 	{
> 		if (State == DoorState.Closed)
> 			State = DoorState.Open;
> 	}
> 
> 	public void Close()
> 	{
> 		if (State == DoorState.Open)
> 			State = DoorState.Closed;
> 	}
> 
> 	public void Lock()
> 	{
> 		if (State == DoorState.Closed)
> 			State = DoorState.Locked;
> 	}
> 
> 	public void Unlock(int password)
> 	{
> 		if(password == _Password &&  State == DoorState.Locked)
> 			State = DoorState.Closed;
> 	}
> 	
> 	public void ChangePassword(int previousPassword, int newPassword)
> 	{
> 		if(previousPassword == _Password)
> 		{
> 			_Password = newPassword;
> 			Console.WriteLine("The password has been changed.");
> 		}
> 		else
> 		{
> 			Console.WriteLine("The password is incorrect and change failed.");
> 		}
> 	}
> }
> 
> 
> public enum DoorState
> {
> 	Open,
> 	Closed,
> 	Locked
> }
> ```
>
> **Boss Battle: The Password Validator**
>
> ```c#
> PasswordValidator PV = new PasswordValidator();
> while (true)
> {
>     Console.WriteLine("Please enter a password:");
>     string password = Console.ReadLine();
>     if(PV.IsValid(password))
>     {
>         Console.WriteLine($"Password: {password}");
>         break;
>     }
> }
> 
> public class PasswordValidator
> {
>     public bool IsValid(string password)
>     {
>         if(!CheckLength(password)) throw new ArgumentException("Password should be at least 6 characters and no more than 13 characters");
>         if(!CheckContains(password, 'T')) throw  new ArgumentException("Password should not contain with 'T' character");
>         if(!CheckContains(password, '&')) throw new ArgumentException("Password should not contain with '&' character");
>         if(!HasUpper(password)) throw  new ArgumentException("Password should contain at least one uppercase letter");
>         if(!HasLower(password)) throw new ArgumentException("Password should contain at least one lowercase letter");
>         if(!HasDigit(password)) throw new ArgumentException("Password should contain at least one digit");
>         return true;
>     }
> 
>     private bool HasUpper(string password)
>     {
>         foreach (char c in password)
>         {
>             if (char.IsUpper(c))
>             {
>                 return true;
>             }
>         }
> 
>         return false;
>     }
> 
>     private bool HasLower(string password)
>     {
>         foreach (char c in password)
>         {
>             if (char.IsLower(c))
>             {
>                 return true;
>             }
>         }
> 
>         return false;
>     }
> 
>     private bool HasDigit(string password)
>     {
>         foreach (char c in password)
>         {
>             if (char.IsDigit(c))
>             {
>                 return true;
>             }
>         }
> 
>         return false;
>     }
> 
>     private bool CheckLength(string password)
>     {
>         if (password.Length > 13 || password.Length < 6)
>         {
>             return false;
>         }
>         return true;
>     }
> 
>     private bool CheckContains(string password, char letter)
>     {
>         foreach (char c in password)
>         {
>             if (c == letter)
>             {
>                 return false;
>             }
>         }
> 
>         return true;
>     }
> }
> ```
>
> 

