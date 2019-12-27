
# Python Notes


```python
[1,2,3] + [4,5,6]
```




    [1, 2, 3, 4, 5, 6]




```python
len('Hello')
```




    5




```python
len([1,2,3])
```




    3




```python
spam = ['Luke', 'is', 'awesome']
spam[2] = 'dope'
spam
```




    ['Luke', 'is', 'dope']




```python
spam = ['Luke', 'is', 'awesome']
spam[:2] = ['Mike', 'is', 'not'] # from beginning to index 2 (not inclusive)
spam
```




    ['Mike', 'is', 'not', 'awesome']




```python
del spam[2]
spam
```




    ['Mike', 'is', 'awesome']




```python
'Hello' * 3
```




    'HelloHelloHello'




```python
int('20')
```




    20




```python
str(69)
```




    '69'




```python
list('Luke')
```




    ['L', 'u', 'k', 'e']




```python
'howdy' in ['sup', 'hey', 'howdy', 'hi']
```




    True




```python
'ciao' not in ['sup', 'hey', 'howdy', 'hi']
```




    True




```python
greetings = ['sup', 'hey', 'howdy', 'hi']
greetings[-1]
```




    'hi'




```python
greetings = ['sup', 'hey', 'howdy', 'hi']
greetings[1:3] # [inclusive:exclusive], called a 'slice'
```




    ['hey', 'howdy']




```python
for i in range(2, 7): # start at 2, end before 7
    print(i)
    
# NOTE: range() returns a 'list-like' value
# which can be passed to the list() function if you need an actual list value
```

    2
    3
    4
    5
    6



```python
import random
randNum = random.randint(1,5)
if randNum == 2:
    print('Yup, the random number was 2!')
elif randNum == 3: 
    print('Yup, the random number was 3!')
else:
    print('The random number was ' + str(randNum)) # can only concatenate strings
```

    The random number was 5



```python
num = input() # input always returns a string
num = int(input()) # would have to convert to int
```

     10
     10



```python
spam = list(range(0, 10, 2))
spam
```




    [0, 2, 4, 6, 8]




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



```python
supplies = ['paper', 'pencil', 'pens', 'highlighter']
for i in range(len(supplies)): # returns [0,4]
    print('Index ' + str(i) + ' in supplies is: ' + supplies[i])
```

    Index 0 in supplies is: paper
    Index 1 in supplies is: pencil
    Index 2 in supplies is: pens
    Index 3 in supplies is: highlighter



```python
cat = ['fat', 'orange', 'loud']
size, colour, disposition = cat # multiple assignment
print(size, colour, disposition) 

# can also do
first, middle, last = 'Luke', 'Andrew', 'MacKenzie'
print(first, middle, last)
```

    fat orange loud
    Luke Andrew MacKenzie



```python
# Augmented assignment operators
spam = 68
spam += 1
print(spam)
spam *= 0.5
print(spam)
```

    69
    34.5





### Index method


```python
spam = ['hi', 'hello', 'bye']
spam.index('hello')
```




    1



### Append / Insert methods


```python
spam = ['cat', 'dog', 'bat']
spam.append('moose')
spam
```




    ['cat', 'dog', 'bat', 'moose']




```python
spam = ['cat', 'dog', 'bat']
spam.insert(1, 'moose') # insert at index 1
spam
```




    ['cat', 'moose', 'dog', 'bat']



### Remove method


```python
spam = ['cat', 'dog', 'bat']
spam.remove('dog')
spam
```




    ['cat', 'bat']



### Sort method


```python
spam = [3 , 5, 3.14, -10, 22]
spam.sort()
spam
```




    [-10, 3, 3.14, 5, 22]




```python
spam = ['cats', 'dogs', 'ants', 'bears']
spam.sort(reverse=True)
spam
# sorts in ASCII-betical order (i.e. capitals come first)
# so, capital Z will come before lowercase 'a'
# for true alphabetical order, .sort(key=str.lower)
```




    ['dogs', 'cats', 'bears', 'ants']



#### NOTE: mutable values (ex. lists) are not stored 'inside' variables. Instead, variables store a reference to the value(s) spot in memory.
- programming langs do this because lists/array can potentially be very long and it would be "computationally expensive" to make multiple copies of them.


```python
def eggs(someParameter):
    someParameter.append('Hello')

spam = [1,2,3]
eggs(spam)
print(spam) # the function actually changes the value of spam
```

    [1, 2, 3, 'Hello']



```python
import copy # used to create actual copies (i.e. not refs)
spam = ['A', 'B', 'C', 'D']
brandNewCopy = copy.deepcopy(spam)
brandNewCopy.append('BLAHBLAHBLAH')
spam, brandNewCopy
```




    (['A', 'B', 'C', 'D'], ['A', 'B', 'C', 'D', 'BLAHBLAHBLAH'])
