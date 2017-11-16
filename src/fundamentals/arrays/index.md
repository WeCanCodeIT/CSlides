title: Arrays
subtitle: •••
theme: league

## What Are They?

Arrays allow us to store a sequence of values of a given type. This could be items on a menu, lottery numbers, or the birds in your menagerie.

*Head First Java* likens them a sequence of cups. This is a pretty good analogy.

Each of these "cups" in an array holds a value, which we call an *element*. We reference a specific element using its zero-based *index*.

<div class="cups">
	<div><p class="row-label">Element →</p></div>
	<div class="cup"><p>42</p></div>
	<div class="cup"><p>86</p></div>
	<div class="cup"><p>23</p></div>
	<div class="cup"><p>8</p></div>
	<div class="cup"><p>91</p></div>

	<div><p class="row-label">Index →</p></div>
	<div><p>0</p></div>
	<div><p>1</p></div>
	<div><p>2</p></div>
	<div><p>3</p></div>
	<div><p>4</p></div>
</div>

<style type="text/css">
div.cups {

	display: grid;
	grid-template-columns: max-content repeat(5, 10rem);
}

div.cups .row-label, div.cups .cup {
	font-weight: bolder;
}

div.cups > div {

	height: 6rem;

	text-align: center;
	vertical-align: middle;
}

div.cups .row-label {
	text-align: right;
}

div.cups .cup {

	color: var(--background-color);

	background: no-repeat center url(./resources/cup.png);
	background-size: contain;
}
</style>

# Declaring an Array

We declare an array using a syntax that we won't see elsewhere in Java. We follow the type of elements it will hold with its size (the number of elements it will hold) in square brackets. Also, we use the `new` operator in a different way.

To create an array destined to hold the values of our cups from the previous example, we would do this:

```java
int[] cupValues = new int[5];
```

This creates an array of type `int` whose name is `cupValues`. It has five elements.

# Assigning Values

Remember our cups?

<div class="cups">
	<div><p class="row-label">Element →</p></div>
	<div class="cup"><p>42</p></div>
	<div class="cup"><p>86</p></div>
	<div class="cup"><p>23</p></div>
	<div class="cup"><p>8</p></div>
	<div class="cup"><p>91</p></div>

	<div><p class="row-label">Index →</p></div>
	<div><p>0</p></div>
	<div><p>1</p></div>
	<div><p>2</p></div>
	<div><p>3</p></div>
	<div><p>4</p></div>
</div>

We use array indices (that's the plural of index) to assign values to elements. This is how we'd declare our array and assign element values:

```
int[] cupValues = new int[5];
cupValues[0] = 42;
cupValues[1] = 86;
cupValues[2] = 23;
cupValues[3] = 8;
cupValues[4] = 91;
```

## Change can be painful

Arrays are very efficient, but their size is fixed. If I wanted to change the number of cups, I'd need to create a new array, assign it to my variable, then repopulate all the values:

```
cupValues = new int[2];
cupValues[0] = 42;
cupValues[1] = 86;
```

Notice I didn't *declare* `cupValues` again. I merely reassigned a new array to it. We will look at `List`s and `Collection`s later, types in Java that are more flexible.

# Retrieving Values

To retrieve values, we use a syntax like we used to assign values:

```java
System.out.println(cupValues[0]); // prints "42"
System.out.println(cupValues[1]); // prints "86"
System.out.println(cupValues[2]); // prints "23"
System.out.println(cupValues[3]); // prints "8"
System.out.println(cupValues[4]); // prints "91"
```

# How Big Is It?

Often, it's important to know the size of an array. How many cups do I have?

To do this, we use the `length` property, like so (notice that dot operator):

```java
int[] cupValues = new int[5];
int numberOfCups = cupValues.length;
System.out.println(numberOfCups); // prints "5"

cupValues = new int[2];
System.out.println(cupValues.length); // prints "2"
```

What is the value of `numberOfCups` after we run this code?

## Revenge of the Curly Brackets

We can also initialize an array with values. We do this using curly brackets to surround a comma-delimited list of values, like so:

```java
String[] giantWords = { "fee", "fie", "foe", "fum" };
```

Note that we also do not include the *size* of the array. Java figures this out based on the number of values we provide.

<div class="fragment sidebar"><img src="./resources/wat.jpg" alt="WAT?" /></div>

This creates a String array with these values:

|index	|value	|reference
|-------|-------|---------
|0		|"fee"	|`giantWords[0]`
|1		|"fie"	|`giantWords[1]`
|2		|"foe"	|`giantWords[2]`
|3		|"fum"	|`giantWords[3]`

… and these curly brackets aren't defining a code block. By now, you're probably thinking…

## There's more than one way…

When we do this:

```java
String[] giantWords = { "fee", "fie", "foe", "fum" };
```

It is equivalent to doing this:

```java
String[] giantWords = new String[4];
giantWords[0] = "fee";
giantWords[1] = "fie";
giantWords[2] = "foe";
giantWords[3] = "fum";
```

We can *initialize* an array with this syntax, but we can't use it to later assign it new values. This is because array sizes are fixed (can't change), and Java wouldn't be able to check when compiling our code.

## Let's Do It Together

If we needed to create a class roster, would an array be appropriate? How would we go about it?

## Now You Do It!

- For each of the following, create an array, assign its values, then print out those values:
	- The names of three people you know.
	- The GPAs on a 4.0 scale of five students.
- Create an array of your top four vacation spots, then print the top (first) spot and the bottom (last spot).
- Create a `String` that holds your last name. Print out the number of letters in your name.

## And then and then and then…

There are some useful methods of `String` which *return* arrays.

### Splitting Strings

`split` is one of them. It allows us to split a `String` into an array of `String`s. It accepts one argument, which is the delimiter it should use to split the `String`:

```java
String source = "this, that, the other";
String[] elements = source.split(", ");

System.out.println(elements[0]); // prints "this"
System.out.println(elements[1]); // prints "that"
System.out.println(elements[2]); // prints "the other"
```

What is the value of `elements.length`?

*Note: technically, the `split` method accepts a* regular expression, *pretty powerful stuff, but you can just think of it as a `String` for now.*

!SLIDE

### Looking at characters

We have talked about `String`s as sequences of characters. Now we have the tools to treat them that way. `String` has a `toCharArray` method that returns an array of `char`s:

```java
String myName = "Sue";
char[] letters = myName.toCharArray();

System.out.println("The first letter of my name is " + letters[0]);
```

A related method is `indexOf`, which returns the first index of a character:
```java
System.out.println(myName.indexOf('S')); //prints "0"
System.out.println("foo".indexOf('o')); //prints "1"
```

Another version of the `indexOf` method (this is called *overloading*) will accept a `String`:
```java
System.out.println("fee, fie, foe, fum".indexOf("foe")); //prints "10"
```

## A Little Wonky

Before teaching a bootcamp, I… *uhhh*… I mean a *friend* of mine often had to look up the syntax for arrays because they're not really like other things in Java.

Arrays are objects, but they don't conform to all the rules of other objects. They are special snowflakes. 

Some differences to be aware of:

- We create them using the `new` operator, but we don't use a *constructor* method like we would with other objects.
- Their values can be initialized with a creative (confusing) use of curly brackets.
- We can't call methods on them (at least not directly).
- We use square brackets to both declare arrays and to access element values, something we won't see elsewhere.

## Work It

- Create an array holding the names of four of your peers sitting next to you. Print the first letter of each of their names.
	- Change your code (or create more code) that asks you to enter each of their names via the console.

- Create a console application that asks you to enter a word and then a letter. Print out either "Yep, it's got one of those" or "So, sorry", depending on whether the word contains that letter.

- Create a `String` representing a list of things that uses some delimiter (commas, dashes, etc). Split that `String` into an array of `String`s, then print one or more of these array elements.
	- Stretch Task: research *regular expressions*, and allow the use of either of two delimiters to split the `String`. (Either a comma *or* a dash, for example.)