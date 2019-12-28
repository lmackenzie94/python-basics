## Basics

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
