I dislike this kind of condition expression. It's not explicit and it takes time for others to understand.

```python
while not name:
    print('Enter your name:')
    name = raw_input()
```

```python
if numOfGuests:
    print('Be sure to have enrough room for all your guests.')
```

I would rather write the second example like this:

```python
if numOfGuests > 0:
    print('Be sure to have enrough room for all your guests.')
```

It is more explicit what I am trying to do. Sure, number of guests would never be negative. So the obvious posibilities would be 0 (False) or greater than 0 (True). But why not just write like that. It's just more clearer.



