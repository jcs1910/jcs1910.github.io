---
title: "[Py]String Interpolation"
date: "2019-08-01T17:26:21.169Z"
template: "post"
draft: false
slug: "/posts/string-interpolation/"
category: "python fundamentals"
tags:
  - "Python"
  - "String interpolation"
  - "Formatted string literals"
  - "Multiline f-strings and line break"
description: "There are two existing ways to format Strings. One is string modulo operator(%) and the other is str.format(value). The former is old and the latter is relatively new"
---

There are two existing ways to format Strings. One is string modulo operator(%) and the other is str.format(value). The former is old and the latter is relatively new.

<figure>
    <img src="/media/20190802-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

- **Syntax: {}.format(value)**
- **(value) : Can be an integer, floating point numeric constant, string, characters or even variables.**

### 1. string modulo operator(%)

```python
    #2
    format = "there is %s culture among %s"
    wecode = ("implict-rule", "wecoders")
    print(format % wecode)
```

### 2. str.format(value)

```python
    #1
    wecode = 'We are {} who believe are creating wealth every time we write {}'.format("wecoders", "code")
    print(wecode)

    #2
    wecode = '{0} are writing {1} '.format("wecoders", "code")
    print(wecode)
```

There are so many cool stuff coming out every day in programming languages and Python is no different. Why don't you try more new, easy and improved way to format Strings in Python.

# 1. Formatted string literals

Formatted string literals was joined in Python 3.6, which was written by Eric V. Smith in August of 2015. **F-strings** are string literals which have an **f** at the beginning and **curly braces** containing expressions that will be replaced with their values. f-strings are known to be faster than old versions of both %-formatting and str.format()

```python

    name = "Jason Mraz"
    age = 32

    #LowerCase
    print(f"Hello, I'm {name} and I'm {age} years old")
    #UpperCase
    print(F"Hello, I'm {name} and I'm {age} years old")
```

You can also interchangeably use capital letter **F.** It's pretty simple and familiar to someone who's pro at Javascript. `${variable}`

Plus, there are multiple use cases of f-strings.

- Method with strings.

```python
    name = "jason mraz"
    job = "SINGER-SONGWRITER"

    print(f"{name.upper()} is a great {job.lower()}!!")
```

- Call functions

```python
    def to_lowercase(input):
        return input.lower()

    print(to_lowercase('JASON MRAZ'))
```

- **Multiline f-strings and line break**

1. You always need to put an f(or F) in front of each line of a multiline string in order for Python to read code properly.

```python
    name = "Jason Mraz"
    job = "singer-songwriter"
    debut_album = "Jason Mraz Live & Acoustic 2001"

    profile = (f"He is {name}",
    F"a {job}, who first came to prominence in San Diego in 2000 and"
    F"his debut album was {debut_album}"
    )
    print(profile)
    #('He is Jason Mraz', 'a singer-songwriter, who first came to prominence in San Diego in 2000 andhis debut album was Jason Mraz Live & Acoustic 2001')
```

What is there is no parentheses in the start and end sentences?? Python only reads the first line of a sentence and ignore the following line of sentences.

```python
    name = "Jason Mraz"
    job = "singer-songwriter"
    debut_album = "Jason Mraz Live & Acoustic 2001"

    profile = f"He is {name}",
    F"a {job}, who first came to prominence in San Diego in 2000 and"
    F"his debut album was {debut_album}"

    print(profile)
    #('He is Jason Mraz',)
```

To make the code interpreted, you need to use backslash \ in the end of every sentence so that you can spread strings over multiple lines.

```python
    name = "Jason Mraz"
    job = "singer-songwriter"
    debut_album = "Jason Mraz Live & Acoustic 2001"

    profile = f"He is {name}, "\
    F"a {job}, who first came to prominence in San Diego in 2000 and " \
    F"his debut album was {debut_album}"\

    print(profile)
    # He is Jason Mraz, a singer-songwriter, who first came to prominence in San Diego in 2000 and his debut album was Jason Mraz Live & Acoustic 2001
```

But, the better way is to use three double quote """ and use just one f in the first sentence.

```python
    name = "Jason Mraz"
    job = "singer-songwriter"
    debut_album = "Jason Mraz Live & Acoustic 2001"

    profile = f"""
    He is {name}, a {job},
    who first came to prominence
    in San Diego in 2000 and his debut album was {debut_album}
    """

    print(profile)

    #He is Jason Mraz, a singer-songwriter,
    #who first came to prominence
    #in San Diego in 2000 and his debut album was Jason Mraz Live & Acoustic 2001
```

## Dictionaries

Be careful with quotation marks when using f-strings. If you want to use a single quotation marks for the keys of the dictionary, you should use different quotation marks. f-strings for a single quotations marks and calling for dictionaries for double quotations marks. Or vice versa.

```python
    #different quotations marks
    name = "Jason Mraz"
    job = "singer-songwriter"
    debut_album = "Jason Mraz Live & Acoustic 2001"

    Jason_Mraz = {'name': "Jason Mraz", 'job': "singer-songwriter"}
    print(f'His name is {Jason_Mraz["name"]} and {Jason_Mraz["job"]}')

    #different quotations marks
    name = "Jason Mraz"
    job = "singer-songwriter"
    debut_album = "Jason Mraz Live & Acoustic 2001"

    Jason_Mraz = {'name': "Jason Mraz", 'job': "singer-songwriter"}
    print(f"His name is {Jason_Mraz['name']} and {Jason_Mraz['job']}")
```

```python
You cannot use escape \ inside the value of dictionary in f-strings.

    name = "Jason Mraz"
    job = "singer-songwriter"
    debut_album = "Jason Mraz Live & Acoustic 2001"

    Jason_Mraz = {'name': "Jason Mraz", 'job': "singer-songwriter"}
    print(f"His name is {Jason_Mraz["\name"\]} and {Jason_Mraz["\job"\]}")
```

---

## We are creating wealth every time we write a code
