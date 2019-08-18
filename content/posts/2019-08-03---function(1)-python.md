---
title: "[PY]Function(1) in Python"
date: "2019-08-03T21:13:18.199Z"
template: "post"
draft: false
slug: "/posts/function(1)-python/"
category: "python fundamentals"
tags:
  - "Python"
  - "Keyword arguments"
  - "dictionary unpacking"
  - "Default arguments"
description: "In Python, you can unpack dictionary to pass its value to a function parameter. In order to take value out of a dictionary"
---

<figure>
    <img src="/media/20190804-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

# 1. Keyword arguments and dictionary unpacking

```python
def favourite_singer(name,debut_year,favSong):
    print('name :', name)
    print('debut_year :', debut_year)
    print('favSong :', favSong)

favourite_singer('Jason Mraz', 2001, "I'm yours")
```

Above is a typical way of calling function. In Python, you can unpack dictionary to pass its value to a function parameter. In order to take value out of a dictionary, you need to use double Asterisk(\*\*) before the name of a dictionary.

```python
my_fav_singer = {
    'name' : 'Jason Mraz',
    'debut_year' : 2001,
    'favSong' : "I'm yours"
}

favourite_singer(**my_fav_singer)
```

# 1-1. Unpacking dictionary rules

### 1) The keywords in dictionary must be string. Otherwise it will result in TypeError.

### 2)The name of keywords in dictionary must be equal to that of function parameter

### 3)The number of keywords in dictionary must be equal to that of function parameter.

```python
my_fav_singer = {
    'name' : 'Jason Mraz',
    'debut_month' : 2001,
    'favSong' : "I'm yours"
}

favourite_singer(**my_fav_singer)

#Error
#Traceback (most recent call last):
#favourite_singer(**my_fav_singer)
#TypeError: favourite_singer() got an unexpected keyword argument **'debut_month'**



my_fav_singer = {
    'name' : 'Jason Mraz',
    'debut_year' : 2001,
}

favourite_singer(**my_fav_singer)

#Error
#Traceback (most recent call last):
#favourite_singer(**my_fav_singer)
#TypeError: favourite_singer() missing 1 required positional argument: **'favSong'**
```

What would happen if you use just one Asterisk(\*)?

As expected, one Asterisk(\*) means unpacking keywords in dictionary.

```python
def favourite_singer(name,debut_year,favSong):
    print('name :', name)
    print('debut_year :', debut_year)
    print('favSong :', favSong)

my_fav_singer = {
    'name' : 'Jason Mraz',
    'debut_year' : 2001,
    'favSong' : "I'm yours"
}

favourite_singer(*my_fav_singer)


#name : name
#debut_year : debut_year
#favSong : favSong
```

# 2. Default arguments

Programmers should consider the number of required positional arguments. If you have three parameters in function and only deliver two arguments, then error will pop up. To prevent this error,

Python allows function arguments to have default values.

```python
def person(firstname, lastname = "Mraz", profession="singer"):
    print(firstname, lastname, "is a(n) American", profession)

person("Jason")
person("Leo", "Yoon", "doctor")
person(firstname="Cozy")
person(firstname="Cozy", profession="nurse")


#Jason Mraz is a(n) American singer
#Leo Yoon is a(n) American doctor
#Cozy Mraz is a(n) American singer
#Cozy Mraz is a(n) American nurse
```

Below is error code

```python
#1
person()

#2
person(firstname="Cozy", "Mraz")

#3
person(age="32")
```

#### #1) In the first call, value is not passed for parameter firstname which is the required parameter

#### #2) In the second call, second argument has no keyword.

#### #3) In the third call, there is no defined parameter of "age", but the passing keyword argument age is passed

---

## We are creating wealth every time we write a code
