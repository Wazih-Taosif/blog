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
