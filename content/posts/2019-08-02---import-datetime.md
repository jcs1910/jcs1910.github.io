---
title: "[Py]Import datetime"
date: "2019-08-02T18:43:18.169Z"
template: "post"
draft: false
slug: "/posts/import-datetime/"
category: "python fundamentals"
tags:
  - "Python"
  - "Import Datetime"
description: "In order to use a date in Python, you first need to import a module named `datetime`. The `datetime` module has various class types,"
---

<figure>
    <img src="/media/20190803-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

In order to use a date in Python, you first need to import a module named `datetime`. The `datetime` module has various class types, but the most common use of class types is class `datetime` which is a combination of a date and a time. Do not confuse `datetime()` class (constructor) with `datetime` module. They just have same name.

Its attributes are `year, month, day, hour, minute, second, microsecond` in sequence order.

```python
    import datetime

    currentTime = datetime.datetime.now()

    print(currentTime.year)
    print(currentTime.month)
    print(currentTime.day)
    print(currentTime.hour)
    print(currentTime.minute)
    print(currentTime.second)
    print(currentTime.strftime("%A")) # day of week
```

The last example of strftime is a method for formatting date objects into human readable strings. `strftime()` method takes one parameter, something similar to regular expression. You can check all the legal format codes below if you're not sure what parameter you choose.

## datetime.datetime.strftime(parameter)

<figure>
    <img src="/media/python20190801.png" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

references: [https://docs.python.org/3.7/library/datetime.html](https://docs.python.org/3.7/library/datetime.html)

---

## We are creating wealth every time we write a code
