# Slot Machine using Python

This project comprised of slot machine created using the object oriented concepts in Python. The game started with a minimum bet and randomly displayed 3 emotes from a predefined set. It the combination was complete then the winning amount was doubled. If the combination was partially complete, the winning amount was increased to half of the bet. If there was no combination then the bet was removed from winning amount. The game ended when the winning amount was less than two. Bet validation were also added in this project.

Description:

1. This program has 3 classes: Purse, Column and Slot
2. The Slot class inherits all methods and variables from Purse and Column class 

# Purse Class
This class has a constructor with variable balance of float data type which initially set to 10.00. This value will be changed according to the score.

This class has three methods:

1. get_balance() - This returns the user balance.
2. credit() - This method is used to credit the user balance after winning.
3. debit() - This method is used to debit the user balance after losing.


# Column Class

1. In this class I have imported the emoji package inorder to use emoticons of apple, pear and tangerine.
2. I have used "from random import choice" as it imports choice from random to my program and I can use choice method directly instead of random.choice
3. I have initialised a global variable faces which is a list which is used to create a column of each face
4. The constructor is used to append emoticons to the list faces
5. This class has change_face() method. It is used to shuffle values in the list by using choice method


# Slot Class
1. This class is derived from the Purse class and Column class.
2. The constructor is used to accesss constructor of Purse class and Column class. In this constructor I have created 3 variables slot1, slot 2, slot3. In this variables we pass the parameters of emoji(red_apple, pear and tangerine) to the emojize method used in Column class which appends values to the list faces in Column class.

This class has 4 methods:
1. take_bet() - This method is the initial point of the program. It has an input variable bet which stores the value of bet inserted by the user. It checks whether the value is an integer, is greater than 2(as minimum bet is 2) and is greater than the balance available. Else it prints "Please enter a valid bet". The program can be exited by typing 'n' or 'N'. pull_Handle() method is called if its a valid input.
2. pull_Handle() - This method invokes the change_face() of Column class and appends all the values to the local list outputString. After appending all values to the outputString, the show_slot() method is called and we pass value of outputString to show_slot() method.
3. show_slot() - This method prints outputString using a for loop. The score_slot() method is invoked after this method.
4. score_slot() - In this method it checks if all the faces are same then the bet is credited to user balance by invoking credit function from Purse class, else if two faces are same it credits half value to the user balance by invoking credit function from Purse class else it debits the bet from the user balance by invoking debit function from Purse class. This method also prints the score and the user balance which is obtained by invoking get_balance from Purse class.


# run_slot_machine()
This function is used to execute the program of slot machine. I have created an instance variable "spin" of Slot class. The take_bet() of Slot Class is called with the help of instance variable spin