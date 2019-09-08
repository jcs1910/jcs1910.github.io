---
title: "[Django] Django model: A Primer"
date: "2019-08-19T11:15:18.199Z"
template: "post"
draft: false
slug: "/posts/django-model/"
category: "Django"
tags:
  - "Python"
  - "Django"
  - "Model"
  - "APP"

description: "In this Django article series, you will learn the process of Django project and apps."
---

<figure>
    <img src="/media/nature-photo4.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

In this Django article series, you will learn the process of Django project and apps. Let's learn how to create an app in a Django project and create and use models to store data needed for a new app.

## Create a Django project

```python
django-admin startporject my_twitter
```

## Create a Django app

```python
python manage.py startapp users
# Your project, my_twitter, has many features like users, comments.
```

Once created the app, you will see the below structures.

```python
    |-- test01
    |   |-- __init__.py
    |   |-- settings.py
    |   |-- urls.py
    |   |-- wsgi.py
    |-- users
    |   |-- __init__.py
    |   |-- admin.py
    |   |-- apps.py
    |   |-- models.py
    |   |-- tests.py
    |   |-- views.py
    |-- manage.py
```

The files at the bottom of the newly created app play the following roles.

`admin.py`: default admin screen configuration provided by django
`apps.py`: the main app file
`models.py`: The models file for your app
`tests.py`: a test file
`views.py`: the application's views file

## Always add your new app to settings.

Don't forget to add the newly created app to settings.INSTALLED_APPS.

```python
    INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'users',
    ]
```

## Create Models

```python
from django.db import models

class Tweets(models.Model):
  # Fields
  name = models.CharField(max_length=30)
  contents = models.CharField(max_length=300, null=True)
  created_at = models.DateTimeField(auto_now_add=True)
  updated_at = models.DateTimeField(auto_now=True)

  #Metadata
  class Meta:
    db_table = "tweets"

  #Method
  def __str__(self):
      """String for representing the Tweets object (in Admin site etc.)."""
      return self.name
```

`class Tweets (models.Model):` defines the model. (Don't forget that models are objects.)

## Fields

To define attributes such as name, contents, created_at, and updated_at, it is necessary to determine what kind of data type each field has. Data types include text, numbers, dates, and references to other objects such as users.

### Common Field Arguments

1. `NULL:` If True, Django will store empty NULL values in the database for the field (Character will save an empty string instead). The default value is `False`.

2. `BLANK:` If 'True', the 'field' is allowed to be left blank in the form. The default is `False`, which means that Django's form verification will force you to enter a value. This is often used with null = True. This is because when you allow a blank value, the database must be able to display the blank value appropriately.

## Creating Migrations

With the model created, the first thing you need to do is create a migration for it. You can do this with the following command:

```python
$ python manage.py makemigrations users

#Migrations for 'users':
 # historical_data/migrations/0001_initial.py
   #  - Create model PriceHistory
```

## Applying Migrations

You have now created the migration, but to actually make any changes in the database such as mysql, SQLite or Oracle, you have to apply it with the management command migrate:

```python
$ python manage.py migrate
```

---

> **We are creating wealth every time we write a code**
