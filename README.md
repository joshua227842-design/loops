Lab - Loops in Python
Joshua Vega CISC 179

1. While loop
a. The n sequence (Collatz Conjecture)
I used a while loop to change the number until it reaches 1. I also added a counter for the steps.

```python

n0 = int(input("Enter a number: "))
steps = 0

while n0 != 1:
    if n0 % 2 == 0:
        n0 = n0 // 2
    else:
        n0 = 3 * n0 + 1
    print(n0)
    steps += 1

print("steps =", steps)

```
b. Infinite loop and fix
First, I made a loop that never stops, and then I used break to fix it.

```python

# Infinite loop (Don't run this forever!)
# while True:
#    print("Infinite")

# Fixed with a condition or break
x = 0
while True:
    print(x)
    x += 1
    if x == 5:
        break
```
c. Simple Calculator with Restart
This program asks for numbers and an operation, then asks if you want to play again.
```python
while True:
    num1 = int(input("Number 1: "))
    num2 = int(input("Number 2: "))
    op = input("Operation (+, -, *, /): ")

    if op == "+": print("Result:", num1 + num2)
    elif op == "-": print("Result:", num1 - num2)
    elif op == "*": print("Result:", num1 * num2)
    elif op == "/": print("Result:", num1 / num2)

    choice = input("Do you want to continue? (y/n): ").lower()
    if choice != "y":
        print("Have a good day.")
        break



2. For loops
a. Character Counter
I used a for loop to go through the text. I ignored everything that is not a letter using .isalpha() and kept track of the counts.


```python

text = "To be, or not to be, that is the question"
text = text.lower()
total_letters = 0
counts = {}

for char in text:
    if char.isalpha():
        total_letters += 1
        if char in counts:
            counts[char] += 1
        else:
            counts[char] = 1

print("Total number of alphabets:", total_letters)
print("Total number of distinct alphabets are:")
for letter in counts:
    print(letter, "=", counts[letter])
        ```


        Challenges
The most difficult part was the character counter in part 2a i had to remember to use .lower() so T and t are counted as the same letter. Also, using a dictionary to store the counts was a bit tricky, but it is easier than having many variables. 
