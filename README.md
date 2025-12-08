# C#-ProgressTracker
> [!CAUTION]
>
> Following the C# Player's Guide of RB

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

​	
