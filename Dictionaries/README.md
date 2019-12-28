### Dictionaries

```python
name = {'first': 'Luke', 'last': 'MacKenzie'}
name['first'] + ' ' + name['last']
```

    'Luke MacKenzie'

```python
name = {'first': 'Luke', 'last': 'MacKenzie'}
list(name.keys())
```

    ['first', 'last']

```python
name = {'first': 'Luke', 'last': 'MacKenzie'}
list(name.values())
```

    ['Luke', 'MacKenzie']

```python
name.values() # returns a list-like value
# use list function to convert it
```

    dict_values(['Luke', 'MacKenzie'])

```python
for i in name.values():
    print(i)
```

    Luke
    MacKenzie

```python
for k, v in name.items():
    print(k,v)
```

    first Luke
    last MacKenzie

```python
name = {'first': 'Luke', 'last': 'MacKenzie'}
name.get('middle', 'Andrew')
# checks for key of 'middle', if it does NOT exist, returns 'andrew'
```

    'Andrew'

##### Character Count

```python
import pprint # pretty print

message = 'It was a bright cold day in April, and the clocks were striking thirteen.'
count = {}

for character in message.upper():
    count.setdefault(character, 0) # sets to 0 if key doesn't exist
    count[character] = count[character] + 1

pprint.pprint(count)
```

    {' ': 13,
     ',': 1,
     '.': 1,
     'A': 5,
     'B': 1,
     'C': 3,
     'D': 3,
     'E': 5,
     'G': 2,
     'H': 3,
     'I': 7,
     'K': 2,
     'L': 3,
     'N': 4,
     'O': 2,
     'P': 1,
     'R': 5,
     'S': 3,
     'T': 6,
     'W': 2,
     'Y': 1}

```python

```
