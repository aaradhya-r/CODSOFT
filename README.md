# CODSOFT
CODSOFT internship task includes simple calculator , rock paper and scissors game , and password generator.
## CALCULATOR
/code
  def add(a,b):
      return a + b
  def subtract(a,b):
      return a - b
  def multiply(a,b):
      return a * b
  def divide(a,b):
      if b == 0:
           return "Undefined"
      else:
          return a / b
  print("Welcome to simple calculator")
  print("Slect arithmetic operation:")
  print("1.Addition")
  print("2.Subtraction")
  print("3.Multiplication")
  print("4.Division")
  while True:
       choice = input("Enter choice:")
       if choice in ('1','2','3','4'):
          x = float(input("Enter first number:"))
          y =float(input("Enter second number:"))
          if choice == '1':
             print("Result:", add(x, y))
          elif choice =='2':
                print("Result:", subtract(x, y))
          elif choice =='3':
                print("Result:", multiply(x, y))
          elif choice == '4':
                print(Result:", divide(x, y))
          break
       else:
            print("Invalid input")
            
## ROCK PAPER SCISSORS GAME
/CODE
import random
def play_game():
    while True:
        user_choice = input("Enter your choice(rock,paper,) or 'quit' to exit game")
        if user_choice == 'quit':
           print("Thanks for playing")
           break
        if user_choice not in ["rock", "paper", "scissors"]:
                     print("Invalid choice.Please enter rock, paper, or scissors.")
                     continue
        computer_choice = random.choice(["rock", "paper", "scissors"])
        print("You choose:", user_choice)
        print("Computer choose:", computer_choice)
        if user_choice == computer_choice:
           print("It's a tie!")
        elif user_choice == "rock":
           if computer_choice == "scissors":
              print("You Win!")
           else:
              print("Computer Wins!")
        elif user_choice == "paper":
           if computer_choice == "rock":
              print("You Win!")
           else:
              print("Computer Wins!")
        elif user_choice == "scissors":
           if computer_choice == "paper":
              print("You Win!")
           else:
              print("Computer Wins!")
play_game() 

## PASSWORD GENERATOR
/CODE
import random
import string
import time
def gen_psword(length):
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ' '.join(random.choice(characters) for _in range(length))
    return password
def main():
    try:
        length = int(input("Enter the desired length of the password: "))
        if length <= 0:
            print("Length must be a positive integer")
            return
        delay = random.uniform(1, 3)
        time.sleep(delay)
        password = gen_psword(length)
        print("Generate password:", password)
    except ValueError:
       print("Enter a valid integer for the length")
if __name__ == "__main__":
    main()

## ROCK PAPER SCISSORS GAME WITH GUI

from tkinter import *
import tkinter.font as font
import random

root = Tk()
root.title("Rock Paper Scissors Game")
app_font = font.Font(size = 12)
root.config(bg = '#FFE873')
root.geometry('700x300')

player_score = 0
computer_score = 0
options = [('rock', 0), ('paper', 1), ('scissors', 2)]

Label(text = 'Rock Paper Scissors Game', font = font.Font(size = 20), bg = '#FFE873').pack()

def player_choice(player_input):
    global player_score, computer_score
    computer_input = get_computer_choice()
    player_choice_label.config(text = 'You Selected : ' + player_input[0])
    computer_choice_label.config(text = 'Computer Selected : ' + computer_input[0])
    if player_input == computer_input:
       winner_label.config(text = "Tie")
    elif (player_input[1]-computer_input[1]) % 3 == 1:
        player_score += 1
        winner_label.config(text="You Won!!!")
        player_score_label.config(text = 'Your Score : ' + str(player_score))
    else:
        computer_score += 1
        winner_label.config(text="Computer Won!!!")
        computer_score_label.config(text='Your Score : ' + str(computer_score))

def get_computer_choice():
    return random.choice(options)

winner_label = Label(text = "Let's start the Game...", fg = 'green', bg = '#FFE873', font = font.Font(size = 13), pady = 8)
winner_label.pack()

input_frame = Frame(root, bg = '#FFE873')
input_frame.pack()

player_options = Label(input_frame, text = "Your Options : ", font = app_font, fg = 'grey', bg = '#FFE873')
player_options.grid(row = 0, column = 0, pady = 8)

rock_btn = Button(input_frame, text = 'Rock', width = 15, bd = 0, bg = 'pink', pady = 5, command = lambda: player_choice(options[0]))
rock_btn.grid(row = 1, column = 1, padx = 8, pady = 5)

paper_btn = Button(input_frame, text = 'Paper', width = 15, bd = 0, bg = 'silver', pady = 5, command = lambda: player_choice(options[1]))
paper_btn.grid(row = 1, column = 2, padx = 8, pady = 5)

scissors_btn = Button(input_frame, text = 'Scissors', width = 15, bd = 0, bg = 'light blue', pady = 5, command = lambda: player_choice(options[2]))
scissors_btn.grid(row = 1, column = 3, padx = 8, pady = 5)

score_label = Label(input_frame, text = 'Score : ', font = app_font, fg = 'grey', bg = '#FFE873')
score_label.grid(row = 2, column = 0)

player_choice_label = Label(input_frame, text = 'You Selected : ---', font = app_font, bg = '#FFE873')
player_choice_label.grid(row = 3, column = 1, pady = 5)

player_score_label = Label(input_frame, text = 'Your Score : 0', font = app_font, bg = '#FFE873')
player_score_label.grid(row = 3, column = 2, pady = 5)

computer_choice_label = Label(input_frame, text = 'Computer Selected : ---', font = app_font, fg = 'black', bg = '#FFE873')
computer_choice_label.grid(row = 4, column = 1, pady = 5)

computer_score_label = Label(input_frame, text = 'Computer Score : 0', font = app_font, fg = 'black', bg = '#FFE873')
computer_score_label.grid(row = 4, column = 2, padx = (10,0), pady = 5)

root.mainloop()
              
        
          
