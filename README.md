# Team-Project1-rps-game
Play  Rock Paper Scissors against the computer
import random

choices = ["rock", "paper", "scissors"]
computer = random.choice(choices)

class RPSGame:
    def __init__(self, choices, computer):
        self.choices = choices
        self.computer = computer
       
    def play(self, player_choice):
        self.player_choice = player_choice
        print("Starting game...")
        if player_choice not in self.choices:
            raise ValueError("Invalid choice. Please choose either rock, paper or scissors.")

        print(f"Your choice was:\n{self.player_choice}")
        print(f"Displaying computer choice...\nComputer choice is:\n{self.computer}")   
        if player_choice == computer:
            return "It's a tie!"
        elif player_choice == "rock" and computer == "scissors":
            return "You win!"
        elif player_choice == "paper" and computer == "rock":
            return "You win!"
        elif player_choice == "scissors" and computer == "paper":
            return "You win!"
        else:
            return "You lose."

game = RPSGame(choices, computer)
while True:
    try:
        player_choice = input("Enter a choice between words: rock, paper or scissors ").lower()
        result = game.play(player_choice)
        print(result)
        break
    except ValueError as e:
        print(e)
        
