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

          
