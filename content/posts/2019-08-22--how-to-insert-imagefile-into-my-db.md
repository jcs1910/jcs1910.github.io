---
title: "[MySQL] How to insert imagefile into my db"
date: "2019-08-23T16:25:11.199Z"
template: "post"
draft: false
slug: "/posts/how-to-insert-imagefile-into-my-db/"
category: "MySQL"
tags:
  - "Python"
  - "MySQL"
  - "os.getcwd()"
  - "imagefield"

description: "This post illustrates how I was able to insert imagefile from my os to my database."
---

<figure>
    <img src="/media/nature-photo6.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

This post illustrates how I was able to insert imagefile from my os to my database. Django provides a built-in class specifically for images. `from django.core.files.images import ImageFile` inherits all the attributes and methods of File. When I open the Python shell, I have to import all the necessary files from my django project.

```
    ##import everything from my app models
    from category.models import *
    from users.models import *
    from pins.models import *

    #import necessary files to save local file images in my DB
    from django.core.files.images.import ImageFile
    from django.core.files import File
```

## How to know/change current directory in Python shell?

You can use the `os` module.

```
    >>> import os
    >>> os.getcwd()  # check current path
    '/home/user'
    >>> os.chdir("/tmp/") #change current directory
    >>> os.getcwd()
    '/tmp'
```

1. My current path is

```
    >>> os.getcwd()
    '/home/jcs191072/Desktop/wecode/pinterest-backend'
```

I thought my current path was `'/home/jcs191072/Desktop/wecode/pinterest-backend'` so additional path I need to add was`/pins/test.png` . But this is absolutely wrong path.

```
    >>> b.background_img.save('test.png', File(open('/pins/test.png', 'r')))
    Traceback (most recent call last):
      File "<console>", line 1, in <module>
    FileNotFoundError: [Errno 2] No such file or directory: '/pins/test.png'
```

The right path is `'pins/test.png'` and I had to remove slash(/) to make it right.

```
    >>> b = Category(name = 'animal')
    >>> b.background_img.save('test.png', File(open('pins/test.png', 'r')))
    Traceback (most recent call last):
      File "<console>", line 1, in <module>
      File "/home/jcs191072/miniconda3/envs/pinterest-backend/lib/python3.7/site-packages/django/db/models/fields/files.py", line 87, in save
        self.name = self.storage.save(name, content, max_length=self.field.max_length)
      File "/home/jcs191072/miniconda3/envs/pinterest-backend/lib/python3.7/site-packages/django/core/files/storage.py", line 52, in save
        return self._save(name, content)
      File "/home/jcs191072/miniconda3/envs/pinterest-backend/lib/python3.7/site-packages/django/core/files/storage.py", line 270, in _save
        for chunk in content.chunks():
      File "/home/jcs191072/miniconda3/envs/pinterest-backend/lib/python3.7/site-packages/django/core/files/base.py", line 60, in chunks
        data = self.read(chunk_size)
      File "/home/jcs191072/miniconda3/envs/pinterest-backend/lib/python3.7/codecs.py", line 322, in decode
        (result, consumed) = self._buffer_decode(data, self.errors, final)
    UnicodeDecodeError: 'utf-8' codec can't decode byte 0x89 in position 0: invalid start byte
```

```
After solving the path issue,I get this error:

> `UnicodeDecodeError: 'utf-8' codec can't decode byte 0x80 in position 0: invalid start byte`
```

The solution is opening the files in binary mode ('rb').

    >>> b.background_img.save('test.png', File(open('pins/test.png', 'rb')))
    >>> b.save()

Successfully, I can insert all the required data including imagefile into my db.

<figure>
    <img src="/media/pinterest_db.png" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

---

> **We are creating wealth every time we write a code**
