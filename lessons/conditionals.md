---
title: Processing.js - Conditionals
layout: lesson
type: main
order: 6
---

# Processing.js - Conditionals

**Objective:** This lesson will introduce students to conditionals. Students will learn the syntax of if-then constructions and will gain a basic understanding of booleans.

## Key Words and Concepts
- conditionals
- boolean

## Timeline

### Review Draw
*Since the draw function is an important concept in Processing.js and can be difficult for students to grasp, this lesson’s review time will largely repeat the material from the previous lesson.*

Last week, we learned how to animate our drawings using the draw function. Let’s begin by returning to a practice exercise from two lessons ago. We started with a program that draws a bee. We then added a variable that allowed us to move the entire bee by only changing one number.

If we were moving the car “manually,” we would increase the horizontal position, `x`, by 1 each time. We can do the same thing with code by adding a line within the braces that increases `x`. This line of code would be `x = x + 1`.

As we noticed last week, however, the bee remains stationary. This is because each time the loop runs, it resets `x` to 0. We can easily fix this by placing this line of code outside the loop. Now we set the value of `x` to be 0 outside the loop, and it increases each time. Typically, we don’t want to declare variables within loops.

When the restart button in the bottom-right corner is pressed, the bee starts on the left and slowly moves to the right. Like last week, we notice that the bee leaves behind a blob. We can fix this by adding one line of code that colors in the background before drawing the car each time. This line of code should be placed within the braces, before the rest of the code.

<https://www.khanacademy.org/cs/flying-bee/5302398142644224)>

### Introduce “If”
Last week, we began building an animated car that starts on the left side of the screen and moves to the right. Once it leaves the right side of the screen, it never returns. If we want to watch the animation again, we would have to press the restart button. Suppose we wanted the car to return to the start each time it left the screen. We would need some way to check if it left the screen, then send it back to the beginning.

We can use conditionals to do just this. We begin conditionals with the word `if`. This is followed by a set of parentheses, which contain a condition or boolean. A boolean is a statement that can either be true or false. In English, the boolean we want to test is “has the car left the screen?”. In order to answer this question, we can check if the x coordinate of the car is greater than 400. In code, this would look like: `if (x > 400)`.

*Building conditionals from English sentences is a good technique for learning how to write `if` statements. Emphasize this process throughout the lesson.*

After the parentheses, we add a set of braces. Everything that we put inside of these braces will happen only if the boolean is true. Inside the braces, we want to write code that places the car back at the beginning of the screen. In other words, we want to set the x coordinate of the car back to 0. In code, this would be `x = 0;`.

Putting this together, we have:

	if (x > 400)  
	{  
		x = 0;  
	}  

If this is inside of the draw function, each time the computer loops through the code, it will check to see if the variable `x` is greater than 400. If it is greater than 400, it will set `x` equal to 0. If it is not greater than 400, it will ignore the line that sets `x` equal to zero.

<https://www.khanacademy.org/cs/animated-car-with-conditionals/2038000455>

*Personifying the computer here might help to explain how computers deal with conditionals. Pretend to “be” the computer, and walk through code with a number of possible `x`’s.*

### Elaborate on Booleans
In order to determine whether the car has left the screen, we checked that its x coordinate was greater than 400. In a different scenario, we might want to check if a number is less than another or check if a number is equal to another. The following symbols can be used to compare two numbers in Processing.js:

> \<    less than  
> \>    greater than  
> ===    equal to  
> <=    less than or equal to  
> \>=    greater than or equal to  

If you want a statement to be true only if 2 booleans are true, you can combine them with “and”: `&&`. If you want a statement to be true if 1 or both of 2 booleans are true, you can combine them with “or”: `||`. 

*Provide some examples in which it might be useful to combine two booleans. If you want to foreshadow later exercises, explain how you might determine if a point is in the bottom right corner of the screen.*
 
### Introduce “Else”
Suppose we want to utilize our new knowledge of conditionals to create a program that helps people round decimals. If we have a number between 0 and 1 and we want to round to the nearest integer (i.e. 0 or 1), we would round down if the number were less than 0.5 and round up if the number were greater than or equal to 0.5. Suppose we want to tell the user to round down by making the background black and tell the user to round up by making the background red.

Let’s declare a variable called num that will keep track of the number that we want to round. We can set it to 0.5 initially: `var num = 0.5;`

Now our knowledge of conditionals comes in handy. We can write an if statement that tests if `num` is less than 0.5 and makes the background black if so. This code would look as follows:

	if (num < 0.5) 
	{
		background(0, 0, 0);
	}

Now we need to test if `num` is greater than or equal to 0.5. We can write another `if` statement that looks as follows:

	if (num >= 0.5) 
	{
		background(255, 0, 0);
	}

The background is now red! This is the expected behavior since `num` is currently set to 0.5. The computer checks if `num` is less than 0.5, realizes it is not, and ignores the code between these braces (the code that makes the background black). The computer then checks if `num` is greater than or equal to 0.5, realizes that it is, and executes the code between these braces (the code that makes the background red). If we set `num` to a different number, say 0.3, we see that the background becomes black.

This program seems to work as expected so let’s take another look at the `if` statements. We first check to see if `num` is less than 0.5 then we check to see if `num` is greater than or equal to 0.5. Since this covers all possible cases, we can actually replace the second `if` statement with the word `else`:

	if (num < 0.5) 
	{
		background(0, 0, 0);
	} 
	else 
	{
		background(255, 0, 0);
	}

Now the computer checks if `num` is less than 0.5. If it is, it makes the background black. Otherwise, it makes the background red. The concept of “otherwise” is expressed in code as `else`. `Else`s only come after `if`s and everything inside their braces happens only if the boolean in the `if` statement is false. Although it was perfectly correct to use the two `if` statements, using this `else` statement makes our code cleaner and slightly faster since the computer doesn’t have to check the second condition.

<https://www.khanacademy.org/cs/round-updown/2045097594>

### Worksheet
Open your workbooks and complete the worksheet on page [].

### Practice
When you have shown one of us your completed worksheet, you can turn to page [] and begin working on the [practice exercises](https://docs.google.com/a/college.harvard.edu/presentation/d/1xOOMcZFJRK79y80scU9wocH-IvcfvzIte-aQrkSsFso/edit?usp=sharing).

## Relevant Links
- [Finished Swimming Fish](https://www.khanacademy.org/cs/swimming-fish/6486229876998144)
- [Finished Rising Balloon](https://www.khanacademy.org/cs/rising-balloon/6471795834093568)
