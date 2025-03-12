# Writing Pseudocode

[Watch this video!](https://youtu.be/nv3WZK7wzBk)

Even without knowing the syntax or semantics of a specific programming language, we can solve problems like programmers informally, using pseudocode.

Pseudocode is an informal set of instructions that describes how a program operates in English. There isn't any specified language or rules of pseudocode - however, programmers use pseudocode all the time, because it helps them visualize the solution to a problem before they dive into the specific grammar of their chosen programming language.

Pseudocode is a lot like like giving instructions to a human - like a recipe, or driving directions. The only difference is that with pseudocode, we often have to be more specific, because we're giving instructions to a machine, not a human.

For example, here's a pie recipe the way we might offer it to a human:

Preheat oven to 375 degrees
Mix ingredients together in a bowl
Put pie crust into the dish and fill with ingredient mix
Bake until golden brown
Now, let's pretend we're giving these same instructions to a machine. Now bear in mind that this machine can only do one thing at a time (it can't multitask), and will only do exactly what it's been told to do:

1. Turn on oven
2. If oven temperature is less than 375 degrees, wait 1 minute and then repeat step 2
3. Else, mix ingredients into bowl
4. Put pie crust into dish
5. Put mixture into pie crust
6. Put pie into oven
7. Check if pie is golden brown - if not, wait 1 minute and then repeat step 7
8. Else, remove from oven

Notice how with our machine, we didn't make some of the same assumptions we made with our human. This is the mindset we often use when writing pseudocode.

Here's another example - say that we have a robot vacuum cleaner. Here's the specification for the robot:

It can clean our room one square foot at a time by moving up, down, left or right. It can keep track of its previous moves, and it can tell whether a square foot has been cleaned or not. It also has a sensor on it so that it can tell what it's next possible moves are, and whether those squares are dirty or not.

How could we describe, in pseudocode, a program for our vacuum cleaner to clean the whole floor?

We could just say - move around the floor until everywhere is clean...but that's not really going to help us write a real program. Remember, we should assume that our robot vacuum cleaner is really dumb, and needs to be told exactly what to do each step of the way.

Here's a more specific set of instructions:

1. Clean the current square
2. Look at the possible moves that we can make
3. If one of those moves leads toward a dirty area, move toward that area and go back to step 1. If there is more than one option, pick one at random
4. Else if there is no dirty area to move into, that means we're done!
Pretend to be the robot and try playing out these instructions in your head. 

Do you get to clean all four squares?