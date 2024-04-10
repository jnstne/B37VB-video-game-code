# Aidan Johnstone Noughts and Crosses Game Report

## Introduction
for my video game i decided to make my own version of the pre existing noughts and crosses.
its a game made for 2 players to compete and enjoy

## Instructions of the Game

the game is a very simple concept as its just a classic game of noughts and crosses where 2 players go against each other 
to try and get 3 of their shape in a row while simultaniously stopping the other player from
doing the same

the controls are shown in the game but ill explain them here too,

- Player 1 plays as the symbol X
- Player 2 plays as the symbol O

the noughts and crosses grid is split up into 9 sections each with a connected number (1-9).

Player 1 goes first and picks any of the sections they want to start with by typing the number associated with said section.

then Player 2 continues by choosing a different number than what Player 1 chose and the game continues like this.

the game ends when one player gets 3 of their symbols in a row, whether thats up & down, left & right or diagonal.

alternatively the game also ends when all 9 sections have been filled and no winner is found, hence the result is a draw.

when a game is completed a prompt will come up asking the player if they'd like to play again or terminate the run, also any game can be terminated by typing -1.

## Code Explanation

comments have been left throughout the entire code to briefly explain what each section of code is for.

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

the function "void playNC()" starts by initializing some variables:

- "int gameResult = 0;" initializes a variable gameResult to store the result of the game (0 for no result, 1 if player 1 wins, 2 if player 2 wins).
  
- "int cell = 0;" initializes a variable cell to store the player's input for the cell number they want to mark (1-9).

- "int playCount = 0;" initializes a variable playCount to keep track of the number of moves played.

- "int updationResult = 1;" initializes a variable updationResult to store the result of updating the game board (1 for successful update, 0 for unsuccessful update).

- "char playerSign = ' ';" initializes a variable playerSign to store the symbol ('X' or 'O') of the current player.

the while loop (while (!gameResult && playCount < 9)) continues until the gameResult is non-zero (indicating a win) or playCount reaches 9 (indicating a draw).

within the loop, the current player is determined based on the value of "playCount % 2". If playCount is even, it's player 1's turn (X), otherwise it's player 2's turn (O).

the player is prompted to enter a cell number where they want to place their symbol.
then the input is validated, If the entered cell number is valid (between 1 and 9), the game board is updated using the updateBoard() function.

after updating the board, the checkWinner() function is called to determine if the current player has won the game.
if the game result is 1 or 2 (depending on which player wins the game) the winner is announced, and the loop exits.

if the entered cell number is invalid, the player is prompted to enter a valid cell number.

if no winner is found and all cells are filled (i.e., playCount reaches 9), it's a draw.
the function prints the result of the game (win, draw) and displays "--- Game Over ---".

this final section "int main()" is for calling functions that make the game run and printing whats required of those functions for the player to see and use.
instructions for the game are printed using said printf statements, including player signs, how to exit the game, and cell numbers on the board. 
whereas "initializeBoard();" Calls the initializeBoard() function to initialize the game board.

"char start = ' ';" declares the variable "start" to store the player's input for starting the game.
printf("\n> Press Enter to start!");: prompts the player to press Enter to start the game and "scanf("%c", &start);" takes that input for the player pressing Enter.

if the player presses Enter start becomes true and the game loop starts.
inside the loop, the playNC() function is called to start playing the game.

after playing the game, the player is prompted with a menu to either play again or end the game.
if the player chooses to play again (if the function userChoice is 1), the game board is reinitialized using initializeBoard().
the loop continues until the player chooses to end the game (if the function userChoice is 0).

after exiting the game loop, a message thanking the player for playing the game is displayed and "return 0;" indicates successful completion of the main() function.

the entire code constantly makes use of special characters (\n, \t) which are used for formatting the output to a desired quality, like the board for example, its 9 sections cant be all on the same line so the use of formatting characters cleans that up.

## Conclusion 

overall this was just my take on the classic game noughts & crosses with hopefully a clear and consise guide on the making of my code.

