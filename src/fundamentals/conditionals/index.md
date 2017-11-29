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
<p>In C#, we would say:</p>
<pre><code class="language-C#">int age = 42;
if (age >= 16) {
  Console.WriteLine("You are " + age + ", so you are legal to drive.");
}</code></pre>
</div>

<div class="fragment">
Question time: What do think would happen if age == 15?
</div>
## We might say…

*If* I get eight or more hours of sleep, I am likely to feel more rested.

<div class="fragment">
<p>In C#, we would say:</p>
<pre><code class="language-C#">int hoursOfSleep = 42;
if (hoursOfSleep >= 8) {
  Console.WriteLine("You are likely to feel more rested.");
}</code></pre>
</div>

<div class="fragment">
Question time: What would happen if we changed the condition statement to read (hoursOfSleep !> 8)?
</div>

<div class="fragment">
<p>We can follow one conditional with another.</p>
<pre><code class="language-C#">if (hoursOfSleep == 42) {
  Console.WriteLine("He used 42 again, didn't he?");
 }
 if(hoursOfSleep == 52){
   Console.WriteLine(hoursOfSleep + "Aint such a bad number");
 }
 </code></pre>
</div>
<div class="fragment">
Question time: What do you think would happen if hoursOfSleep == 42?
</div>
<div class="fragment">
Question time: What do you think would happen if hoursOfSleep == 52?
</div>
<div class="fragment">
Question time: What do you think would happen if hoursOfSleep == 102?
</div>

## So let break down the 'if' statement!!

An `if` statement starts with the keyword `if`:
<pre><code class="language-C#" data-noescape>int heightInInches = 73;

<mark>if</mark>(heightInInches >= 60) {
  Console.WriteLine("You are tall enough to ride");
}</code></pre>

## Next comes the decision

'if' is then followed by parentheses that contain a *condition*:
<pre><code class="language-C#" data-noescape>int heightInInches = 73;

if<mark>(</mark>heightInInches >= 60<mark>)</mark> {
  Console.WriteLine("You are tall enough to ride");
}</code></pre>

## Lets think through an example

```C#
int heightInInches = 73;

if(heightInInches >= 60) {
  Console.WriteLine("You are tall enough to ride");
}
```
<div class="fragment">
Question time: If we sent the result of the conditional statement (heightInInches >= 60) to the console, what do you think we would see?
</div>


## Lets code it and see what results returned if any!

```C#
int heightInInches = 73;

    if (heightInInches >= 60)
    {
        Console.WriteLine("You are tall enough to ride");
    }
		Console.WriteLine("You are to short to ride);
		Console.WriteLine(heightInInches >= 60);
```

<div class="fragment">
Question time: What results did you get and were the results what you expected?
</div>
<div class="fragment">
Question time: What data type do you think is represented with the answer you received?
</div>

## Lets try again

Change the value of heightInInches to 42
 
<pre><code class="language-C#">int heightInInches = 42;

if(heightInInches >= 60) {
  Console.WriteLine("You are tall enough to ride");
}
	Console.WriteLine("You are to short to ride);
    Console.WriteLine(heightInInches >= 60);

</code></pre>

<div class="fragment">
Question time: What results did you get and were the results what you expected?
</div>
<div class="fragment">
Question time: Again, what data type do you think is represented with the answer you received?
</div>

## We want the truth!!... Or Not!!

As we have seen the *condition* evaluates to a `boolean` value:
<pre><code class="language-C#" data-noescape>int heightInInches = 73;

if(<mark>heightInInches >= 60</mark>) {
  Console.WriteLine("You are tall enough to ride");
}</code></pre>

## Ok where does all the work take place?

This is followed by a code block that executes only if the *condition* is `true`. Remember that code blocks open with a left curly bracket (`{`) and close with a right curly bracket (`}`):
<pre><code class="language-C#" data-noescape>int heightInInches = 73;

if(heightInInches >= 60) <mark>{</mark>
  Console.WriteLine("You are tall enough to ride");
<mark>}</mark></code></pre>

<pre><code class="language-C#" data-noescape>int heightInInches = 73;

if(heightInInches >= 60) 
  Console.WriteLine("You are tall enough to ride");</code></pre>

## Else what?

It's polite to offer an apology, eh? We can be polite.

An `if` statement allows us to do something else if its *condition* does not evaluate to `true`:

<pre><code class="language-C#" data-noescape>int heightInInches = 42;

if(heightInInches >= 60) {
  Console.WriteLine("You are tall enough to ride.");
} else {
  Console.WriteLine("I'm sorry, too short.");
}</code></pre>

## And then?

We can create sequences of `if/else` statements:

```C#
if(heightInInches >= 60) {
  Console.WriteLine("You are tall enough to ride.");
} else if(heightInInches >= 30) {
  Console.WriteLine("Try the teacups. They look fun.")
} else {
  Console.WriteLine("I'm sorry, too short.");
}
```

Think of this as connecting multiple `if/else` statements.

# Swichin' it up!

Sometimes, we can use a `switch/case` statement to replace several `if/else` statements. Let's say we are categorizing our amusement park patrons into the following groups based on their ageGroup:adult, youngster, and everyone else.

## The teacups are fun, right?

We can use a `switch/case` statement to execute one or more statements based on a value:

```C#
String ageGroup = "youngster";

switch (ageGroup) {
case "adult":
	Console.WriteLine("You can ride the rollercoaster!");
	break;
case "youngster":
	Console.WriteLine("The teacups are fun.");
	break;
default:
	Console.WriteLine("Oh, you must be a toddler. Toddle on!");
}
```
<div class="fragment">
What is displayed if we change `ageGroup`'s value to "adult"? Why?
</div>
<div class="fragment">
What is displayed if we change its value to anything other than "adult" or "youngster"? Why?
</div>
<div class="fragment">
What functions does the 'break' statement perform?
</div>

## Lets switch it up a little

 You are getting ready to take a trip to Columbus for work. You were thinking about all the items you should pack. 

 You need to base the items you will take on the current tempurature in Columbus Oh.

 Write a 'swtich' statement that will use the currentTemp in Columbus, Oh to decide which of the following you should bring: Parka, Down Feather Jacket, PCoat, sweater.