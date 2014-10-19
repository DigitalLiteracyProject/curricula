---
title: Processing.js - Variables
layout: lesson
type: main
order: 4
---

# Processing.js - Variables

**Objective:** This lesson will introduce students to the concept and use of variables. Students will see how variables can be used to simplify programming and will end the class by learning to identify uses for variables in everyday life.

## Key Words and Concepts:
- variables
- declare
- _syntax_: `var`

## Timeline:
### Review
Last week, we started working with Processing.js. First, we learned about the coordinate system. When we create drawings or animations using Processing.js, they will appear on the right side of the Khan Academy page. Can you remind me how many units wide the area is, _[cold call]_? And how many units tall is the area, _[cold call]_?

Then we learned how to draw two shapes, rectangles and ellipses. What is the name of the function that draws rectangles, _[cold call]_? In order to tell the computer where to plot the shapes and how big to make them, we need to provide 4 parameters. What are the 4 parameters to the function rect, _[cold call]_?

Finally, we learned how to add color to our shapes. What is the name of the function that allows us to add color to our shapes, _[cold call]_?

_Walk through the process of drawing a car with Processing.js. This will set up the rest of the lesson._
 
### Introduce Variables
_In order to motivate this section of the lesson, walk the students through an example in which it is tedious to make changes to a drawing. For example, suppose we want to change the size of the wheels on the car we just drew. We would have to adjust the height and width of the first ellipse then adjust the height and width of the second ellipse. Suppose we want to change the size of the wheels again. We would have to go through the same process of changing each number one at a time. Wouldn’t it be nice to only have to change one number every time we wanted to change the size of wheels?_

**Variables** allow us to store and access information _(like the diameter of wheels)_. You can think of a variable as a bucket with a certain label. We can store information in the bucket, and we can retrieve information from the bucket, as long as we know what the bucket is labeled.

In Processing.js, we can create a variable by writing `var` followed by the name we want to give the variable. We can choose pretty much any name, and it’s useful to choose a name that gives us an idea of what information the variable is storing. For example, if we want to store the diameter of the wheels, we might use the name `diameter`. We then have to give the variable a value to store. In this case, we might initially set the value to 75. The full line of code would read var `diameter = 75`; When we create a variable like this, we call this **declaring** a variable.

After we declare a variable, we can change its value at any point. For example, after var `diameter = 75`; you could write `diameter = 100`; At any point after these two lines, diameter is equal to 100 instead of 75. Notice that we don’t need the `var` this time. We only need to put `var` before the name of the variable the first time we use it.

We can now use the variable `diameter` in our code as if it were the number 75 itself. Anytime that we see `diameter` in the code, we can replace it with a 75 in our minds. If we make the height and width of the ellipses `diameter` instead of 75, we will not be changing the behavior of the code at all. We now change the value of diameter to a different value; replace  `var diameter = 75`; with `var diameter = 100`;. With one simple change, we were able to change both ellipses’ height and width.

	ellipse(100, 350, diameter, diameter);
	ellipse(300, 350, diameter, diameter);
<https://www.khanacademy.org/cs/variable-location/2034413840>

_It may be difficult for students to understand why it is necessary to declare variables before using them. Try personifying the computer: _
_“We need to give the computer a heads up whenever we want to create a new variable. When we write var diameter = 75, we are saying, ‘’Hey, computer! I want use this new variable. It’s called diameter, and it’s value is 75. Whenever you see the word diameter, I’m really telling you to use the number 75!’”_

### Introduce Comments
It is important to choose variable names that help you remember their meaning. `diameter` is a better name for the diameter of a circle than `foo` or `bar` because if you were to return to the program months from now, you would be able to guess the meaning of the variable.

Programmers frequently revisit old code or read, use, and modify other programmers’ code. Suppose you wanted to leave a note for your future self or another programmer who might read your code. It would nice to be able to write that note right inside your program in plain English.

Luckily, Processing.js gives us a way to do this! These notes are called comments. They always start with `//`. The computer knows to ignore lines that start with `//` so you’re free to write words that the computer won’t necessarily understand. 

_You may choose to introduce comments by adding a line to the car program or you may point to comments on the practice examples._

### Use Variables in the Context of Movement
Returning to our example, suppose we want to move our car to the right or left. Before we learned about variables, we would have first moved the body of the car, then moved one wheel, then moved the other. Now we know that we can utilize variables in order to make this move easier. 

Since we’re going to be moving to the left and right, we can create a variable called x to represent the horizontal position of the of the car. Create the variable x and set it equal to 75, the current x position of the rectangle. This line of code would be `var x = 75`;. If we replace the x coordinate of the rectangle with `x`, nothing changes. 

If we increase `x` to 100, then we see that the rectangle moves towards the center of the screen. If we now change the x coordinates of the ellipses to `x`, the two ellipses stack on top of one another too far to the left. In order to move the wheels to their correct locations, we need to add a number to `x`. We can experiment with numbers until we manage to get the ellipses in their correct locations. For example, we might add 25 to one ellipse’s x coordinate and 225 to the other ellipse’s x coordinate.

	ellipse(x + 25, 350, 100, 100);
	ellipse(x + 225, 350, 100, 100);

Now if we want to move the whole car, we can just change the value of `x`.
<https://www.khanacademy.org/cs/variable-location/5151005041754112>

_Be sure to walk through this example slowly. After you have built the car and have made its position dependent on a variable, show how the whole car moves if you change the value of x. Instruct students to add something to the car (perhaps a window) that has a location that is also dependent on x._

### Practice
Turn to page [] in your workbooks and begin working on the [practice exercises](https://docs.google.com/a/college.harvard.edu/presentation/d/14kPwZMhG2O96GRM6SuN0ExygQtOIJ3wblyfb2a9Mujs/edit?usp=sharing)

### Relevant Links:
- [Finished Caterpillar](https://www.khanacademy.org/cs/caterpillar/6547448696668160)
- [Finished Bee](https://www.khanacademy.org/cs/bee/5008344968331264)
- [Finished Butterfly](https://www.khanacademy.org/cs/butterfly/6308230108020736)
- [Finished Smiley Face](https://www.khanacademy.org/cs/smiley-face/6214278419841024)
- [Finished Target](https://www.khanacademy.org/cs/target/6473933639385088)

### Evaluation
_Bring your students’ attention back to the front of the classroom. Give a warning two minutes, one minute, and thirty seconds before you want their attention. Count down the last ten seconds, and then have students put both hands up to ensure that no one is still working._

Great work with the practice exercises today! We will spend the last five minutes of class completing an evaluation. Go to [dlp.io/eval/4/](dlp.io/eval/4/) and carefully fill out the evaluation.