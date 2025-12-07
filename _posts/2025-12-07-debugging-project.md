Wazih Taosif
<br>
December 7th, 2025

# Debugging Blog

<h1>What is Debugging?</h1>

Debugging is the process of finding, analyzing, and fixing errors (or "bugs") in software or hardware to ensure it functions correctly. It involves identifying the root cause of a problem, implementing a fix, and then testing the correction to make sure it works as intended.

And since I am studying Full Stack Development at the STEAM Center, I have to deal with debugging codes in my projects almost every single day. In order to tackle debugging, I first read through the code, and also keep in mind what the code is supposed to do. For instance a code could be written in a program to simply add two numbers. After that, if a problem occurs in the code, meaning the correct answer is not being outputed, I try to find any possible mistakes in the code. Then after finding the mistakes, I correct them, and then I run the code again. If the code works fine then, I move on.

In my class I was given a debugging project to work on. There were several mistakes in the codes, and I had to find mistakes in the code, and write the solutions. It was quite a fun experience debugging the codes, and I would like to elaborate how I went on with debugging the code below.

<h2>Code Snippet 1</h2>

```python
text = "Hello, world, my name is"
count = 0

for char in text:
    if char == "":
       count += 1

print(count)
```
This was the original code given to me. The code was supposed to count how many spaces are there in between the text. In technical terms, it was supposed to count the spaces in a string. Now the problem is very obvious, and it is a logical error. specifically in line 4 it is written 
```python
if char == "":
```
We just need to change that to 
```python
if char == " ":
```
This is because python understand "" as nothing, but " " as space. 

Thus the final code will look like:
```python
text = "Hello, world, my name is" # given string
count = 0

for char in text:
    if char == " ": #only runs the following statement when it detects a space in the loop
       count += 1

print(count)
```

<h2>Code Snippet 2</h2>

```python
print("give me a number")
n = input()

for num in range(1, n):
    if num % 2 < 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```
The given code is supposed to tell us if the numbers from 1 to n is even or odd, 'n' being the maximum number, so if n = 10, it would check and tell us which numbers from 1 to 10 are even and which are odd. But the code does not even run. This is because there are 3 problems.

<strong>First problem:</strong> The inputed number by the user is a string not an integer. So we need to fix it by converting the data type of n from string to integer. <br>
<strong>Second problem:</strong> It doesn’t include the imputed number (n). We can fix it by incrementing n by 1 in line 3, making sure it counts n too. This has to be done because in python the range() function does not include the last number. <br>
<strong>Third problem:</strong>It only prints the else condition’s statement. This is mainly because there is a problem in the if condition. So on line 4 we need to change the condition to: <strong>if num % 2 == 0.</strong> This will thus only print the following statement if the remainder is 0. <br>  

So the final code will look like:

```python
n = int(input()) # takes a integer input

for num in range(1, n + 1): #n + 1 includes n too.
    if num % 2 == 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```

<h2>Code Snippet 3</h2>

```python
num = int(input("Enter an integer: "))

if num < -1:
  print("No negative numbers.")
else:
  result = 1
  for i in range(1, num):
    result *= i   

  print("Factorial of " + num + "is" + result)
```

The objective of the code is to calculate the factorial of a given number. But once again the code fails to run. Well in this case, there are two problems in the code. <br>

<strong>First problem:</strong> The end print statement doesn’t work as we can’t add strings with integers with a plus (+) sign. So instead we can use a formating method. So we will use print(f””) instead, and placing the variables ‘num’, and ‘result’ inside curly brackets {}. <br>

<strong>Second problem:</strong> The result isn’t correct as the loop doesn’t iterate the correct amount of time. To fix it we need to include the inputted integer ‘num’. So change the range of for loop to (1, num + 1)<br>

The final code will look like:
```python
num = int(input("Enter an integer: "))

if num < -1:
  print("No negative numbers.") # negative numbers cant be factorial as it is undefined.
else:
  result = 1
  for i in range(1, num + 1): # includes the inputted integer num. 
    result *= i   #result of the factorial of the given integer 'num'. 

  print(f"Factorial of {num} is {result}")
```

<h2>Code Snippet 4</h2>

```python
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1

    if password == "incorrect_password":
        print("Correct password!")
    else:
        print("Incorrect password")

    if attempts > 3:
        print("Too many attempts")
        break
```
The objective of the code is to ask user to enter the correct password but only give them 3 attempts. But it doesn't work like we want. There are three issues with the code.

<strong>First problem:</strong> It doesn’t print ‘correct password!’ even when the user gets it correct. In order to fix it, we need to change condition of first if condition to password == correct_password. <br>
<strong>Second problem:</strong> It gives the user 4 attempts instead of 3. To fix it the last if statement should be  if attempts == 3. This is because this way it will stop the code when attempts is 3, and not more than 3. <br>
<strong>Third problem:</strong> It doesn’t end the code when the user gets it correct. So, we need to put a break statement in the first if statement after print(“correct password!”). The break statement will stop the code when the if condition is met. <br>

Thus the final code will be:

```python
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1

    if password == correct_password:
        print("Correct password!")
        break
    else:
        print("Incorrect password")

    if attempts == 3:
        print("Too many attempts")
        break
```


