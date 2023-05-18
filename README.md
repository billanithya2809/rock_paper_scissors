# rock_paper_scissors
import random

def determine_winner(player_choice, computer_choice):
    """
    Determine the winner of the game based on the choices made by the player and the computer.
    """
    if player_choice == computer_choice:
        return "It's a tie!"

    if (player_choice == "rock" and computer_choice == "scissors") or \
       (player_choice == "paper" and computer_choice == "rock") or \
       (player_choice == "scissors" and computer_choice == "paper"):
        return "You win!"
    else:
        return "Computer wins!"

def play_game():
    """
    Play a game of Rock-Paper-Scissors.
    """
    choices = ["rock", "paper", "scissors"]

    while True:
        print("Rock, Paper, Scissors")
        print("---------------------")
        print("1. Rock")
        print("2. Paper")
        print("3. Scissors")
        print("4. Quit")

        # Get the player's choice
        choice = input("Enter your choice (1-4): ")

        if choice == "4":
            print("Goodbye!")
            break

        if choice not in ["1", "2", "3"]:
            print("Invalid choice. Try again.")
            continue

        player_choice = choices[int(choice) - 1]
        computer_choice = random.choice(choices)

        print(f"\nYou chose: {player_choice}")
        print(f"Computer chose: {computer_choice}\n")

        result = determine_winner(player_choice, computer_choice)
        print(result + "\n")

play_game()
