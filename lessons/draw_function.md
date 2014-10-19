---
title: Processing.js - Draw Function
layout: lesson
type: main
order: 5
---

# Processing.js - Draw Function

**Objective:** This lesson will teach students how to utilize variables to add animation to their drawings. They will be exposed to the concept of iteration and will learn how to use the draw function.

**Key Terms and Concepts:**

- draw
- iteration
- _syntax_: braces, indentation

## Timeline:

### Review

_Begin by briefly reviewing the coordinate system. Review how to create and use variables, and reiterate the importance of variables in computer science and everyday life. Return to the example in which we trying to move the horizontal position of the car since it serves as a starting point for the introduction of the draw function._

_Since adding animation to a drawing is a significant step above adding variables to a program, this lesson purposely contains limited new content. It is important to go through the material slowly. Any extra time should be dedicated to practice!_

### Introduce the [Draw](http://processingjs.org/reference/draw_/) Function

Suppose we want to move our car from the left side of the screen to the right side of the screen. One way to do this is to set x equal to 0 and increase it by 1 until it gets to the right side of the screen. This process would take a long time and would require us to do a lot of work.

We can instead utilize a built-in structure which looks like this:

	var draw = function() {
	};

Anything inside these curly **braces** will be repeated forever. Although it does not affect the behavior of the code, it is customary to **indent** every line of code inside these braces. It makes it easier for someone reading your code to tell which lines of code are going to be repeated.

Suppose we wanted to repeatedly draw our car. We could copy the code inside the draw function and indent it. The program would look as follows:

	var x = 0;
	var draw = function() {  
		fill(0, 255, 255);
		rect(x, 225, 250, 125);
		fill(0, 0, 0);
		ellipse(x + 25, 350, 75, 75);
		ellipse(x + 225, 350, 75, 75);
	};

When we introduce animation, it will become clear why we need to keep the variable declaration outside the loop. When we do something again and again in computer science, we say that we are iterating. **Iterate** means perform repeatedly.

_This section introduces a lot of terminology and syntax. Make sure to write key words and structures on the board. Also point out some potential errors (e.g. forgetting the semicolon after the closing brace of the draw function)._

### Add Animation

Instead of repeatedly drawing the car is the same position, we can draw it in different positions by changing `x`. If we were moving the car "manually" as described in the previous lesson, we would increase `x` by 1 each time. We can do the same thing with code by adding a line within the braces that increases `x`. This line of code would be
`x = x + 1`.

The code should now look as follows:

	var x = 0;
	var draw = function() {
		fill(0, 255, 255);
		rect(x,225,250,125);
		fill(0, 0, 0);
		ellipse(x + 25,350,75,75);
		ellipse(x + 225,350,75,75);
		x = x + 1;
	};

Now we should see the car moving to the right! As the car moves, it leaves behind a black blob. This is because the computer begins by drawing the car on the left side of the string. It pauses for a second, then draws the car again slightly farther to the right. All of these drawings are done on top of one another and the previous car is not "erased" when a new one is drawn.

We can fix this by adding one line of code that colors in the background before drawing the car each time. This will effectively erase the previous drawing when we are about to draw the car in each new position. `background` is the function that colors in the background, and it takes the same arguments as `fill` (3 integers between 0 and 255 that specify the amount of red, green, and blue respectively). This line of code should be placed within the braces, before the rest of the code: `background(255, 255, 255);`

The final code should look as follows:

	var x = 0;
	var draw = function() {
		background(255, 255, 255);
		fill(0, 255, 255);
		rect(x, 225, 250, 125);
		fill(0, 0, 0);
		ellipse(x + 25, 350, 75, 75);
		ellipse(x + 225, 350, 75, 75);
		x = x + 1;
	};

<https://www.khanacademy.org/cs/animated-car-draw/2034164513>

Notice that if we had included the variable declaration inside the loop, we would always be resetting x to 0 and the car would remain stationary.

### Step Through Iteration

_In order to solidify students' understanding of iteration, walk through the code a few times, treating each line like an instruction. Keep track of the value of x on the board and draw/redraw the car a few times. Ask the students how we might make the car move faster. (Instead of adding 1 to x, we could 5.)_

### Worksheet

Open your workbooks and complete the worksheet on page 41.

### Practice

When you have shown one of us your completed worksheet, you can turn to page 44 and begin working on the practice exercises.

<https://docs.google.com/a/college.harvard.edu/presentation/d/1VuroDZSa7LwPog5eDwBDru0laa2tvErRrGS4iXNeU5s/edit?usp=sharing>

### Relevant Links:

- [Finished Animated Car](https://www.khanacademy.org/cs/animated-car/6405923618684928)
- [Finished Growing Flower](https://www.khanacademy.org/cs/growing-flower/6698931943636992)
- [Finished Rolling Ball](https://www.khanacademy.org/cs/rolling-ball/5544742678953984)
- [Finished Backwards Car](https://www.khanacademy.org/cs/backwards-car/5537051600486400)

### Evaluation

_Bring your students' attention back to the front of the classroom. Give a warning two minutes, one minute, and thirty seconds before you want their attention. Count down the last ten seconds, and then have students put both hands up to ensure that no one is still working._

Great work with the practice exercises today! We will spend the last five minutes of class completing an evaluation. Go to [dlp.io/eval/5](http://dlp.io/eval/5) and carefully fill out the evaluation.