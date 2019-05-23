---
title: Introduction to JavaScript — Part II
title: JS II
length: 120
tags: javascript, introduction, foundation, variables
---

<!-- To Do List/Items: -->

<!-- 
- Chart paper for review of JS 1
- Write questions for review on the board
- Write password for internet on the board
- Write URL for DSST repo on board -->

## Review

Before we get started with new material, let's go over over what we've learned so far.  

- The primitive data types
- Variables
- Conditionals
- Functions

<!-- ## Chartboard Review template: 

Norms:
* Each group member should share some findings to the larger group
* While your group is not going, you should be taking notes on the other groups' findings
* At the end, time should be given for folks to walk around and check the other chartboards

- Give the groups 8 minute to answer questions
- Set a timer to project onto the board

Break students into groups of 3-4 people (4 max) each to review specific topics.

Groups should answer the following 3 questions on chart paper. These should be written on the board before the students arrive:

1. What would be an example of ___________ ?

2. What are the most important/significant things someone should know about ___________________?

3. What might be a metaphor or analogy for  ________________?

Groups have 8 mins to answer questions and draw/write out their answers. End with groups sharing out.


 -->

## Learning Goals

- Review and understand functions at a deeper level
- Understand how basic scoping works in JavaScript
- Understand what an array is and why they are useful
- Demonstrate how to set and access values in an array
- Use for loops to iterate
 
## Vocab

- See [vocab](http://frontend.turing.io/lessons/module-1/js-1.html) for JS I
- `Anonymous Function` A function without a name
- `Scope` Determines the accessibility/visibility of variables and other expressions
- `Literal`  A way of declaring a data structure and its values at the same time
- `Array` Used to store a list of data items/multiple values under a single variable name
- `Loops` A quick and easy way to do something repeatedly
- `Control Flow` The order in which the computer executes statements in a script. The order of execution can change whenever the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops.

## Resources
[JS Style Guide](https://github.com/turingschool-examples/javascript)

# More on Functions

Can't get enough.  

## Part 1: Calling functions inside of other functions
When writing Javascript, you want to do your best to keep your code DRY. That means keeping functions concise and single responsibility. It's not uncommon to do a first pass at solving a problem and end up with a more verbose solution, and then revisit your code to tighten it up. This process of cleaning up your working code is called `refactoring`. When we refactor, one of the things we look for is unnecessary duplication. If we see a line of code being used in multiple places, we can pull it out into its own separate functions of reusable code.

Let's take a crack at refactoring some functions and calling functions within other functions. Below we see two very important functions:

```js
function karateChop() {
  console.log("KARATE CHOP!");
  alert("KAPOW!");
}

function ninjaAttack() {
  alert("KAPOW!");
  console.log("NINJA SURPRISE!");
}
```

We can see that we have some duplication going on between these two functions. We see we have an `alert` that is exactly the same in both functions, which means it is a prime candidate to get pulled into its own function. This will let us reuse this code without retyping it repeatedly (which helps reduce human error and typos), and gives us the flexibility to easily use it in future functions as well. Let's see what that looks like:

```js
function kapow() {
  alert("KAPOW!");
}

function karateChop() {
  console.log("KARATE CHOP!");
  kapow();
}

function ninjaAttack() {
  kapow();
  console.log("NINJA SURPRISE!");
}
```

### Your Turn

Turn to your neighbor and explain how the functions above work. Remember, getting practice using the vocabulary is important so make sure you both have a chance to talk through it!  

_Challenge: How would you use parameters and arguments to make the logged string be different each time we call the function?_

## Part 2: Putting a name (or not) to our functions

### Named Functions aka Function Declarations

So far, we've been working with *named functions*. *Named functions* can also be referred to as *function declarations*, or even *normal functions*.  

Through *function declaration*, or *named functions*, ie: `function myNamedFunction()`, we create a function that we intend to call later in our code via the name we gave it.  

Although there are other ways to declare functions in JavaScript, today we will primarily focus on using named functions for our code.

```javascript
// Declare a named function
function myRadFunction(parameter) {
  console.log(parameter);
  alert("All done!");
}

// Call that named function to execute
myRadFunction("Boom");

```

### Anonymous Functions

Another type of function that we will sometimes utilize is the *anonymous function*, which does not have a name. These are commonly used as arguments to other functions as seen below:

```js
setTimeout(function() {
  alert('BOO!')
}, 1000)
```  

In general, you should only use an anonymous function when a named function doesn't make sense. For example, it is common to use anonymous functions when you have a function that is only being called in one place.

So why use named functions over anonymous functions?

* Named funtions are more useful for identifying what functions caused errors (during the debugging process)
* Named functions are more readable
* Named functions are easier to reuse

#### Journal

- In your own words, describe a function. What is the difference between an anonymous and a named function?

# Variable Scope

Where you declare a variable affects where it can be used within your code. If you declare a variable within a function, it can only be used within that function. This is known as the variable's `scope`. When we talk about variables in regard to their scope, there are two (kind of three) types:

- Local Variables:
  - created _inside_ a function using the var keyword
  - said to have "local scope"
  - cannot be accessed outside the function in which it was declared
  - they are created when the function is run, and removed when it is done
  - if the function runs twice, the variable could have a different value each time
  - if the variable is locally scoped, then two different functions can use the same variable name without a naming conflict

- Global Variables
  - created _outside_ a function
  - can be used anywhere in the script
  - said to have "global scope"
  - stored in memory for as long as the web page is loaded
  - takes up more memory than local variables, as well as introduces more risk of naming conflicts

- Variables sans the keyword `var`
  - ok when used to redefine a variable that has already been declared
  - risky business otherwise

<!-- Use analogy from code analogies -->

## The Variable Danger Zone

Keep this in mind as you're making new variables:

Variables sans the keyword `var`
  - will work
  - will be considered global variable, even if declared _inside_ a function
  - are bad practice

The good news is all you have to do to avoid this is to always remember to use the `var` keyword when declaring a new variable!

# Arrays

<!-- Use analogy to talk about arrays from code analogies -->

An array is a special type of variable. Instead of storing just one value, it stores an ordered list of values. You should consider using an array whenever you are working with a collection of values, or values that are related to one another.

You can put different types of data into an array:

```js
var arrayName = [element0, element1, ...];
var rainbowColors = ['Red', 'Orange', 'Yellow', 'Green',
'Blue', 'Indigo', 'Violet'];
var lotteryNumbers = [33, 72, 64, 18, 17, 85];
var myFavoriteThings = ['Broccoli', 1024, 'Sherlock'];
```

<!-- Talk about naming and how arrays should be plural -->

You can create an array just like you would any other variable, using the var keyword followed by the name of your array. The values are assigned to the array inside a pair of square brackets ([]), and each individual value is comma-separated. The above technique for creating an array is known as an **array literal**. It is usually the preferred method for creating an array. You can also write an array with values on separate lines, like so:

```javascript
colors = ['white',
          'black',
          'pink']
```

#### Your Turn 

Open up your console and create an array of your favorite rides at Elitch Gardens.

## Accessing Values in Arrays
Each value in an array is automatically given a number called an index. This index can be used to access a particular value in any given array.

Indices begin at 0 and order incrementally. So in the above `colors` example, the following is true:

- color white has an index of 0
- color black has an index of 1
- color pink has an index of 2

You can change values in an array by their index. Let's walk through it in the console:

```javascript
// Create the array
var colors = ['white', 'black', 'pink'];

// Check the value of colors
colors;

// Update the third value in the array
colors[2] = 'blue';

// Check the value of colors
colors;

// Get the value of the 1st element
colors[0];
```
<!-- 
Open up the console - make an array of your favorite things. Then update/access the values that are within the arrays
 -->

### Your Turn (5 min)

In the console:  
- create an array of cars or books
- change the values within the array
- add a new car or book to the array
- identify the value of the 3rd element of the array

<!-- Could pull someone up from audience who has finished the exercise to showcase what they did/walk through what they did -->

## Getting Multiple Values from Functions:

Functions can return more than one value using an array. Let's see what this looks like:

```javascript
function getSize(width, height, depth) {
  var area = width * height;
  var volume = width * height * depth;
  var sizes = [area, volume];
  return sizes;
}
var firstSizes = getSize(3, 2, 3);
var secondSizes = getSize(3, 2, 3);
```

### Your Turn (10 min)

Okay, let's pick this apart in the console, step by step, and make sure we understand what's what. In the console, do these things:

```javascript
// Declare the getSize function
function getSize(width, height, depth) {
  var area = width * height;
  var volume = width * height * depth;
  var sizes = [area, volume];
  return sizes;
}

// Ask the console what "getSize" is
getSize;

// Call the "getSize" function
getSize();

// Why this?
[NaN, NaN];

// Okay, pass getSize some arguments
getSize(5, 3, 2);

// I feel pretty good about this result, but feel free to check the math. ;)
[15, 30];

// Interactive Pop Quiz Time!
var sizes1 = getSize(3, 2, 3);
var sizes2 = getSize(3, 2, 3);
var sizes3 = getSize(5, 1, 2);
var sizes4 = getSize(2, 2, 2);
var sizes5 = getSize(1, 8, 7);
```

# Loops
There are times when we want to repeat the same operation multiple times over a set of data. Loops allow us to do just that by running through our data one by one and executing code to accomplish a goal.

For example, for each item in a list (maybe an `array`...) if a conditional returns `true`, a code block will be run and the condition will be checked again. This pattern will be repeated until the conditional returns `false`.

Let's take a look at the structure of the most commonly used type, the `for` loop:

```js
for ([initialExpression]; [condition]; [incrementExpression]) {
  statement
}
```

Which looks like this when we implement it in code:

```js
for (var i = 0; i < 10; i++ ) {
  console.log(i);
}
```

If we break this down, we see that our loop is constructed from the following parts:

- the keyword `for`  
- a set of rules, or conditions `(var i = 0; i < 10; i++ )`   
- opening and closing curly braces which contain our code  
- the code that we want our loop to execute: `console.log(i);`  

Let's dig into the three statements separated by semicolons that make up or our conditions:

- We begin with **initialization**. Where do we want our loop to start? The first statement `var i = 0;` creates a variable that is assigned the value of 0. This variable is commonly named `i`, or `index`, and will act as the counter. It is created the first time the loop is run.  
- The next statement **sets the condition** that tells the loop when to stop running: `i < 10;`. In this case, the condition indicates that the loop will stop when `i` equals 10. The condition may use a variable that is assigned a value.
- Finally, with the statement `i++` we **update the value** of our counter `i`. This adds 1 to the value of `i`. This syntax is using the increment operator `++`, which is a way of writing `i = i + 1`. It is also possible to decrement downwards using the decrement operator `--`, which is a way of writing `i = i - 1`.

The statement within the curly braces executes each time the loop runs. In this case, we can see we are logging the value of `i` to the console.

#### Turn and Talk

Describe what is loop in your own words. Think of an real world analogy for a for loop.

### Looping Over Arrays
`for` loops are commonly used to iterate over the items in a array. To do this, we use the property `length` and call it on the variable associated with the array we want to iterate over. This property returns the length of, or number of elements in, an array. Let's see what that looks like in practice:

```js
var fruitList = ['apples', 'oranges', 'bananas'];

for (var i = 0; i < fruitList.length; i++) {
  console.log("I have some " + fruitList[i]);
}
```

You can see that instead of using a hardcoded number, we are using `fruitList.length` in our condition. This means we will continue to loop over the array as long as the counter is less than the total number of elements in the array. That's pretty handy!

#### Your Turn 

Create an array of your favorite emojis. Using a for loop, iterate over that array and log each item to the console.


### Loops and Performance Issues
It's important to be aware of the potential performance problems that loops can cause. When a browser hits Javascript, it stops executing anything else on the page until it has processed that script. Since loops can be run on arrays or containers of unknown -- and potentially enormous -- size, it's possible for our loop to make a page much, much slower to load.

Additionally, if the condition of your loop never returns `false`, you will get stuck in what's known as an `infinite loop`. This means that your loop will never stop running. Eventually your browser will run out of memory and your script will break.

Here's an example of an infinite loop. Open a new tab in your browser and run this in your console. What happens?

```js
for (var i = 0; i > -1; i++) {
  console.log(i);
}
```

We can see that this condition will never return `false` and we'll be stuck in this loop forever (or at least until our page crashes)! Be mindful of the possibility that you could create infinite loops when leveraging loops in your code. They can happen to the best of us, and knowing what they are is the first step to avoiding and correcting them.  

### Closing

- What is an analogy of how scoping works in JavaScript. Illustrate your analogy by drawing a picture.
- Think of your favorite app. What data does it store? What might be stored in an array?
- What are loops? Why do we use them?

### Additional Practice  

* [JavaScript Playground](http://frontend.turing.io/lessons/module-1/javascript-playground.html) let's you experiment more with these concepts.

### Dig Deeper  

* [Seven JS Quirks I Wish I'd Known About](http://developer.telerik.com/featured/seven-javascript-quirks-i-wish-id-known-about/#expdec)  
* [Adequately Good JS](http://www.adequatelygood.com/JavaScript-Scoping-and-Hoisting.html)  
