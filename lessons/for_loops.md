---
title: Processing.js - For Loops
layout: lesson
type: main
order: 7
---

# Processing.js - `For` Loops

**Objective:** This lesson will introduce students to for loops.

## Key Terms and Concepts
- `for` loop
- initialization / condition / update

## Timeline

### Review
*At this point in the course, it is likely that the material that requires reinforcement will vary from classroom to classroom. Review whatever material is most challenging for your students, referring to past lessons for explanations and exercises.*

### Introduce `For` Loops
*This lesson’s worksheet may be used as a note-taking tool, but might be more effective as a quiz at the end of class or before independent practice.*

Last week, we began working with the draw function. We know that everything inside this function will be repeated forever. Suppose that instead we want to repeat a section of code a set number of times. In this case, we can use a structure called a for loop.

There are three parts to the `for` loop: the initialization, the condition, and the update. These parts are separated by semicolons. Let’s look at the following example:

	for (var i = 0; i < 4; i++)
	{
		// code here
	}

Let’s start with the initialization: `var i = 0`. The initialization creates a new variable and gives it an initial value. You can think of it as a counter that keeps track of how many times our code has run. Here, we start the counter at 0.

Next, we have the condition: `i < 4`. The condition tells us when we should loop. Here, we know that we should only loop while the variable `i` is less than 4. We will be discussing conditions in depth next week.

Finally, we have the update: `i++`. The update tells us how our counter variable changes each time we loop. The `++` here means that we increase `i` by 1 each time.

We can tell that the code inside this particular loop runs exactly 4 times. This is because the code will run when `i` is equal 0, 1, 2, and 3, but when `i` gets to 4, it will stop running.

### Use `For` Loops
Now that we understand the basic structure of for loops, let’s look at how we can utilize them within our programs. Suppose we wanted to draw four circles across the center of the screen. Before we introduced for loops, we would have written:

	ellipse(50, 200, 100, 100);
	ellipse(150, 200, 100, 100);
	ellipse(250, 200, 100, 100);
	ellipse(350, 200, 100, 100);

<https://www.khanacademy.org/cs/circles-without-loops/6283722269655040>

You might take this opportunity to review how we determined these parameters!

Four lines of code didn’t take that long to write, but what if we wanted to draw 40 circles? 400? Let’s see how we can use a `for` loop and only one call to the ellipse function to draw any number of circles. We will start with the structure that we analyzed previously, replacing the comment with a call to ellipse function:

	for (var i = 0; i < 4; i++)
	{
		ellipse(50, 200, 100, 100);
	}

The code above effectively draws 4 circles; however, all 4 circles are drawn in the same location. If instead we want to see the circles across the screen, each ellipse must have a different x-coordinate / horizontal position. That means that each time the for loop calls the ellipse function, the first parameter needs to be different.

We know that each time the code inside of the for loop runs, the value of the variable `i` changes. We can therefore utilize `i` in order to change the value of the first parameter. Let’s compare the values of `i` and the x coordinates that we want the ellipses to have (using the 4 lines we wrote earlier as a reference):

>    i     |     x   
    0     |    50  
    1     |   150  
    2     |   250  
    3     |   350  

The first time the for loop runs, we want x to be 50. After that, we want to increase x by 100 each time. Let’s start by creating a variable `x`, and we will initialize it to 50. At the end of the loop, we want to increase `x` by 100. This should remind us of how we changed `x` at the end of the draw function.

	var x = 50;
	for (var i = 0; i < 4; i++)
	{
		ellipse(x, 200, 100, 100);
		x = x + 100;
	}

<https://www.khanacademy.org/cs/circles-with-loops/5546537841065984>

### Worksheet
Open your workbooks and complete the worksheet on page [].

### Practice
When you have shown one of us your completed worksheet, you can turn to page [] and begin working on the [practice exercises](https://docs.google.com/a/college.harvard.edu/presentation/d/1jdTxl25xI-ioUktKHoL38K_HNdGW6ZpBoM6kV1879ms/edit?usp=sharing).

## Relevant Links
- [Finished Caterpillar with Loops](https://www.khanacademy.org/cs/caterpillar-with-loops/5563854964654080)
- [Finished Spectrum](https://www.khanacademy.org/cs/spectrum/6102546389139456)


