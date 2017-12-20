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

```C#
int[] oldArray = myArray;

myArray = new int[4];
for(int index = 0; index < oldArray.Length; index++) {
  myArray[index] = oldArray[index];
}
myArray[3] = 42;
```

We are forced to create a new array and assigned it to our `myArray` variable. Imagine if we needed to insert a new element in the middle? *Yuck!*

## Let's Start a New Project

Create a new Console Application with the title "ToyStore"

<div float="right"><img src="./resources/createproject.jpg" /></div>

## Array Review

This is how we'd set up an array of toys at our toy store. Remember, arrays have a fixed size.

<div float="right"><img src="./resources/toyarray.jpg" /></div>

## How To Initialize a List

A list is created with the <mark>new</mark> keyword, which we will see a lot more of soon!

Create the following list.

<div float="right"><img src="./resources/toylist.jpg" /></div>

Notice the similarities and differences between creating a new List versus creating an array.

## Initializing an Empty List

Unlike arrays, with lists we don't have to set a size when we create an empty list.

<div float="right"><img src="./resources/newEmptyList.jpg" /></div>

## Mutable

Unlike an array, a List is mutable, meaning that it does not have a fixed size and can increase or decrease in size.

We can use the <mark>.Add()</mark> method to add elements to our list.

<div float="right"><img src="./resources/addToToyList.jpg" /></div>

<div class="fragment">
What did our `foreach` loop do?
</div>

## Printing Elements in a List

We saw what the `foreach` loop did in our previous slide. There is another way to print elements in a list using their indices.

<div float="right"><img src="./resources/PrintAtIndex.jpg" /></div>

## Objects and Methods

We will be talking a lot more about objects this week, but it is good for you to know that Lists are a type of object.

Lists have several built-in properties and methods, which we will go over now. Some of those are:
 - .Count
 - .Insert()
 - .Add()
 - .Remove()

## Count and Remove

The .Count property is the List-version of the .Length property that is built in to arrays. .Count tells us the size of the list.

Write out the following code and share what you discover about .Remove().

<div float="right"><img src="./resources/CountAndRemove.jpg" /></div>

## Insert

The .Insert() method allows us to put a new element in our list AND specify which index we want that element to go to. Take a look at the following code.

<div float="right"><img src="./resources/InsertMethod.jpg" /></div>

<div class="fragment">
What index is each element at?
</div>
<div class="fragment">
Where did the elements originally at the indices of 0, 2, and 1 go?
</div>

## Contains

Another built-in method with Lists is the .Contains() method. .Contains() checks for a value in a list and returns a boolean value.

We can use methods inside of loops and conditionals. Write out the example below:

<div float="right"><img src="./resources/ConditionalAndContains.jpg" /></div>

<div class="fragment">
What result did you expect? What method that we've learned can we use to change the result?
</div>

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