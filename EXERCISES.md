# Exercises

#### Note: 

1- You can attempt these Exercises in an OOP language, such as Python, Java, C/C++, etc. However, the naming of files used in the text of the exercises below presumes that python is used. You can change the file extension to the relevant language which you prefer to use.

2- Save your solution on your git repository.

------------
 
#### Exercise 01: 
Write a program called circle.py that asks the user to enter the radius of a circle. Convert the input to data type float and assign the user input to a variable called radius. The program should then calculate and display the area and circumference of the circle using πr2 for the area and 2πr for the circumference.

*Hint: You can use 3.14159 as the value of pi(π).

------------
#### Exercise 02: 
A company has determined that its annual profit is typically 23 percent of the total sales. Write a program called sales_prediction.py that asks the user to enter the projected amount of total sales and then displays the profit that will be made from that amount. The program should then display the projected total profits for each of the next following 10 years, assuming that the amount of total sales grows by 5 percent every year.

*Make sure that all the printed profits are rounded to 2 decimal places, the underscore character is used to separate the hundreds from the thousands (and the thousands from the millions) groups of digits, and the amounts are 16 characters long with zeros to fill the empty spaces.

------------
#### Exercise 03: 
Write a computer program offer_loan.py to implement the following specification: A bank will offer a customer a loan if they are 21 or over, have an annual income of at least £21000 and has not received a loan in the past. The program takes in input from the user the customer’s age, their income and whether they have received a loan already. The program outputs the string “The loan can be offered: True” if the conditions are met, otherwise ”The loan can be offered: False”.

*Hints: bool() is the type casting function for converting to a boolean type.

------------
#### Exercise 04:
Write a script called exercise1.py that includes assignment statements to perform the following operations with the variables a=1.14, b, and c:
1.	Adds 2 to a and assigns the result to b
2.	Multiplies b by 4 and assigns the result to a
3.	Divides a by 3.14 and assigns the result to b
4.	Subtracts 8 from b and assigns the result to c
5.	Display the final values of a, b and c

------------
#### Exercise 05:
Many people keep time using a 24 hour clock (11:00 is 11am and 23:00 is 11pm, 0 is midnight). If it is currently 13:00 and you set your alarm to go off in 50 hours, it will be 15:00 (3pm). Write a Python program to solve the general version of the above problem. Ask the user for the time now (in hours), and then ask for the number of hours to wait for the alarm. Your program should output what the time will be on the clock when the alarm goes off.

------------
#### Exercise 06:
It is possible to name the days 0 through 6 where day 0 is Sunday and day 6 is Saturday. If you go on a wonderful holiday leaving on day number 3 (a Wednesday) and you return home after 10 nights you would return home on a Saturday (day 6) Write a program which asks for the starting day number, and the length of your stay, and it will tell you the number of day of the week you will return on. 

------------
#### Exercise 07:
Write a script grade.py that asks the user to input the score out of 100. If the input is positive, it assigns grades to the user as the following and prints out the mark (A, B, C, D). If the score is out of range (i.e. < 0 or >100), tell user it’s invalid.

1.	Score < 0	-- invalid
2.	0 <= Score < 30	– D
3.	30 <= score < 50	– C
4.	50 <= score < 70	– B
5.	70 <= score <= 100	– A
6.	Score > 100

------------
#### Exercise 08:
Let us consider a scenario where the user inputs an alphabet and our program tells the user if it is a vowel or a consonant.

letter = input("Please enter a letter : ")

Write a script named alphabet.py that performs this classification and inform the user about it.

------------
#### Exercise 09:

Accept a string from user, write a statement that uses a slicing expression and displays the first 3 characters in the string. Write another statement that uses a slicing expression and displays the last 3 characters in the string. Find out what happens when user only enter string with two characters.

------------
#### Exercise 10:

Write a Python program to ask user for two strings, then display a single string from these two given strings, separated by a space and swap the first two characters of each string. 

*For example,
Sample String : 'abc', 'xyz' 
Expected Result : 'xyc abz'

------------
#### Exercise 11:

Write a Python program to find the substring 'not bad' from a given string, replace the ‘not bad’ substring with 'good'. Display the resulting string.

*Sample String : 'The lyrics is not bad!' 
*Expected Result : 'The lyrics is good!'

------------
#### Exercise 12:

Write a script logic.py that takes three integer inputs x, y and z from the user and check for the truth value of following statements.
1.	x < y or y > z
2.	y != z
3.	x >= z or y > z and x != y


------------
#### Exercise 13:

Write a script security.py which asks the user to input a password as a string. Then we ask the user to re-enter the password and tell him/her if the passwords match or not.

------------
#### Exercise 14:

Write a script for following problem statement.
months = [‘January’, ‘March’, ‘May’,‘September’, ‘December’]
After declaring the above list, the program asks user to input name of a month and checks if it there in the list. If not, it appends that month to our list. The program continues to ask for input unless all 12 months have been entered. Then, it removes May, September and October from the list.

------------
#### Exercise 15:

Create a script which implements the hangman game. First define a list of 10 words. The script randomly selects one of them and the objective is the user to guess the word. At each iteration the user inputs a letter and the script returns if the letter is part of the word. The script iterates until the user provides correctly all the letters of the word (win condition) or the user has done 9 wrong guesses (lose condition)



