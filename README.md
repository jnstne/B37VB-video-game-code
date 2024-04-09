# Aidan Johnstone Noughts and Crosses game report

## introduction
for my video game i decided to make my own version of the pre existing noughts and crosses.
its a game made for 2 players to compete and enjoy

## instructions of game

its just a classic game of noughts and crosses where 2 players to go against each other 
to try and get 3 of their shape in a row while simultaniously stopping the other from
doing the same

the controls are shown in the game too but ill explain them here too,

- Player 1 plays as the symbol X
- Player 2 plays as the symbol O

the noughts and crosses grid is split up into 9 sections each with a connected number (1-9).

Player 1 goes first and picks any of the sections they want to start with by typing the number associated with said section.

then Player 2 continues by choosing a different number than what Player 1 chose and the game continues like this.

the game ends when one player gets 3 of their symbols in a row, whether thats up & down, left & right or diagonal.

alternatively the game also ends when all 9 sections have been filled and no winner is found, hence the result is a draw.

when a game is completed a prompt will come up asking the player if they'd like to play again or terminate the run, also any game can be terminated by typing -1.

## code explanation

comments have been left throughout the entire code to briefly explain what each section of code is for

the line of code "char board[3][3];" is declaring the global array for the game board, being a 3 by 3 (9 section) array.
the variables "i" and "j" are used as placeholders for initializing the limits of the board.
"for" statements act as nested loops and the nested loops are used to initialize the elements of the 2D array (board) to a default value of (' ').

the function "void showBoard(int x, int y)" is about setting up the format of the board 

- the outer loop (for (int i = 0; i < 3; i++)) iterates over the rows of the game board.
- the inner loop (for (int j = 0; j < 3; j++)) iterates over the columns of the game board.

the line "printf("%c", board[i][j]);" loops up until "j < 2" which prints " | " and up until "i < 2" which prints " \n\t----------------\n\t ".

the function starting with "int updateBoard(int cell, char playerSign)" is a function that calculates the row and column indices of the section based on the provided cell number, it checks if the cell is already filled, then it updates the game board if the cell is empty, lastly it displays the updated game board and returns whether the move was valid or not.
if its not then "printf("\nInvalid, Cell is already Filled! Try Again.\n");" is printed

the function "int checkWinner(char sg)" is simply a way of individually checking the 2D array for a winner by checking if either player has 3 in a row with every possible outcome of 3 in a row.
here is a flow chart explaining the code from this function:


Start

V

Check all 3 rows

V

Check all 3 columns

V

Check both diagonals

V

If any condition is true, return 1 (indicating a winner)

V

If no winner is found, return 0

V

Loop to start when the next move is made



the entire code constantly makes use of special characters (\n, \t) which are used for formatting the output to a desired quality, like the board for example, its 9 sections cant be all on the same line so the use of formatting characters cleans that up.


## conclusion 
