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

NOTE: List methods also work on strings

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
