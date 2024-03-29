# Tic Tac Toe CLI: Adding Player Move to the Game Board

## Objectives

1. Define a method that updates an array passed to it.
2. Define a method with a default value.
3. Use a method in a CLI.
4. Accept user input via gets.
5. Use user input in a method.

## Overview

In this lab we'll be adding a `move` method to Tic Tac Toe to update the board with a player's token. The `move` method represents a user moving into a position, like the middle cell, in Tac Tac Toe. We already have a method, `#display_board`, that prints out the tic tac toe board to the console and maps each location of the board to an array index. Then, we'll build a CLI that asks the player for the position on the board, i.e. location in the array, that they like to fill out with an "X" or an "O", updates the board, and displays the updated board.

## Project Structure

In previous exercises, we've learned to build programs that the user interacts with via the command line. Such interaction is considered to occur through the CLI, or command line interface. Conventionally, CLI programs have a `bin` directory with contains an executable file. This file contains the code that is responsible for running the program.

Take a look at the file structure of this project, mapped out below: 

```
bin
  |–– move
lib
  |–– move.rb
spec
  |–– 01_move_spec.rb
  |–– 02_cli_spec.rb
  |–– spec_helper.rb
...
``` 

We have our `bin` directory and it contains our executable file, `move`. Remember that executable files conventionally are not given a file extension like `.rb`. 

Open up `bin/move` and take a look at the following code: 

```ruby
#!/usr/bin/env ruby

require_relative '../lib/move.rb'
```

First, we have our shebang line that tells the terminal which interpreter to use to execute the remainder of the file. Second, we are requiring the `move.rb` file, from within the `lib` directory. This gives our executable file access to whatever code we write in the `move.rb` file. 

We'll be writing our `#display_board` and `#move` methods in `lib/move.rb` and writing the code that interacts with the command line in the `bin/move` file. 

## Desired Behavior

Now that we understand the broad strokes of what we've trying to accomplish, as well as where we'll be writing our code, let's take a look at an example of the functionality: 

When we run our executable file with `ruby bin/move` in the terminal, inside the directory of this project, we should see something like the following: 

```bash
Welcome to Tic Tac Toe
Where would you like to go?
2
   | X |   
-----------
   |   |   
-----------
   |   |   
```

Our program will: 

1. Print out a welcome message.
2. Ask the user to input the position on the board they would like to fill.
3. Fill out that position with either an "X" or an "O".
4. Print the updated board.

Okay, we're ready to start coding!

## Instructions

### Part I: Defining our Methods

The first part of this lab is test-driven. Run `learn` to get started and use the test output to guide you in defining the move method. 

Notice that we've already given you the `#display_board` method, since we've already built that out in a previous exercise. 

**Hint:** Your `#move` method must take in three arguments, the board array, the location in the board array that the player would like to fill out with an "X" or and "O", and the player's character (either "X" or "O"). The third argument, the player's character, should have a default of "X". Regarding the player's input: if the user's input is `5`, the player wants to fill out position 5 with their character. This means that your method must fill out the correct array index with the player's character. Remember that, from the player's point of view, the board contains spaces 1-9. But, an array's indexes start their count at 0. You'll have to account for that in your `#move` method. 

Once you have the tests passing, move on to part II. 

### Part II: The CLI

Open up `bin/move`. We're ready to code the executable portion of this program. 

1. Our program should first welcome the player by outputting a friendly message to the terminal: "Welcome to Tic Tac Toe".
2. Next, establish the starting state of the game, i.e. the empty board. Create a new board by setting a variable `board` equal to instantiating a new array with 9 elements, each of which is a blank space, `" "`.  
3. Now, ask the user for input by outputting "Where would you like to go?" to the terminal. 
4. We need to store the user's input. Use `gets.strip` to store their input to a variable, `input`. 
5. Now we're ready to call our `#move` method. Do so with the arguments of the the `board`, the user's `input` and either an `"X"` or an `"O"`. It doesn't matter whether you choose "X" or "O". 
6. Lastly, display the board by calling the `#display_board` method. 

Now, run your program by typing `ruby bin/move` in the terminal. Have fun playing (one round of) tic tac toe!
