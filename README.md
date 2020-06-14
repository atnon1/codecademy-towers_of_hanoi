# codecademy-towers_of_hanoi
Codecademy Project Tower of Hanoi
(Guided Project)

Python 3.6.9

Towers of Hanoi
Towers of Hanoi is an ancient mathematical puzzle that starts off with three stacks and many disks.

The objective of the game is to move the stack of disks from the leftmost stack to the rightmost stack.

The game follows three rules:

Only one disk can be moved at a time.
Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack or on an empty rod.
No disk may be placed on top of a smaller disk.
In this project, we are going to use our knowledge of stacks to implement this game! Let’s get started!

If you get stuck during this project or would like to see an experienced developer work through it, click “Get Help“ to see a project walkthrough video.

Tasks
33/33Complete
Mark the tasks as complete by checking them off
Creating the Stacks
1.
In this game, we will have three stacks. Each of these stacks will have a name. Tab over stack.py and see how the _init_ method now takes in a name.

In addition, there is also a get_name method, a get_size method, and a print_items method that we will use later on in the project.

2.
Tab back over to script.py. First, we will set up our three stacks.

Underneath the comment, #Create the stacks, create a variable, stacks, and set it equal to an empty list. We will store the stacks in here.

3.
Now, create three Stack instances: left_stack, middle_stack, right_stack. Give them the respective names of "Left", "Middle", and "Right".


Stuck? Get a hint
4.
Append each of these Stack instances to stacks.

Setting up the Game
5.
Now that we have our stacks, let’s create your disks.

Underneath the comment, #Set up the Game, create a variable, num_disks, and set it equal to the int representation of the user input when asked "\nHow many disks do you want to play with?\n".

Check the hint for a solution.


Stuck? Get a hint
6.
Save your code. In the terminal, run python3 script.py. Your code should print:

Let's play Towers of Hanoi!!

How many disks do you want to play with?
and then prompt you for an input.

7.
The game is only fun when there is at least three disks.

Make a while loop that checks if num_disks is less than 3.

In the loop, set num_disks to the int representation of the user input when prompted "Enter a number greater than or equal to 3\n".

8.
Save your code. In the terminal, run python3 script.py. Try entering a number less than 3.

9.
Now, we will add our disks. We will represent disks with numbers. Disk 3 is larger than Disk 1 etc.

After the while loop, create a for loop that iterates backwards through the range of the num_disks.

Check the hint for a solution.


Stuck? Get a hint
10.
In the for loop, push the number onto the left_stack.

11.
Now that we created our initial stacks and set up the disks, let’s calculate the number of optimal moves.

For towers of hanoi, the number of optimal moves is always 2Number of Disks - 1.

After the for loop, create a variable, num_optimal_moves, and set it equal to the number of optimal moves.

Afterwards, print, "\nThe fastest you can solve this game is in {0} moves" {0} corresponds to the num_optimal_moves.


Stuck? Get a hint
12.
Save your code. In the terminal, run python3 script.py.

Enter a number of disks and see the number of moves the game can be solved in.

Getting User Input
13.
Now, let’s create a helper function that prompts users to choose a stack. We want to have users only enter the first letter. For instance:

Enter L for Left
Under the comment, #Get User Input, define a function called get_input that takes in no parameters.

14.
In the function, create a variable, choices, and set it equal to a list of the first letters of the names of the stacks.

Instead of hard-coding the letters like choices = ['L', 'M', 'R'], try and use the .get_name method of the stacks and a list comprehension.

Check the hint for a solution.


Stuck? Get a hint
15.
Now, we will keep asking the user for an input until we get one that is valid.

Still inside the get_input() function, create a while True loop.

16.
First, let’s print our choices. We will do so by iterating through the stacks and printing the corresponding first letter and name.

In the while loop, create a for loop that uses an iterator, i, to iterate through the range of the length of stacks.

Check hint for the solution.


Stuck? Get a hint
17.
In the for loop:

Create a variable, name, and set it equal to the name of stacks[i]. Use the .get_name() method.
Create a variable, letter, and set it equal to choices[i]
18.
Next, print the following statement in the for loop:

"Enter {0} for {1}". {0} corresponds to letter, and {1} corresponds to name.
19.
Now that we printed the options, let’s get the user input.

After the for loop, but still inside the while loop:

Create a variable user_input.
Set it equal to an input of empty quotes.
20.
Awesome! Let’s test it out.

In the terminal, run python3 -c 'import script; script.get_input()'

You should continuously be prompted to enter a letter from the three choices.

To exit the loop, you can press Ctrl C.

21.
Now, let’s check if the user made a valid choice.

In the while loop, create an if statement that checks the following:

user_input is in choices
Inside that conditional statement, we want to check which stack the user chose.

Inside the if statement, create a for loop that uses an iterator, i, to iterate through the range of the length of stacks.


Stuck? Get a hint
22.
Inside the for loop, do the following:

Check if user_input is equal to choices[i]
If so, return stacks[i]
23.
Let’s test this out.

In the terminal, run python3 -c 'import script; script.get_input()'.

You should be prompted to enter a letter from the three choices until you make a valid choice. Try entering invalid choices to test it out.

Playing the Game
24.
Now, let’s write code to play the game.

Under the comment, #Play the Game, start off by creating a variable, num_user_moves, and setting it equal to 0.

25.
The game ends when the right_stack is full.

Create a while loop that loops while the size of the right_stack is not equal to num_disks. Use the .get_size() method.

Check the hint for a solution.


Stuck? Get a hint
26.
First, we want to print our current stacks.

In the while loop, do the following:

print "\n\n\n...Current Stacks..."
Iterate through stacks and call the .print_items() method on each stack.
27.
Now, we will keep asking the user what move they want to make until they make a valid move.

After printing the stacks, but still in the while loop, create a while True loop.

In this inner loop, start off by doing the following:

Print "\nWhich stack do you want to move from?\n"
Create a variable, from_stack, and set it equal to the return value of get_input()
Print "\nWhich stack do you want to move to?\n"
Create a variable, to_stack, and set it equal to the return value of get_input()
28.
Save your code. In the terminal, run python3 script.py. You should continuously be asked to enter what stacks you want move from and move to.

29.
Now, we will make the move. First, we will check if the user made a valid move. If the user tried to move from an empty stack, that is an invalid move because there is nothing to move.

In the inner while loop, create an if statement that checks if the from_stack is empty.

If so, print "\n\nInvalid Move. Try Again".

30.
If the user moves a disk to an empty stack or moves a disk onto a larger disk, that’s a valid move.

In the inner while loop, create an elif statement that checks if EITHER of the following is True:

The to_stack is empty.
The “peeked” value of the from_stack is less than the “peeked” of the to_stack
If so, do the following:

Create a variable, disk, and set it equal to the popped value of the from_stack.
Push disk onto the to_stack
Increment num_user_moves
break from the inner while loop
31.
The only other case is if the user tries to move a larger disk onto a smaller disk.

In the inner while loop, create an else statement. Inside it, print "\n\nInvalid Move. Try Again".

32.
Finally, after both while loops, print the following:

"\n\nYou completed the game in {0} moves, and the optimal number of moves is {1}". {0} corresponds to num_user_moves and {1} corresponds to num_optimal_moves.
33.
Congratulations! You made the game!

Save your code. In the terminal, run python3 script.py and play the game!
