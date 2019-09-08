---
title: "[PY]JSON to Python Objects"
date: "2019-08-22T16:15:21.199Z"
template: "post"
draft: false
slug: "/posts/json-to-python-objects/"
category: "json-to-python"
tags:
  - "Python"
  - "JSON"
  - "JSON_ENCODING"
  - "JSON_DECODING"

description: "JSON is an abbreviation of Javascript Object Notation"
---

<figure>
    <img src="/media/nature-photo6.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

### **1. JSON**

JSON is an abbreviation of Javascript Object Notation. JSON allows for exchanging data between client(web browser) and server(web server) and is widely used due to its simplicity and flexibility. The most popular JSON format is a collection of Key-Value Pair.

Python has a built-in JSON library, which allows you to use the JSON libray using "import json". Converting the python formats to the JSON string is called JSON encoding and the opposite refer to JSON decoding.

### **2. JSON Encoding**

In order to use JSON encoding, you first need to import json library and use `json.dumps()` method to change Python objects to JSON strings.

```python
import json

user = {
    'id': 100,
    'name': 'Jason Mraz',
    'comments_history': [
       {'date': '2019-05-11', 'comment': 'hello'},
       {'date': '2019-04-13', 'comment': 'Good morning'},
]}

# JSON encoding
jsonString = json.dumps(user)
print(jsonString)
print(type(jsonString))   # class str

# {"id": 100,
# "name": "Jason Mraz",
# "comments_history": [
#   {"date": "2019-05-11", "comment": "hello"},
#   {"date": "2019-04-13", "comment": "Good morning"}
# ]}

#<class 'str'>
```

## 3. JSON 디코딩

Just the same as we did Json encoding, you need to import json library first and use `json.loads() method` to convert a JSON string to a Python grammar.

```python
import json

jsonString = '{"id": 100,
"name": "Jason Mraz",
  "comments_history": [
    {"date": "2019-05-11", "comment": "hello"},
    {"date": "2019-04-13", "comment": "Good morning"}
]}'

# JSON Decoding
dict = json.loads(jsonString)

# Print
print(dict['name'])
for h in dict['comments_history']:
  print(h['date'], h['comment'])

 # Json Mraz
 # 2019-05-11 hello
 # 2019-04-13 Good morning
```

---

> **We are creating wealth every time we write a code**
