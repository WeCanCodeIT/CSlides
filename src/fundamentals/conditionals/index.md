title: Conditionals
subtitle: If not that, then… ?
theme: league

## An Insightful Process

![No worries](./resources/no-worries.png)

*This diagram isn't quite right. If you don't think learning to code is difficult, then you miiiight not get it yet.*

# Conditional Statements

Conditional statements are one of the ways that we control the flow of a program.

## We might say…

*If* I am 16 or older, *then* I can drive legally.

<div class="fragment">
<p>In Java, we would say:</p>
<pre><code class="language-java">int age = 42;
if (age >= 16) {
  System.out.println("You are " + age + ", so you are legal to drive.");
}</code></pre>
</div>

## We might say…

*If* I get eight or more hours of sleep, I am likely to feel more rested.

<div class="fragment">
<p>In Java, we would say:</p>
<pre><code class="language-java">int hoursOfSleep = 42;
if (hoursOfSleep >= 8) {
  System.out.println("You are likely to feel more rested.");
}</code></pre>
</div>

<div class="fragment">
<p>We can follow one conditional with another.</p>
<pre><code class="language-java">if (hoursOfSleep == 42) {
  System.out.println("He used 42 again, didn't he?");
 }</code></pre>
</div>

# Let's Break It Down

An `if` statement executes if its *condition* evaluates to `true`:

```java
int heightInInches = 73;

if(heightInInches >= 60) {
  System.out.println("You are tall enough to ride");
}
```

<div class="fragment">
<p>Sorry, you're too short. :(</p>
<pre><code class="language-java">int heightInInches = 42;

if(heightInInches >= 60) {
  System.out.println("You are tall enough to ride");
}</code></pre>
</div>

## Syntax

An `if` statement starts with the keyword `if`:
<pre><code class="language-java" data-noescape>int heightInInches = 73;

<mark>if</mark>(heightInInches >= 60) {
  System.out.println("You are tall enough to ride");
}</code></pre>

## Syntax

It is followed by parentheses that contain a *condition*:
<pre><code class="language-java" data-noescape>int heightInInches = 73;

if<mark>(</mark>heightInInches >= 60<mark>)</mark> {
  System.out.println("You are tall enough to ride");
}</code></pre>

## Syntax

This *condition* must evaluate to a `boolean` value:
<pre><code class="language-java" data-noescape>int heightInInches = 73;

if(<mark>heightInInches >= 60</mark>) {
  System.out.println("You are tall enough to ride");
}</code></pre>

## Syntax

This is followed by a code block that executes only if the *condition* is `true`. Remember that code blocks open with a left curly bracket (`{`) and close with a right curly bracket (`}`):
<pre><code class="language-java" data-noescape>int heightInInches = 73;

if(heightInInches >= 60) <mark>{</mark>
  System.out.println("You are tall enough to ride");
<mark>}</mark></code></pre>

We *can* skip the curly brackets if we only want to execute one line of code, but that's usually frowned upon since it's easy to mess up. This code is the same:

<pre><code class="language-java" data-noescape>int heightInInches = 73;

if(heightInInches >= 60) 
  System.out.println("You are tall enough to ride");</code></pre>

## Else what?

It's polite to offer an apology, eh? We can be polite.

An `if` statement allows us to do something else if its *condition* does not evaluate to `true`:

<pre><code class="language-java" data-noescape>int heightInInches = 42;

if(heightInInches >= 60) {
  System.out.println("You are tall enough to ride.");
} else {
  System.out.println("I'm sorry, too short.");
}</code></pre>

## And then?

We can create sequences of `if/else` statements:

```java
if(heightInInches >= 60) {
  System.out.println("You are tall enough to ride.");
} else if(heightInInches >= 30) {
  System.out.println("Try the teacups. They look fun.")
} else {
  System.out.println("I'm sorry, too short.");
}
```

Think of this as connecting multiple `if/else` statements.

# Swichin' it up!

Sometimes, we can use a `switch/case` statement to replace several `if/else` statements. Let's say we are categorizing our amusement park patrons into "adult", "youngster" (just short people, really), and everyone else.

## The teacups are fun, right?

We can use a `switch/case` statement to execute one or more statements based on a value:

```java
String ageGroup = "youngster";

switch (ageGroup) {
case "adult":
	System.out.println("You can ride the rollercoaster!");
case "youngster":
	System.out.println("The teacups are fun.");
	break;
default:
	System.out.println("Oh, you must be a toddler. Toddle on!");
}
```

What is displayed if we change `ageGroup`'s value to "adult"? Why?

What is displayed if we change its value to anything other than "adult" or "youngster"? Why?
