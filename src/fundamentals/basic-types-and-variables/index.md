title: Basic Types and Variables
subtitle: •••
theme: league

## It's a Value-Based Proposition

We saw *literals* yesterday. In the statement:

```C#
Console.WriteLine("Hello, World!");
```

`"Hello, World!"` is a String literal. It's a String because it's a sequence of characters surrounded by quotation marks. It's a literal because it always has that value.

## Let's Not Be Literal

In contrast, we have *variables*. In C#, a variable's *type* is defined, but its value can *vary* (thus the name).

<div class="fragment">
<p>Instead of:</p>

<pre><code class="language-C# hljs">Console.WriteLine("Hello, World!");
</code></pre>
</div>

<div class="fragment">
<p>I could have written…</p>
<pre><code class="language-C# hljs">String message = "Hello, World!";
Console.WriteLine(message);</code></pre>
</div>

## Variables are variable

Variables store a value, but allow us to change the value that is stored.

```java
String message = "I am Sam";
Console.WriteLine(message); // prints "I am Sam"

message = "I am Spartacus";
Console.WriteLine(message); // prints "I am Spartacus"
```

## Reusing Variables

Notice that in the previous example, when we first used our `message` variable, we specified its type:

<pre><code class="language-C# hljs" data-noescape><mark>String</mark> message = "I am Sam";
Console.WriteLine(message);</code></pre>

<div class="fragment">
<p>When we reassigned its value, we didn't specify a type:</p>
<pre><code class="language-C# hljs" data-noescape>message = "I am Spartacus";
Console.WriteLine(message);</code></pre>

That's because we had already <em>declared</em> the variable. We declare a variable only once.
</div>

## Defining Variables

When we do this:
```java
String message = "I am Sam";
```

<div class="fragment">
<p>We are really combining these two things:</p>
<pre><code class="language-java hljs">String message;
message = "I am Sam";</code></pre>
</div>

## Declaring vs Initializing a Variable

We declare a variable by giving it a *type* and a *name*. That's what we did here:

```java
String message;
```

The variable's *type* is `String`. Its *name* is `message`.

## Initializing a variable

When we did this, we assigned a value of `"I am Sam"` to the variable. *Initializing* is only different than *assigning* a value in that we haven't assigned a value yet:

<pre><code class="language-java hljs" data-noescape>String message;
<mark>message = "I am Sam";</mark></code></pre>

# Variable Naming Conventions

We will talk about naming conventions quite a bit. They're important, since they reduce the *cognitive load* of people that need to look at your code. (This person might be you.)

Apart from constants (more on that later), we use `camelCase` to name variables. The first letter should be lowercase, and the first letter of each additional word in a variable's name should be uppercase:

```C#
String myVariable = "my variable's value";
```

Not (all lowercase):
```C#
String myvariable = "my variable's value";
```

Not (begins with a capital letter):
```C#
String MyVariable = "my variable's value";
```

# Basic Data Types

C# is a *pure* object-oriented language. That is to say that is all data types, for example int string char long, are considered *objects*. We will introduce *objects* later in the course. For now, recognize that data types are declared in lowercase.

## Booleans

A `boolean` variable holds either the value `true` or `false`, which is represented by a '1' for 'true' and '0' for 'false'.

```java
boolean writingCodeIsFun = true;// Is represented by a 1.
boolean rootCanalsAreFun = false; // Is represented by a 0.
```
Question time: Are we using camelCase or PascalCase for our variable naming convention?

## Integer Primitives

There are three sizes of integer (whole number) types: `short`, `int`, and `long`. They vary in their maximum and minimum values. `short`s support a smaller range of values than `int` supports. `int` supports a smaller range of values than `long` supports. We use `int`s (short for "integer") for most practical purposes. We often see `long`s for things like database record ids since we may have a lot of records in a database.

All of the following are valid:

```C#
short answerInt = 42;
int answerInt = 42;
long answerInt = 42;
```

## Floating Point Primitives

Floating point (numbers with decimal fractions) types are `float` and `double`. `double` is more precise than `float`.

Let's try it. (Note that we append 'f' to the value for the float variable):

```C#
public class FloatingPointDemo {

	public static void main(String[] args) {
		
		double doubleValue = 2.16440330489723961032;
		System.out.println(doubleValue);
		
		float floatValue = 2.16440330489723961032f;
		System.out.println(floatValue);
	}

}
```

The values assigned to each variable are the same. Try it. What do you see?

*Computers aren't as good at math as you thought, eh?*

## Character primitives

The `char` type holds individual characters. We define `char` literals by using single apostrophes.

```java
char myChar = 'a';
```


## String objects

Strings are proper objects. We'll talk more about them later. We've seen them. We denote their values with quotation marks:

```java
String myDeclaration = "I can code";
```