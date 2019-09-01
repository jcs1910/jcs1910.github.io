---
title: "[MySQL] mysql access denied eror and set new password"
date: "2019-08-16T23:15:11.199Z"
template: "post"
draft: false
slug: "/posts/mysql-access-denied/"
category: "MySQL"
tags:
  - "Python"
  - "MySQL"
  - "set new password"

description: "ERROR 1054 (42S22): Unknown column 'password' in 'field list'"
---

<figure>
    <img src="/media/nature-photo3.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

I had a issue with mysql access due to unknown passoword. Since I didn't set my password during the installation, I had to set a new password.

```
UPDATE user set password=password("my_password123") WHERE user = 'root';
```

But a new MYSQL version changed the settings of new password field. That's why, the below code line produced a error message.

```
ERROR 1054 (42S22): Unknown column 'password' in 'field list'
```

Enter the below updated database (set authentication_string=password)

```
UPDATE user set authentication_string=password("my_password123") WHERE user = 'root';
```

Make sure you add flush privileges to confirm your new password

```
mysql> flush privileges;
Query OK, 0 rows affected (0.00 sec)
mysql> exit;
```

---

> **We are creating wealth every time we write a code**
