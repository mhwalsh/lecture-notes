### JavaScript - Basics

- [https://www.codecademy.com/learn/javascript](https://www.codecademy.com/learn/javascript)
- [https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
- [https://www.codeschool.com/courses/javascript-road-trip-part-1](https://www.codeschool.com/courses/javascript-road-trip-part-1)
- [https://atom.io/](https://atom.io/)

1. Hello World

	#### Objectives
	Learn how to source a JavaScript file. Learn how to console log values and see the results. Both are essential to testing out any JavaScript concepts you learn. 

	JavaScript is a programming language. It will be the base language that we use throughout this course. The fundamental programming concepts are the essential building blocks to building a full featured application. 
	- For now let's make a folder on your desktop called hello-world.
	- Open folder up you code editor. At Prime we will use [Atom](https://atom.io/). You can do this by dragging the folder over the atom icon in your dashboard.
	- Make two new files: index.html and script.js. Mention file extensions (js and html). Things might look different, you won't have file icons yet.
	- Code basic html page. html head and body. Test by opening in finder. Show the file path in URL. We use chrome. Comments in HTML.
	- Code basic script file. Comments in JS. Can't test until we source.
	- Source the script file. Meaning make the HTML aware of the JS file. JavaScript isn't require, but makes our pages do cool things. script tag. src attribute takes a path to the file.
	- file system.
	- Test that they are sourced.
	- Log hello world.

	#### Try it! 
Make the classic "Hello World" program. Scrub back through the video and follow along. Challenge: Append to the DOM.

2. Variable
	**What is a variable?** - *Variables are containers that you can store values in.* - MSDN
	
	**Example**: While talking through following points, so the creation of a variable, assignment, reassignment, and logging it out.
	
	**Declaration** - The key word *var* followed by the name of the container or variable.
	
	**Assign it** - Give it value, with the assignment operator = followed by the value you want the container to hold.
	
	**Reassign it**
	
	**Example**: Let's change our Hello World from Tau to a specific person. First we could 'hard code' this (meaning a string of the name we want), but this doesn't really solve our problem because now instead of saying Tau every time it says Fred. We want that portion to be variable based on the user input. Simple way to get user input is the prompt method.
	
	**Why use a variable?** - The reassignment is important. This gives use the ability to make functionality that is generalized and can preform the same tasks on different input (variables). 
	
	#### Try it! 
	Modify the code you wrote after the 'Hello World' video to take user input and console log the value.
	
3. Arrays
An array - is way to store repeated data in one variable. A list of things that you would group together. 

We will look at examples of these in a minute. Some things could be: Cars, feelings, names, word, ages, etc.

**What is the syntax?**
square brackets [] with comma separated values inside. You can assign this to a variable. 

// Declare an empty array
var myArr = [];

//Or initiate it with values
var myArr = [1, 2, 3, 5];

//Try some different data types: Cars, feelings, names, from above.

**Keep types consistent**
Keep the datatypes inside the array consistent. JavaScript doesn't require this, but it is good practice.  WHY?
// Mix value types. 
var myMix = [1, "string"];

// You can instantiate the array values using variables.
var name1 = "Millie";
var name2 = "Dev";
var name3 = "Huck";
var myArr = [name1, name2, name3];
log this...
storing the variable of the value of it

**Index**
How do you get at the elements. Index into them.
- sub/of 
- arr[0]
- console.log these
- count from zero

**Methods**
You can operate on arrays using special **builtin** methods and properties. 

- ```.length```
- ```.push()```
- More resources here: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Methods)

**loops**
Pairs nicely with a for loop. To **iterate** over all your data stored in the array.

```
for(var i = 0; arr.length; i++) {
	console.log(fruits[i]); // what happens if this isn't variable?
}
```

