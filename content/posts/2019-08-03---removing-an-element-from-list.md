---
title: "[PY]Removing an element from List"
date: "2019-08-04T14:23:38.199Z"
template: "post"
draft: false
slug: "/posts/removing-an-element-from-list/"
category: "python fundamentals"
tags:
  - "Python"
  - "For Loop"
  - "Shallow Copy"
  - "Deep Copy"
description: "You should think twice when removing items from a list while iterating over it"
---

<figure>
    <img src="/media/20190805-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

First and foremost, let's write a function to remove odd numbers from a list.

```python
def remove_odd_numbers(n):
    	remove_odd_numbers
```

What kinds of methods did you use to solve it? remove method or del method?? Didn't you use `for loop` while using them?

Did you get it right? If not, ponder why you get an incorrect answer?

## For loop

You should think twice when removing items from a list while iterating over it. When you remove items from a list, then the index position of each item is constantly changing and their turns can be skipped.

```python
    def remove_odd_numbers(n):
    	for i in n:
    		if i % 2 != 0:
    			n.remove(i)
       print n
       return n

    # a = remove_odd_numbers([1,2,3,4,5,6,7,8,9,10,11])
    # print(a)
    # result: [2, 4, 6, 8, 10]
```

Still confused? Let me show you the same for loop with `index` added.

```python
    def remove_odd_numbers(n):
        for index,value in enumerate(n):
            print(index)
            print(value)
            if value % 2 == 1:
                n.remove(value)
                print(n)
        print(n)

    '''Result:
    Index : 0
    Value : 1
    a List after removing one item: [2, 3, 4, 5, 6, 7, 8, 9, 10, 11]
    Index :1
    Value :3
    [2, 4, 5, 6, 7, 8, 9, 10, 11]
    Index :2
    Value :5
    [2, 4, 6, 7, 8, 9, 10, 11]
    Index :3
    Value :7
    [2, 4, 6, 8, 9, 10, 11]
    Index :4
    Value :9
    [2, 4, 6, 8, 10, 11]
    Index :5
    Value :11
    [2, 4, 6, 8, 10]
    [2, 4, 6, 8, 10]
    '''
```

Did you catch the difference? While the list is iterated, some of the items are just skipped, because of different positions. To avoid this, what you need to is to make a shallow copy of list.

```python
    def remove_odd_numbers(n):
        for value in n[:]:
            print(value)
            if value % 2 == 1:
                n.remove(value)
                print(n)
        print(n)

    #result: [2, 4, 6, 8, 10] // all the odd numbers are removed
```

Shallow Copy & and Deep Copy

### `n[:] is a shallow copy of list n.`

In other words, thanks to `n[:]`, the index of `for loop` starts with **zero.** So every time the list of n is iterated, it will spit out zero, allowing every item to be passed in if statement. \*\*\*\*

However, the better way to remove an item from a list is to use **`filter method.`**

```python
    def remove_odd_numbers(x):
        return x % 2 == 0

    a = [1,2,3,4,5,6,7,8,9,10,11]
    n = list(filter(remove_odd_numbers, a))
    print(n)

    #result:
    #[2, 4, 6, 8, 10]
```

### Instead, you can make use of lambda expression.

```python
    a = [1,2,3,4,5,6,7,8,9,10]
    n= list(filter(lambda x: x % 2 == 0, a))
    print(n)

    #result:
    #[2, 4, 6, 8, 10]
```

---

> **We are creating wealth every time we write a code**
