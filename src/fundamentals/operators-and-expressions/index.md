title: Operators and Expressions
subtitle: •••
theme: league

# Lesson Goals

- Learn about the different operators and their functions.
- Become familiar with Java syntax.

## Write practice statements for the arithmetic operators

If variable *a* holds 10 and variable *b* holds 15, then:

|Operator|Operation|Description|Expression|Result
|--------|---------|-----------|------------------|------
|+|addition|adds two operands|`a + b`|25
|-|subtraction|subtracts second operand from the first|`a - b`|-5
|*|multiplication|multiplies the operands|`a * b`|150
|/|division|divides first operand by second operand|`b / a`|1
|%|modulus (remainder)|returns the remainder after integer division|`b % a`|5

## Write practice statements for the increment<br>and decrement operators

If variable *a* holds the value 42, then:

|Operator|Operation|Description|Expression|Equivalent to…|`a`'s value afterwards
|--------|---------|-----------|----------|----------------------
|++|increment|adds one to the value its `int` operand holds|`a++`|`a = a + 1`|43
|&#x02010;&#x02010;|decrement|subtracts one from the value its `int` operand holds|`a--`|`a = a - 1`|41

## Write practice statements for the equality operators

If variable *a* holds 10 and variable *b* holds 15, then:

|Operator|Operation|Description|Expression|Result
|--------|---------|-----------|------------------|------
|==|equal to|evaluates to true if the two operands are equal|`a == 10`<br>`a == b`|true<br>false
|!=|not equal to|evaluates to true if the two operands are *not* equal|`a != 10`<br>`a != b`|false<br>true

## Write practice statements for the relational operators

If variable *a* holds 10 and variable *b* holds 15, then:

|Operator|Operation|Description|Expression|Result
|--------|---------|-----------|------------------|------
|>|greater than|evaluates to true of the first operand is greater than the second operand|`a > b`|false
|>=|greater than or equal to|evaluates to true of the first operand is greater than *or equal to* the second operand|`a >= b`<br>`a >= 10`|false<br>true
|<|less than|evaluates to true of the first operand is less than the second operand|`a < b`|true
|<=|less than or equal to|evaluates to true of the first operand is less than *or equal to* the second operand|`a <= b`<br>`a <= 10`|true<br>true

## Write practice statements for the logical operators

If variable *a* holds `true` and variable b holds `false`, then:

|Operator|Operation|Description|Expression|Result
|--------|---------|-----------|------------------|------
|&&|conditional AND|evaluates to true if both operands are true;<br>otherwise, evaluates to false|`a && b`<br>`a && true`|false<br>true
|&#124;&#124;|conditional OR|evaluates to true if either operand is true;<br>otherwise, evaluates to false|`a || b`<br>`b || false`|true<br>false

% TODO TMI? Note that the conditional AND and OR are *short-circuit* operators.

# Translating English to Java

Let's translate English statements into Java. First, we'll do one together.

Start by writing the statements as comments. Here's an example:

```java
// Jessica is 23 years old.
int jessicaAge = 23;

// Sam is 47.
int samAge = 47;

// Jessica is younger than Sam.
System.out.println(jessicaAge < samAge);
```

## Let's break it down…

### Defining a variable to hold Jessica's age:

We need to create a variable to hold the age of Jessica. What should its type be?

<p><code class="language-java hljs"><span class="hljs-comment">// <span class="highlight">Jessica</span> is 23 <span class="highlight">years old</span>.</span></code></p>

<div class="fragment">
<p>Since we think of ages as whole numbers, we will use an <code>int</code>:</p>
<code class="language-java hljs"><span class="highlight"><span class="hljs-keyword ">int</span> jessicaAge</span></code>
</div>

## Let's break it down…

### Assigning a value for Jessica's age:

The word "is" means equals. How do we represent assignment?

<p><code class="language-java hljs"><span class="hljs-comment">// Jessica <span class="highlight">is 23</span> years old.</span></code></p>

<div class="fragment">
<p>If Jessica "is 23", then Jessica's age = 23:</p>
<code class="language-java hljs"><span class="hljs-keyword ">int</span> jessicaAge <span class="highlight">= <span class="hljs-number">23</span></span>;</code>
</div>

## Let's break it down…

### Comparing Jessica's and Sam's ages:

To say Jessica *is younger than* Sam means we are comparing their ages. Which operator would we use to compare them?

<code class="language-java hljs"><span class="hljs-comment">// Jessica <span class="highlight">is younger than</span> Sam.</span></code>

<div class="fragment">
<p>We use the "less than" relational operator to perform this comparison:</p>
<code class="language-java hljs">System.out.println(jessicaAge <span class="highlight">&lt;</span> samAge);</code>
</div>

## Let's look at the syntax

Single line comments start with `//`:

<code class="language-java hljs"><span class="hljs-comment"><span class="highlight">//</span> Jessica is 23 years old.</span><br>
<span class="hljs-keyword">int</span> jessicaAge = <span class="hljs-number">23</span>;<br>
<span class="hljs-comment"><span class="highlight">//</span> Sam is 47.</span><br>
<span class="hljs-keyword">int</span> samAge = <span class="hljs-number">47</span>;<br>
<span class="hljs-comment"><span class="highlight">//</span> Jessica is younger than Sam.</span><br>
System.out.println(jessicaAge &lt; samAge);
</code>

## Let's look at the syntax

Each statement ends with a semicolon. It acts like a period (.) in English at the end of a sentence.

<code class="language-java hljs"><span class="hljs-comment">// Jessica is 23 years old.</span><br>
<span class="hljs-keyword">int</span> jessicaAge = <span class="hljs-number">23</span><span class="highlight">;</span><br>
<span class="hljs-comment">// Sam is 47.</span><br>
<span class="hljs-keyword">int</span> samAge = <span class="hljs-number">47</span><span class="highlight">;</span><br>
<span class="hljs-comment">// Jessica is younger than Sam.</span><br>
System.out.println(jessicaAge &lt; samAge)<span class="highlight">;</span>
</code>

The statement:

```java
int jessicaAge = 23;
```

reads as "Jessica's age is 23."

## Let's look at the syntax

`println` is a *method*, so it ends with a set of opening and closing parentheses:

<code class="language-java hljs">
System.out.println<span class="highlight">(</span>jessicaAge &lt; samAge<span class="highlight">)</span>;
</code>

<div class="fragment">
<p>Inside the parentheses, we find the method <em>arguments</em>. For the <code>println</code> method, this is what we want to print. In this case, that's whether Jessica is younger than Sam:</p>
<code class="language-java hljs">
System.out.println(<span class="highlight">jessicaAge &lt; samAge</span>);
</code>
</div>

## Your turn! Try translating these word problems into Java.

- Lisa is cooking muffins. The recipe calls for 7 cups of sugar. She has already put in 2 cups. How many more cups does she need to put in?
- At a restaurant, Mike and his three friends decided to divide the bill evenly. If each person paid $13 then what was the total bill?
- How many packages of diapers can you buy with $40 if one package costs $8?
- Last Friday Trevon had $29. Over the weekend he received some money for cleaning the attic. He now has $41. How much money did he receive?
- Last week Julia ran 30 miles more than Pranav. Julia ran 47 miles. How many miles did Pranav run?
- How many boxes of envelopes can you buy with $12 if one box costs $3?
- After paying $5.12 for a salad, Norachai has $27.10. How much money did he have before buying the salad?

## Just keep coding! Just keep coding!

- 331 students went on a field trip. Six buses were filled and 7 students traveled in cars. How many students were in each bus?
- Aliyah had $24 to spend on seven pencils. After buying them she had $10. How much did each pencil cost?
- The sum of three consecutive numbers is 72. What is the smallest of these numbers?
- The sum of three consecutive even numbers is 48. What is the smallest of these numbers?
- Maria has boxes. She buys seven more. A week later, half of her boxes are destroyed in a fire, leaving her with 22 boxes. With how many did she start?