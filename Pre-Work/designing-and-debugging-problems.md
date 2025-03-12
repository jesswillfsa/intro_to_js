# Designing and Debugging Programs

[Watch this Video!](https://youtu.be/CneJexmG6Qo)

Let's revisit our robot vacuum cleaner. Here's the pseudocode we wrote:

1. Clean the current square
2. Look at the possible moves that we can make
3. If one of those moves leads toward a dirty area, move toward that area and go back to step 1. If there is more than one option, pick one at random
4. Else if there is no dirty area to move into, that means we're done!

This seems to work okay for our one example. But how would it perform in some other scenarios? Here's another possible room configuration, including an obstacle that the robot can only move around - how will this play out now? See if you can figure it out in your head first.

Uh oh, it looks like our program is causing our robot to finish too early! We've found a problem with our program, or as developers like to call it, a bug. But that's okay - actually, it's part of the process. Nobody's perfect, and it's hard to tell if an idea will work until we try it out. So, we try things out to see what the problems are, and then we go back and try to fix those problems. And the cycle often repeats itself - this the development lifecycle. Recall that we first applied this process when we learned about HTML. Let's tweak the process a bit and apply it to programming:

1. Understand the problem
2. Design the solution in pseudocode
3. Implement the solution in real code
4. Test the solution against various different inputs
5. If a problem occurs, solve it using the same process (back to step 1)

Let's apply this process to our problem.

(1. Understand the problem) Right now, it's possible for our robot to get "trapped in a corner". This is because we're no longer moving as soon as we can't move onto a dirty square. It's clear from the layout of the floor that it will be impossible to clean the whole floor without some level of backtracking.

Let's recall the specification for our robot vacuum cleaner:
- It can clean our room one square foot at a time by moving up, down, left or right. 
- It can keep track of its previous moves, and it can tell whether a square foot has been cleaned or not. 
- It also has a sensor on it so that it can tell what it's next possible moves are, and whether those squares are dirty or not.

Since our robot tracks its previous moves, we can assume it knows where it moved from. Here's an idea: let's say that if we can't move to a square that's dirty, we'll move back to where we came from.

Let's design a new solution in pseudocode (2. Design in pseudocode)! Changes to our design are in bold:

1. If dirty, clean the current square
Look at the possible moves that we can make
2. If one of those moves leads toward a dirty area, move toward that area and go back to step 1. If there is more than one option, pick one at random
4. Else, go back to our previous position, and repeat from step 1

At this point, we would write actual code, but we'll skip that for now. We can move right on the next step, (4. testing the solution).

Try it out in your head! What you might find is that this solution works relatively well in that it gets the entire floor clean, but unfortunately our robot doesn't know when to stop! We've got a new problem! Back to step 1!

We no longer tell our robot when to stop. We can't assume that the absence of dirt means that we can't move anymore - then, we'd be right back to our initial problem! After some lengthy trial and error, we might notice that we can always tell that we're done once we're back on the starting square, and there are no moves to dirty squares left.

Here's the final pseudocode:

1. If dirty, clean the current square
Look at the possible moves that we can make
2. If there's nowhere new to move, AND we're back at start, then we're done!
3. If one of those moves leads toward an unclean area, move toward that area. If there is more than one option, pick one at random
4. Else, go back to our previous position, and repeat from step 1.

What seemed to be a simple problem on the surface actually turned out to be quite a doozy! This is actually a fairly difficult problem dealt with by everyone from game developers to actual robot engineers (for the curious, this problem is called graph traversal)! It's definitely not an easy problem to solve - however, the important takeaway is that we can describe the solution using pseudocode just as well as we can using real code! When you learn to program the first time, you are actually learning two things at once: the rules and syntax of a specific programming language, and how to solve problems in a programmatic manner.