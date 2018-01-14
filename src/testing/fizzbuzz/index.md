title: FizzBuzz Review
subtitle: 1… 2… Fizz! 4… Buzz!
theme: league

# Rules of Testing
- **First Rule**: You can write no production code except to pass a failing test case
- **Second Rule**: You can only write enough of a test case to demonstrate a failure
- **Third Rule**: You can only write enough production code to pass the currently failing test case

# FizzBuzz Kata

## FizzBuzz Game
- "Fizz" if a number is divisible by 3
- "Buzz" if a number is divisible by 5
- "FizzBuzz" if a number is divisible by 3 and 5
- Otherwise, show the number (let's show the number as a String)

## Project Setup
- Open Visual Studio and create a new Solution called `FizzBuzz`.
- Add a Class Library to the solution and name it `FizzBuzz.Tests`.
- Create a class named `FizzBuzzerTests` inside the `FizzBuzz.Tests` class library project.
- Add the `NUnit` Nuget package to your `FizzBuzz.Tests` project.  W
- Add a reference from the `FizzBuzz.Tests` project to the `FizzBuzz` project.  This allows
code in the Test project to use code from the FizzBuzz project (we'll need to use it so we can test it!)

## Writing the first test scenario
```csharp
[TestFixture]
public class FizzBuzzerTests
{
	[Test]
	public void Get_Returns_1_for_1()
	{
		var fizzBuzzer = new FizzBuzzer();

		var result = fizzBuzzer.Get(1);

		Assert.That(result, Is.EqualTo("1"));
	}	
}
```

This code *will not compile* at this point because the `FizzBuzzer` class does not exist.

Why would we write code that doesn't compile? We're thinking from the outside in!  This is
one way that tests _drive_ your design.

## Getting Red

Let's write just enough code to get this to compile.

Create the `FizzBuzzer` class inside the `FizzBuzz` project.

```csharp
public class FizzBuzzer
{
	public string Get(int num)
	{
		return null;
	}
}
```

ctrl + u + l to run the test.  It will fail.  This is the Red step in the "Red, Green, Refactor" loop.

## Getting to Green

Let's follow the third rule by writing a minimal solution that gets us green again.

```csharp
public class FizzBuzzer
{
	public string Get(int num)
	{
		return "1";
	}
}
```

...and we're green!  Time for the most important step: _refactoring_!

## Red, Green REFACTOR

When we enter the refactor step, we should review all the code we've written to see if we can clean it up.

I don't see any way we can simplify this code, but it's a good habit to always pause for a moment and look
for anything you can do to clean up the code without changing it's behavior (refactoring).

## Adding the Next Test

Our current solution works for exactly 1 scenario: the number 1.  Let's write a test that will make it work for
some more inputs.

```csharp
[Test]
public void Get_Returns_2_for_2()
{
	var fizzBuzzer = new FizzBuzzer();

	var result = fizzBuzzer.Get(2);

	Assert.That(result, Is.EqualTo("2"));
}
```

Hit ctrl + U + L to run your tests.  Our old test should pass, but the new one will fail with a message like this:
```
  String lengths are both 1. Strings differ at index 0.
  Expected: "2"
  But was:  "1"
```

Our test expected to get the string `"2"`, but we always just return `"1"`.  Let's fix it.

```csharp
public class FizzBuzzer
{
	public string Get(int num)
	{
		return num.ToString();
	}
}
```

Hit ctrl + U + L to run all the tests again.  Both tests should be passing now

This solution works for every number that isn't a multiple of 3 or 5!  That's way better
than our old solution, which only worked for the number 1.

I don't see any refactoring we can do, so lets forge ahead.

## The Third Test - Introducing Multiples of 3

We could write a test for the number 4, but it would just immediately pass.  Let's pick a test
that will drive our solution closer to what we want.

If we add a test scenario for the number 3, we'll push our solution closed to handling multiples of 3.  

Let's do it.

```csharp
[Test]
public void Get_Returns_Fizz_for_3()
{
	var fizzBuzzer = new FizzBuzzer();

	var result = fizzBuzzer.Get(3);

	Assert.That(result, Is.EqualTo("Fizz"));
}

```
Run the test (ctrl + U + L) and watch it fail.  Check your error and make sure it makes sense:
```
  Expected: "Fizz"
  But was:  "3"
```
Yep, that's what we expected.  Our code doesn't handle multiples of three yet.  Let's fix that.

```csharp
public string Get(int num)
{
	if (num == 3)
	{
		return "Fizz";
	}
	return num.ToString();
}
```
Run it and see it pass.

This solution works for exactly one multiple of 3.  It's the simplest way to solve the test that's currently failing,
although we're obviously going to need to change that soon.

Can we refactor anything here?  Probably not.  Let's write a test that makes our solution work for more than just 3.

## The Fourth Test - Handling All Multiples of 3.

Let's use `6` to push our solution further along.

Write the test:
```csharp
public string Get(int num)
{
	if (num == 3)
	{
		return "Fizz";
	}
	return num.ToString();
}
```

Watch it fail:
```
  Expected: "Fizz"
  But was:  "6"
```

Make it pass:
```csharp
public string Get(int num)
{
	if (num % 3 == 0)
	{
		return "Fizz";
	}
	return num.ToString();
}
```

Refactor?  YES, PLEASE!

We don't have a lot of code, but it's important to clean as we go.  If I asked you what our code does right now, you would
probably say something like: 

<tab>"If we pass it a multiple of three it returns `"Fizz"`, 
<tab>otherwise it returns the input number as a string.".

Notice how our code doesn't really look like that?  Let's make it easier to read by extracting a method:

```csharp
 public class FizzBuzzer
{
	public string Get(int num)
	{
		if (IsMultipleOf3(num))
		{
			return "Fizz";
		}
		return num.ToString();
	}

	private bool IsMultipleOf3(int numberToCheck)
	{
		return numberToCheck % 3 == 0;
	}
}
```

Wow, that's actually more code!  Does that mean it's inferior?

Absolutely not.  By extracting that method we made the `Get` method much easier to understand.  You don't need
to wrap your head around the modulus operator (`%`) and what `num % 3 == 0` means.  We created a name for `num % 3 == 0` - `IsMultipleOf3`.

This raises the level of abstraction and makes the code easier read and easier to maintain.  This is _clean code_ - it doesn't burden us with 
details.  Instead, it assigns names to the details and tucks them away in a place where we can drill into the detail if needed, or ignore it
if we don't care.

## Solving for 5

How many tests do you think we'll need to write to make our code handle multiples of 5?

```csharp
[Test]
public void Get_Returns_Buzz_for_5()
{
	var fizzBuzzer = new FizzBuzzer();          // Arrange - Get ready.

	var result = fizzBuzzer.Get(5);             // Act - Do the thing you're testing.

	Assert.That(result, Is.EqualTo("Buzz"));    // Assert - Make sure it worked.
}
```

Don't forget to run it and see it fail (with the error you expected!)

Notice how every test follows a pretty predictable pattern of 3 lines of code?  We call these steps "Arrange, Act, Assert".  
It's a good practice to use blank lines to separate the three phases of each test. 

Let's make it pass.

```csharp
public string Get(int num)
{
	if (IsMultipleOf3(num))
	{
		return "Fizz";
	}
	if (num == 5)
	{
		return "Buzz";
	}
	return num.ToString();
}
```

Run it and see it go green.

Why didn't we write the `IsMultipleOf5` method?  And why didn't we use the modulus operator to solve for all multiples of 5?

Remember that when you have a red test, your goal is to write the _simplest thing_ that gets you back to green.

Let's hold off on refactoring until we get another test in there.

## Multiples of 5

Write the test:
```csharp
 [Test]
public void Get_Returns_Buzz_for_10()
{
	var fizzBuzzer = new FizzBuzzer();

	var result = fizzBuzzer.Get(10); 

	Assert.That(result, Is.EqualTo("Buzz"));
}
```

Watch it fail for the right reason:
```
  Expected: "Buzz"
  But was:  "10"
```

Make it pass:
```csharp
public string Get(int num)
{
	if (IsMultipleOf3(num))
	{
		return "Fizz";
	}
	if (num % 5 == 0)
	{
		return "Buzz";
	}
	return num.ToString();
}
```

Make it clean (Refactor):
```csharp
public string Get(int num)
{
	if (IsMultipleOf3(num))
	{
		return "Fizz";
	}
	if (IsMultipleOf5(num))
	{
		return "Buzz";
	}
	return num.ToString();
}
```

## Your turn

What's the next test we should write?  How many more tests do you think we need?
