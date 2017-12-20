title: Lists
subtitle: Like Arrays, but Mutable!
theme: league

# Data Collections

We have already seen one data collection type, an `array`. An `array` is a collection of values that have the same type, like `int` or `string`.

There are several types of data collections in C#, many of which you will see during the upcoming weeks and even more during final projects.

Today, we will be talking about `Lists`.

## Arrays are fixed size

We can't change the size of an array once we've created it. It will never grow or shrink. This array will always have a `length` of three:

<code class="language-C#" data-noescape>
int[] myArray = {1, 2, 3};
</code>

If I wanted to add an element to this array, I'd generally do something like this (but hopefully I'd use a loop):

<code class="language-C#" data-noescape>
int[] oldArray = myArray;

myArray = new int[4];
for(int index = 0; index < oldArray.Length; index++) {
  myArray[index] = oldArray[index];
}
myArray[3] = 42;
```

We are forced to create a new array and assigned it to our `myArray` variable. Imagine if we needed to insert a new element in the middle? *Yuck!*

## Lists can grow and shrink

`ArrayList` is a standard class, so we create an *instance* of it just like any class we'd create:
```C#
List<string> giantWords = new List<string>();
giantWords.add("fee");
giantWords.add("fie");
giantWords.add("foe");
foreach (string word in giantWords)
{
	Console.WriteLine(word);
}
Console.WriteLine("my list has " + giantWords.Count + " elements");

giantWords.add("fum");
foreach (string word in giantWords)
{
	Console.WriteLine(word);
}
Console.WriteLine("my list has " + giantWords.Count + " elements");
```

I'm not even forced to specify the size! The `Count` property tells me how big my list currently is.


## Let's Start a New Project

Create a new Console Application with the title "ToyStore"

<div float="right"><img src="./resources/createproject.jpg" /></div>

## Primitives except when they ain't

A limitation of these type parameters is that they can only be objects. We can't put primitives like `int`s into an `ArrayList`. Wouldn't get very far if we didn't have a workaround, would we?

For each of the primitive types, Java has a corresponding class to create full-fledged objects to represent that value. These are found in the `java.lang` package, like `String`, so we don't need `import` statements for them:

|primitive	|class
|---------	|-----
|boolean	|Boolean
|char		|Character
|int		|Integer
|long		|Long
|double		|Double
|short		|Short
|byte		|Byte
|double		|Double
|float		|Float

Remember our naming conventions? Classes start with an uppercase letter.

## That's starting to sound ugly!

It's not as bad as you may think. Java does something called *autoboxing* to automatically convert between primitives and objects, so I can do this:

```java
ArrayList<Integer> answers = new ArrayList<Integer>();
int ultimateAnswer = 42;
answers.add(ultimateAnswer);
answers.add(86);

System.out.println("The answers are: " + answers);

Integer asIntegerObject = ultimateAnswer;
System.out.println("The ultimate answer is " + asIntegerObject);
```

When you need an object, Java will "box" your primitive. When you need a primitive, Java will "unbox" your object.

## Objects like any other

The way we use `ArrayList`s is the same as we would use any other class. We create an instance of it, then we call methods (send messages) to ask it to modify itself or give us information.

## How big is it?

We've already seen the `size` method in use. It corresponds to `length` for an array.

To check whether an array is empty, we would compare its `length` to zero:

```java
if(myArray.length == 0) {
  System.out.println("I'm empty!");
}
```

We can ask an `ArrayList` whether it's empty:
```
ArrayList<Integer> answers = new ArrayList<Integer>();
System.out.println("Are you out of answers? " + answers.isEmpty());
```
Try adding something to yours and see how the response changes.

## Do you have one of these?

If we wanted to check whether an array contained an element, we would iterate over it, checking each element:

```java
String[] myTools = { "hammer", "shovel", "wrench" };
for(String tool: myTools) {
  if(tool.equals("hammer")) {
    System.out.println("I have a hammer!");
  }
}
```

`ArrayList` has a `contains` method for this:

```java
ArrayList<String> myTools = new ArrayList<String>();
myTools.add("hammer");
myTools.add("shovel");
myTools.add("wrench");

if(myTools.contains("hammer")) {
  System.out.println("I have a hammer!");
}
```

## Where is it?

If I want to know the index of an element in an array, it's a bit painful:

```java
String[] myTools = { "hammer", "shovel", "wrench" };
for(int index = 0; index < myTools.length; index++) {
  if(myTools[index].equals("shovel")) {
	  System.out.println("Shovel is element " + index);
  }
}
```

With an `ArrayList`, we have the `indexOf` method:

```java
ArrayList<String> myTools = new ArrayList<String>();
myTools.add("hammer");
myTools.add("shovel");
myTools.add("wrench");

System.out.println("Shovel is element " + myTools.indexOf("shovel"));
```

*Look, ma! No curly brackets!*

## Order is important

Arrays remember the order in which you `add` elements. Other types of collections don't care so much, but order is one of the intrinsic properties of a list. Try running this code, then changing the order of the `add` calls and running it again:

```java
ArrayList<String> giantWords = new ArrayList<String>();
giantWords.add("fee");
giantWords.add("fie");
giantWords.add("foe");
System.out.println(myList);
```

## Loopy again

Like arrays, an `ArrayList` is *iterable*, so we can use the enhanced for loop with it:
```java
ArrayList<String> giantWords = new ArrayList<String>();
giantWords.add("fee");
giantWords.add("fie");
giantWords.add("foe");

for(String word: giantWords) {
  System.out.print(word + "! ");
}
System.out.println();
```

## More Tools

`ArrayList` has a number of other useful methods. The examples assume our list was created like so:

```java
ArrayList<String> myThings = new ArrayList<String>();
myThings.add("this");
myThings.add("that");
myThings.add("the other");
```

Here are some other methods we can use:

|method			|example				|what it does
|----------		|---------				|------------
|`clear()`		|`myThings.clear();`	|removes all the elements
|`set(int index, String element)`	|`myThings.set(1, "foo");`	|assigns "foo" to index 1, replacing "that":<br>"this", "foo", "the other"
|`add(int index, String element)`	|`myThings.add(1, "foo");`	|inserts "foo" at index 1, shifting the others down to make room:<br>"this", "foo", "that", "the other"
|`remove(int index)`	|`myThings.remove(1);`	|removes the element at index 1:<br>"this", "the other"
|`remove(Object o)`		|`myThings.remove("that");`	|removes the value from the list:<br>"this", "the other"

## Exploring `ArrayList`

As you move into exercises, you'll be inclined to dig into the `ArrayList` class. You might not find what you expect. As part of the Collections framework, `ArrayList` is just one piece of the puzzle. You'll find that some of the methods we're using aren't even *in* `ArrayList`!

That's because `java.util.ArrayList` *is a* specific type of `java.util.List`, which in turn *is a* type of `java.lang.Iterable`.

This is called inheritance. `ArrayList` *inherits* from its parent class and interfaces. More on that later.

## A method by any other name…

Notice the convention we're seeing with methods. It's a good one to follow when you create your own methods. Generally, a method should be doing something or giving us information, not both. It's a good practice to use verbs for methods that do things, and nouns for methods that give us information. It is also common to see methods whose names start with `get` or `is` that give us information.

## Not all bad

When might we use an array rather than an `ArrayList`?

## Do It!

- Create an `ArrayList`. Add five animals to your list. Print each animal in your list.

- Create a list that contains the following boolean values: `true`, `false`, `false`, `true`, `false`. Loop through your list. Based on the value of each element, print a message:
	- `true`: "Better bring an umbrella"
	- `false`: "No rain today, enjoy the sun!"

- Create a list with the following numbers: 1, 23, 9, 77, 922, 6, 32, 63, 14, 5, then:
	- determine whether each of the following values is an element in the list: 23, 77, 15
	- remove the following elements: 27, 922, 32, 6
	- again determine whether each of the following values is an element in the list: 23, 77, 15 (*Stretch: create a method so that you don't need to duplicate this work.*)
  
- Come up with an example of how you might use each of the methods from the "More Tools" slide.