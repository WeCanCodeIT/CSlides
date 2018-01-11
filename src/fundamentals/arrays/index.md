title: Arrays
subtitle: Data Structures
theme: league

## Let's talk about Data Structures

- In the field of computing, programmers use <mark>Data Structures</mark> to store and manipulate data.

- Some examples of the more commonly used data structures are as follows: Arrays, Lists, Dictionaries(Hash Tables), Queues, Stacks

- In this lecture we will focus solely on <mark>Arrays</marks>, but we will take a few minutes to introduce you to the rest.

- A <mark>list</mark> is a data strucuture which holds variables in a specific order. 

- Lists are dynamically sized, meaning you do not have to specify the size of the list, and the list can grow as needed.

- Lists are created, accessed and manipulated in much the same way we create, access and manipulate arrays.

- We will go into depth on lists in a future lecture.

## Dictionaries... No not Websters

- Dictionaries, or as they are commonly referred, Hash Tables, are an extended/advanced array. 

- Like a list, dictionaries are dynamically sized, meaning you do not have to specify the size of the dictionary, and the dictionary can grow as needed.

- Unlike arrays or lists in which we only store the data values, in Dictionaries we can also store a key along with a value. This is commonly referred to as a <mark>KeyValuePair</mark>.

- We can also store to the <mark>KeyValuePairs</mark> as different data types. Meaning the Key can be an int, while its value can be a string.

- We will see in a future lecture how to create, access and manipulate Dictionaries, although they will not be the focus of our data structure teaching efforts

## Queues 

- You may have heard this term before if you have ever used a computer to print a document.

- Unlike arrays, lists and dictionaries, the data in a queue cannot be accessed by index. Meaning we cannot choose which piece of data we want to access and write code to directly get to it.

- Queues are commonly refered as <mark>FIFO</mark> or <mark>First In First Out</mark> data structure.

- This course will not go into queues any deeper than this mention. I would encourage you to do some more research to broaden your knowledge on queue operation.

<div class="fragment">
Question time: What are some examples you might be aware of where we might use a Queue?
</div>

## Stacks

- Stacks and queues are similar in many ways with the following exceptions:

	- As we discussed, queues are a <mark>FIFO</mark> data structure, while stackes are <mark>LIFO</mark> data structure.

	- Stacks are accessed and manipulated by <mark>popping and pushing</mark> while queues use <mark>Enqueue() and Dequeue().

- There are many uses for stacks in programming, and I would challenge you to do some further research.

- This course will not go into stacks any deeper than this mention. I would encourage you to do some more research to broaden your knowledge on stack operation.

	 

## Arrays

- Arrays allow us to store a sequence of values of a given type. 

- This could be items on a menu, lottery numbers, or the birds in your menagerie.

- Let's liken our Array to a sequence of cups. This is a pretty good analogy.

- Each of these "cups" in an array holds a value, which we call an *element*. 

- We reference a specific element using its *zero-based index*. 

- It's important to remember the index values of an Array and all other data strutures you will encounter will <mark>START WITH 0</mark>.

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
.img:hover  {
        transform: scale(1.5);
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    }
</style>

# Declaring an Array

- Remember, when we want to create an variable, we declare that variable.

- We use the same process to create an array.

- We declare an array by using the following syntax in C#. 

```C#
int[] cupValues = new int[5];
```

- We include the number of elements it will hold or its size in the square brackets. 

- Likewise we include the use the <mark>new</mark> keyword.

- The <mark>new</mark> keyword tells C# to declare the new array and initialize or set the array elements to their default values.

!SLIDE

- In our example below we can see the left side of the <mark>=</mark> operator is used to declare an int <mark>array</mark> named <mark>cupValues</mark>.

- The right side of the <mark>=</mark> operator will create a space in memory for the <mark>5</mark> elements, and assign those elements the default value of <mark>0</mark>.

```C#
int[] cupValues = new int[5];
```

<div class="fragment">
Question time: What type of array are we declaring?
</div>

<div class="fragment">
Question time: What are the index values for our array?
</div>

## Back to Hello World

- 

- Open your <mark>Hello World</mark> project from last week.

- We should all be here.

<div class="img" float="right"><img src="./resources/arr1.png" /></div>

- Let's start by commenting out our previous code.

- Because the march to battle will be long, we need to create a list of food items which the cooks will need bring.

- We will create an array and assign that array values.
 
# Assigning Values

- Before we can create our array, we need to know what item names we will store as elements. They are as follows:

	- Milk, Fruit, Meat, Wine, Bread.

- By looking at our items we can tell our array should be a <mark>string</mark> array.

- Based on the number of items in our list, its safe to assume our array should be <mark>5</mark> elements long.

- Let's get two volunteers to construct our array on the white board.

<div class="fragment">
This is what our code should look like: <mark>string[] foodList = new string[5];</mark>
</div>

<div class="fragment">
<p>Add the following code below the end of part eleven.</p>
<pre><code class="language-C#" data-noescape>
        //Part twelve array examples
        string[] foodList = new string[5];
</code></pre> 
</div>

!SLIDE

- Now that we have declared and initialized our string array called foodList, let's assign our values to the array.

- There is more than one way to assign values to an array. We initialized an empty array, so we will need to write some code to assign our values.

- When we want to assign values to an array, we must specify the following:

	- The <mark>name</mark> of the array.

	- The <mark>index</mark> we want to access.

	- The <mark>value</mark> we want to place at that <mark>index</mark>

- Let's start at index <mark>0</mark>.

<div class="fragment">
<p>Add the following highlighted code.</p>
<pre><code class="language-C#" data-noescape>
string[] foodList = new string[5];
<mark>foodList[0] = "Milk";</mark>
</code></pre> 
</div>

<div class="fragment">
If we print <mark>foodList[0]</mark> to the console we can see what the value is of the element at index 0. What is the command we would use?
</div>
<div class="fragment">
Please add <mark> Console.WriteLine(foodList[0]);</mark> to your code then execute.
</div>

## We should all be here

<div class="img" float="right"><img src="./resources/arr2.png" /></div>

- It's important to understand <mark>foodList[0]</mark> is acting as a variable, and the information we are accessing is at index 0.

- Let's finish assigning values to our array. Let's get two more volunteers to whiteboard our solution.

!SLIDE

<p>Add the following highlighted code.</p>
<pre><code class="language-C#" data-noescape>
string[] foodList = new string[5];
<mark>foodList[0] = "Milk";</mark>
<mark>foodList[1] = "Fruit";</mark>
<mark>foodList[2] = "Meat";</mark>
<mark>foodList[3] = "Wine";</mark>
<mark>foodList[4] = "Bread";</mark>
<mark>Console.WriteLine("{0}, {1}, {2}, {3}, {4}", foodList[0], foodList[1], foodList[2], foodList[3], foodList[4]);</mark>
</code></pre> 

<div class="fragment">
Question time: What is the term for the formatting of the Console.WriteLine() method?
</div>

<div class="fragment">
Execute your code
</div>

## We should all be here

<div class="img" float="right"><img src="./resources/arr3.png" /></div>

- Now that we have seen how to work with an empty array, let's look at creating a new array with the indices initialized with preset values.

- Let's enter into another array the amount of each food item: Milk 1000 gallons, Fruit 100 cases, Meat 2000 pounds, Wine 10000 gallons, Bread 1500 loaves

!SLIDE

<p>Add the following code and execute.</p>
<pre><code class="language-C#" data-noescape>
int[] foodAmount = new int[] { 1000, 1000, 2000, 10000, 1500 };
Console.WriteLine(foodAmount[0] + ", " + foodAmount[1] + ", " + foodAmount[2] + ", " + foodAmount[3] + ", " + foodAmount[4]);
</code></pre> 

- Here is our output

<div class="fragment">
<div class="img" float="right"><img src="./resources/arr4.png" /></div>
</div>


## Let's ponder our journey

- We have now learned two ways to create and initialize an array. We will learn one more when we discuss <mark>loops</mark>.

- One thing to remember, arrays are very efficient, but their size is fixed. 

- If we wanted to change the number of items in our foodList, I'd need to create a new array, assign it to my variable, then repopulate all the values.

- Like a value type variable or a string, once we declare them, all we need to do is assign new values. Let's review how to accomplish array assignment.

<div class="fragment">
<pre><code class="language-C#" data-noescape>
string[] foodList = new string[5];
<mark>foodList[0] = "Milk";</mark>
<mark>foodList[0] = "Fire";</mark>
</code></pre> 
</div>

<div class="fragment">
Question time: After we execute the code, whats the value of <mark>foodList[0]</mark>?
</div>

# How Big Is It?

- Often, it's important to know the size of an array. How many items does our foodList have?

- If you remember back to our strings lecture, we could use the <mark>.Length</mark> property to get the number of <mark>chars</mark> in a string or the length of the string..

- When we think of arrays, we can also think of the <mark>.Length</mark> property to get the number of <mark>indices</mark> in a array.

<div class="fragment">
<pre><code class="language-C#" data-noescape>
<mark>Console.WriteLine(foodList.Length);</mark>
</code></pre> 
</div>

<div class="fragment">
Question time: If we execute this code, what value do you think will be returned?</mark>
</div>

## Splitting Strings

- C# has some built-in methods which give us the ablity to convert sentences and words to arrays.

- We have learn sentences are comprised of groups of strings, and strings are comprised of groups of chars.

- Lets look at two methods which will make our coding more efficient and clean.

- `Split` is the first of the two methods we will discuss.

- Split allows us to split a sentence into an array of `string`s. 

- Split accepts one argument, which is the delimiter it should use to split the `string`.

- Examples of delimiters are as follows: . , ;  ? + -

## Let's dive deeper

- The <mark>Split</mark> method splits a collection of words based on a delimiter(s) and inserts each word into an array as an element.

- We can <mark>Split</mark> on multiple delimiters. 

- Insert the following code into your Hello World program and then execute.

```C# 
string[] elements = messageTwo.Split('<mark> </mark>');
Console.WriteLine(elements[0]); // prints "I"
Console.WriteLine(elements[1]); // prints "am"
Console.WriteLine(elements[2]); // prints "Spartacus"
```
<div class="fragment">
Question time: On what type of delimiter are we splitting our string?</mark>
</div>

<div class="fragment">
What is the value of `elements.Length`?
</div>

## Looking at characters

<div class="img" float="right"><img src="./resources/arr4.png" /></div>

 - We have talked about `string`s as sequences of characters. 
 
 - Now we have the tools to treat them that way. 
 
 - String has a `ToCharArray()` method that returns an array of `char`s:

```C#
String myName = "Sue";
char[] letters = myName.ToCharArray();
```

Console.WriteLine("The first letter of my name is " + letters[0]);
!SLIDE

- A related method is `IndexOf`, which returns the first index of a character:

```C#
String myName = "Sue";
char[] letters = myName.ToCharArray();

Console.WriteLine(myName.IndexOf('S')); //prints "0"
Console.WriteLine("foo".IndexOf('o')); //prints "1"
```
- Another version of the `IndexOf` method (this is called *overloading*) will accept a `string`:

```C#
Console.WriteLine("fee, fie, foe, fum".IndexOf("foe")); //prints "10" 
```
<div class="fragment">
Why is the index value 10?
</div>


