title: Reading Input from the Console
subtitle: •••
theme: league

## java.util.Scanner

We can create a `Scanner` object to read input from the console (represented by `System.in`):

% TODO this bit needs more work

```java
package org.wecancodeit.fundamentals;

import java.util.Scanner;

public class NamePromptApp {

	public static void main(String[] args) {
		
		Scanner input = new Scanner(System.in);

		System.out.println("What is your name?");
		String name = input.nextLine();
		System.out.println("Hello, " + name);
		
		input.close();
	}
	
}
```

## Let's run it!

If I type *Ford Prefect*, then this is what I will see in my console:

<pre><code class="language-bash hljs" data-noescape>What is your name?
<span class="console-input">Ford Prefect</span>
Hello, Ford Prefect
</code></pre>

<style>
:root {
	--console-input-color: #36c87d
}

.console-input {
	color: var(--console-input-color);
}
</style>

# Let's Break It Down

Rather than a *primitive* like an `int` or a `boolean`, our `Scanner` is an *object*. (`String`s are objects, too.) `Scanner` is a *class* representing our `input` variable's type.

<pre><code class="language-bash hljs" data-noescape><mark>Scanner</mark> input = new Scanner(System.in);</code></pre>

Remember, primitive types are in all lowercase, while class names are `CapitalizedCamelCase`:

<pre><code class="language-bash hljs" data-noescape><mark>S</mark>canner input = new <mark>S</mark>canner(System.in);</code></pre>

## Creating the scanner

We use the `new` operator to create an object. The other operators we've seen have used one (`+`, `-`, `=`) or more (`++`, `!=`) symbols, but `new` is a legit operator, too:

<pre><code class="language-bash hljs" data-noescape>Scanner input = <mark>new</mark> Scanner(System.in);</code></pre>

It is followed by a special method called a `constructor`. The job of a constructor is to construct an object. A constructor's name is the same as the name of the type of thing it's constructing:

<pre><code class="language-bash hljs" data-noescape>Scanner input = new <mark>Scanner</mark>(System.in);</code></pre>

This constructor accepts `System.in` as a *parameter* in order to "scan" input from the console. `System.in` is the complement of `System.out`, representing console input:

<pre><code class="language-bash hljs" data-noescape>Scanner input = new Scanner(<mark>System.in</mark>);</code></pre>

More on classes, objects, and constructors later.

## Dat Message Do

Think of methods as messages we send to objects. We have been using the `main` method:

```java
public static void main(String[] args) {
	// your code here
}
```

`main` is the message that the **J**ava **V**irtual **M**achine (JVM) sends to our application's class to tell it to do something. You may hear a class containing a `main` method called a "main class".

## Can Ya Do Something For Me?

We call the `nextLine` method when we want to ask our `Scanner` for the next line of user input. This is like saying, "Hey input! Can ya give me the next line?":

<pre><code class="language-bash hljs" data-noescape>String name = input.<mark>nextLine()</mark>;</code></pre>

See that dot lurking in there? It's an operator, too. Whimsically, we refer to it as the *dot operator*:

<pre><code class="language-bash hljs" data-noescape>String name = input<mark>.</mark>nextLine();</code></pre>

We use the dot operator to send messages to objects. Ponder `System.out.println("my message");`. What's happening there?

## Call Me

If we look at the Scanner class, we can find out what that `nextLine()` method looks like. The part of the method before the opening curly bracket (`{`) is called its *signature*. The signature of the `nextLine()` method is:

```java
public String nextLine()
```

<div class="fragment">
<p>If it wasn't <code>public</code>, we wouldn't be able to see it, so we wouldn't be able to send that message:</p>
<pre><code class="language-bash hljs" data-noescape><mark>public</mark> String nextLine()</code></pre>
</div>

<div class="fragment">
<p><code>String</code> indicates the method's <em>return type</em>. This is how it responds when we talk to it. When we call <code>nextLine()</code>, its response is a <code>String</code>:</p>
<pre><code class="language-bash hljs" data-noescape>public <mark>String</mark> nextLine()</code></pre>
</div>

## Other Methods

`Scanner` offers us other methods, as well. (Its capabilities are far beyond our simple needs.) We have been using `nextLine()`, which reads an entire line of input. (Until you hit &lt;Enter&gt;.)

Used as we're using it, `Scanner` breaks up input by blank spaces and line breaks. Its other methods don't read entire lines. They read up to the first space or line break.

Here are some of those you may find useful:

|method			|what it does|return type|
|---------------|------------|-----------|
|nextLine()		|reads the next `String` from the input until the line break				|`String`|
|nextInt()		|reads the next `int` from the input until the *next space or* line break	|`int`|
|nextDouble()	|reads the next `double` from the input until the *next space or* line break|`double`|
|next()			|reads the next `String` from the input until the *next space or* line break|`String`|

## Demo

If we do this:

```java
Scanner input = new Scanner(System.in);

System.out.println("Enter street address:");

int houseNumber = input.nextInt();
String street = input.next();

System.out.println("house number is " + houseNumber);
System.out.println("street is " + street);
```

Then we can do this:

<pre><code class="language-bash hljs" data-noescape>Enter street address:
<span class="console-input">43 Brown St</span>
house number is 43
street is Brown</code></pre>