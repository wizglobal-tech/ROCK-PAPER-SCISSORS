# ROCK-PAPER-SCISSORS

## Table of Contents
- [Project Description](#Project-Description)
- [How to Play](#How-to-Play)
- [Running the Game](#Running-the-Game)
- [Code Explanation](#Code-Explanation)
- [Full Code](#Full-Code)
- [Line-by-Line Explanation](#Line-by-Line-Explanation)
- [Tools and Technologies](#Tools-and-Technologies)
- [Example Usage](#Example-Usage)

### Project Description
This is a simple command-line Rock-Paper-Scissors game written in Python. The game pits the user against a computer opponent, with the computer's choice generated randomly. players can continue playing rounds until they choose to quit, at which point the game displays the final scores and declares an overall winner based on the number of rounds won.

### How to Play
1. Start the Game: Run the Python script in a terminal or command-line interface.
2. Make a Choice: When prompted, type 'Rock', 'Paper', or 'Scissors'. The input is case-insensitive, so 'rock' or 'ROCK' works too.
3. Quit the Game: Type 'Q' (case-insensitive) to exit the game at any time.
4. Round Results: After each round, the computer’s choice and the result (win, lose, or tie) are displayed.
5. Final Results: Upon quitting, the total wins for both the user and computer are shown, along with the overall winner.

### Running the Game
To play the game, you need Python installed on your system. Save the code in a file named rock_paper_scissors.py and run it using the following command:
python rock_paper_scissors.py

### Code Explanation
### Full Code
Here is the complete Python script for the Rock-Paper-Scissors game:
import random
def get_user_choice():
    while True:
        user = input("Enter Rock/Paper/Scissors or Q to Quit: ").capitalize()
        if user == 'Q':
            return 'quit'
        elif user in ["Rock", "Paper", "Scissors"]:
            return user
        else:
            print("Invalid choice. Please enter Rock, Paper, Scissors, or Q.")

def get_computer_choice():
    return random.choice(["Rock", "Paper", "Scissors"])

def determine_winner(user, computer):
    if user == computer:
        return 'tie'
    elif (user == "Rock" and computer == "Scissors") or \
         (user == "Paper" and computer == "Rock") or \
         (user == "Scissors" and computer == "Paper"):
        return 'user'
    else:
        return 'computer'

user_score = 0
computer_score = 0
while True:
    user = get_user_choice()
    if user == 'quit':
        break
    computer = get_computer_choice()
    print(f"Computer chose {computer}")
    result = determine_winner(user, computer)
    if result == 'user':
        print("You win")
        user_score += 1
    elif result == 'computer':
        print("Computer wins")
        computer_score += 1
    else:
        print("It's a tie")

print(f"user won {user_score} time(s)")
print(f"computer won {computer_score} time(s)")
if user_score > computer_score:
    print("The overall winner is user")
elif computer_score > user_score:
    print("The overall winner is computer")
else:
    print("No winner")

### Line-by-Line Explanation
Import Statement

-Line 1: import random
Imports the random module, which provides functions to generate random numbers or choices. Here, it’s used to select the computer’s move.

Function: get_user_choice()
-Line 3: def get_user_choice():
Defines a function to get and validate the user’s input.

-Line 4: while True:
Starts an infinite loop to keep prompting until a valid input is received.

-Line 5: user = input("Enter Rock/Paper/Scissors or Q to Quit: ").capitalize()
Prompts the user to enter a choice and capitalizes the first letter (e.g., 'rock' becomes 'Rock') for consistency.

-Line 6: if user == 'Q':
Checks if the user entered 'Q' (quit).

-Line 7: return 'quit'
Returns the string 'quit' to signal the game should end.

- Line 8: elif user in ["Rock", "Paper", "Scissors"]:
Checks if the input matches one of the valid game choices.

- Line 9: return user
Returns the valid choice ('Rock', 'Paper', or 'Scissors').

-Line 10: else:
Handles any invalid input.

-Line 11: print("Invalid choice. Please enter Rock, Paper, Scissors, or Q.")
Prints an error message and loops back to prompt again.

Function: get_computer_choice()

-Line 13: def get_computer_choice():
Defines a function to generate the computer’s choice.

-Line 14: return random.choice(["Rock", "Paper", "Scissors"])
Uses random.choice() to randomly select and return one option from the list.

Function: determine_winner(user, computer)

-Line 16: def determine_winner(user, computer):
Defines a function to determine the winner, taking the user’s and computer’s choices as arguments.

-Line 17: if user == computer:
Checks if both choices are the same.

-Line 18: return 'tie'
Returns 'tie' if the choices match.

-Line 19: elif (user == "Rock" and computer == "Scissors") or \
-Line 20: (user == "Paper" and computer == "Rock") or \
-Line 21: (user == "Scissors" and computer == "Paper"):
Checks all winning conditions for the user:
Rock beats Scissors
Paper beats Rock
Scissors beats Paper

-The \ continues the line for readability.

-Line 22: return 'user'
Returns 'user' if the user wins.

-Line 23: else:
If it’s not a tie or user win, the computer wins.

-Line 24: return 'computer'
Returns 'computer' as the winner.

Main Game Loop
-Line 26: user_score = 0
Initializes the user’s score to 0.

-Line 27: computer_score = 0
Initializes the computer’s score to 0.

-Line 28: while True:
Starts the main game loop, which runs until the user quits.

-Line 29: user = get_user_choice()
Calls get_user_choice() to get the user’s input and stores it in user.

-Line 30: if user == 'quit':
Checks if the user chose to quit.

-Line 31: break
Exits the loop if the user quits.

-Line 32: computer = get_computer_choice()
Gets the computer’s random choice.

-Line 33: print(f"Computer chose {computer}")
Displays the computer’s choice using an f-string.

-Line 34: result = determine_winner(user, computer)
Determines the winner of the round and stores it in result.

-Line 35: if result == 'user':
Checks if the user won.

-Line 36: print("You win")
Prints a win message.

-Line 37: user_score += 1
Increments the user’s score by 1.

-Line 38: elif result == 'computer':
Checks if the computer won.

-Line 39: print("Computer wins")
Prints a win message for the computer.

-Line 40: computer_score += 1
Increments the computer’s score by 1.

-Line 41: else:
If neither won, it’s a tie.

-Line 42: print("It's a tie")
Prints a tie message.

-Final Results
-Line 44: print(f"user won {user_score} time(s)")
Prints the user’s total wins.

-Line 45: print(f"computer won {computer_score} time(s)")
Prints the computer’s total wins.

-Line 46: if user_score > computer_score:
Checks if the user won more rounds.

-Line 47: print("The overall winner is user")
Declares the user as the overall winner.

-Line 48: elif computer_score > user_score:
Checks if the computer won more rounds.

-Line 49: print("The overall winner is computer")
Declares the computer as the overall winner.

-Line 50: else:
If scores are equal, there’s no overall winner.

-Line 51: print("No winner")
Prints that the game ended in a tie.

### Tools and Technologies

Python 3.x: The programming language used to implement the game.
Standard Library:
random: A built-in Python module for generating random choices, used for the computer’s moves.


Command Line/Terminal: The interface where the game is executed and played.

No additional installations or dependencies are required beyond a standard Python installation.

### Example Usage
Here’s an example of a game session:
Enter Rock/Paper/Scissors or Q to Quit: Rock
Computer chose Scissors
You win
Enter Rock/Paper/Scissors or Q to Quit: Paper
Computer chose Paper
It's a tie
Enter Rock/Paper/Scissors or Q to Quit: Scissors
Computer chose Rock
Computer wins
Enter Rock/Paper/Scissors or Q to Quit: Q
user won 1 time(s)
computer won 1 time(s)
No winner

This demonstrates the game flow, including user input, computer choices, round results, and final scoring.

