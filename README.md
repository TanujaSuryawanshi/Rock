# Rock

import random

# Choices available in the game
choices = ["rock", "paper", "scissors"]

# Function to get the computer's choice
def get_computer_choice():
    return random.choice(choices)

# Function to get the player's choice
def get_player_choice():
    while True:
        choice = input("Enter your choice (rock, paper, or scissors): ").lower()
        if choice in choices:
            return choice
        else:
            print("Invalid choice. Please choose rock, paper, or scissors.")

# Function to determine the winner
def determine_winner(player_choice, computer_choice):
    if player_choice == computer_choice:
        return "It's a tie!"
    elif (player_choice == "rock" and computer_choice == "scissors") or \
         (player_choice == "scissors" and computer_choice == "paper") or \
         (player_choice == "paper" and computer_choice == "rock"):
        return "You win!"
    else:
        return "You lose!"

# Main function to run the game
def play_game():
    while True:
        print("\n--- Rock, Paper, Scissors Game ---")
        player_choice = get_player_choice()
        computer_choice = get_computer_choice()

        print(f"You chose: {player_choice}")
        print(f"Computer chose: {computer_choice}")

        result = determine_winner(player_choice, computer_choice)
        print(result)

        # Ask if the player wants to play again
        play_again = input("Do you want to play again? (yes or no): ").lower()
        if play_again != "yes":
            print("Thanks for playing! Goodbye!")
            break

if __name__ == '__main__':
    play_game()
