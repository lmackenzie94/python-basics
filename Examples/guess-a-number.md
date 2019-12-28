```python
import random

print('Hello, what is your name?')
name = input()
print("Well " + name + ", I am thinking of a number b/w 1 and 20")
secretNumber = random.randint(1, 20)

for guessesTaken in range(1, 7): # starts at 1, excludes 7 (i.e. 6 guesses)
    print("Guess a number")
    guess = int(input()) # convert to number because 'input()' returns a string
    if guess < secretNumber:
         print('Too low!')
    elif guess > secretNumber:
        print('Too high!')
    else:
        break

if guess == secretNumber:
    print('Good job, ' + name + '! It only took you ' + str(guessesTaken) + ' guesses')
else:
    print('NOPE! The number I was thinking of was ' + str(secretNumber))
```

    Hello, what is your name?


     Luke


    Well Luke, I am thinking of a number b/w 1 and 20
    Guess a number


     10


    Too low!
    Guess a number


     12


    Too low!
    Guess a number


     14


    Too low!
    Guess a number


     16


    Too low!
    Guess a number


     18


    Too low!
    Guess a number


     19


    Good job, Luke! It only took you 6 guesses
