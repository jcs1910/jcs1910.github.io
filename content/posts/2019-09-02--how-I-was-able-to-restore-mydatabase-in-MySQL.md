---
title: "[MySQL] How I was able to restore my database in MYSQL after Ubuntu installation"
date: "2019-09-02T19:35:11.199Z"
template: "post"
draft: false
slug: "/posts/how-I-was-able-to-restore-mydatabase-in-MySQL/"
category: "MySQL"
tags:
  - "DATABASE"
  - "MySQL"
  - "UBUNTU"

description: "This is how I was able to restore MySQL database from physical files."
---

<figure>
    <img src="/media/nature-photo7.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

Tough times have been passed. I struggled with Ubuntu re-installation because of abnormal NVIDIA graphic issue. I had no choice but to reinstall my Ubuntu. The big issue among many things was I had to backup my MYSQL db since it wasn't saved on AWS.

This is how I was able to restore MySQL database from physical files.

```
1. Install mysql-server

    sudo apt-get update
    sudo apt-get install mysql-server
```
1.1 If you already installed mysql and have a issue with its root login. Remove it and re-install
```
    sudo apt-get remove --purge mysql*
    sudo apt-get autoremove
    sudo apt-get autoclean
    sudo apt-get install mysql-server mysql-client
```
2. Define mysql root password and other security-related options, including removing remote access to the root user and setting the root password
```
    sudo mysql_secure_installation utility
```
3. If you can not access mysql, then enter below commend line.
```
    $ sudo mysql
    or
    $ sudo mysql root
```
## 4. From now, ready to restore MySQL database

### Step 0. Enter the root.

    $ sudo -i

### Step 1. Shutdown Mysql server

    root@jeon-15UB470-KP7SKN:~# **service mysql stop**

### Step 2. Copy database in your database folder (in linux, the default location is /var/lib/mysql). Keep same name of the database, and same name of database in mysql mode.

    root@jeon-15UB470-KP7SKN:~# cp -rf /home/jeon/Desktop/wecode/mysql/django_database_essentials/ /var/lib/mysql/

### Step 3. Change own and change mode the folder:

    root@jeon-15UB470-KP7SKN:~# chown -R mysql:mysql /var/lib/mysql/django_database_essentials/
    root@jeon-15UB470-KP7SKN:~# chmod -R 660 /var/lib/mysql/django_database_essentials/
    root@jeon-15UB470-KP7SKN:~# chown mysql:mysql /var/lib/mysql/django_database_essentials/
    root@jeon-15UB470-KP7SKN:~# chmod 700 /var/lib/mysql/django_database_essentials/

### Step 4. Copy ibdata1 in your database folder

    root@jeon-15UB470-KP7SKN:~# cp /home/jeon/Desktop/wecode/mysql/ibdata1 /var/lib/mysql/
    root@jeon-15UB470-KP7SKN:~# chown mysql:mysql /var/lib/mysql/ibdata1

### Step 5. copy ib_logfile0 and ib_logfile1 files in your database folder.

    root@jeon-15UB470-KP7SKN:~# cp /home/jeon/Desktop/wecode/mysql/ib_logfile0 /var/lib/mysql/
    root@jeon-15UB470-KP7SKN:~# cp /home/jeon/Desktop/wecode/mysql/ib_logfile1 /var/lib/mysql/

### Step 6. Remember change own and change root of those files:

    root@jeon-15UB470-KP7SKN:~# chown -R mysql:mysql /var/lib/mysql/ib_logfile0
    root@jeon-15UB470-KP7SKN:~# chown -R mysql:mysql /var/lib/mysql/ib_logfile1

### Step 7. Start your Mysql server. Everything come back and enjoy it.

    mysql -u root -p
    enter password
    mysql>> show databases;

**References:** 

[https://biolinh.wordpress.com/2017/04/01/restoring-mysql-database-from-physical-files-debianubuntu/](https://biolinh.wordpress.com/2017/04/01/restoring-mysql-database-from-physical-files-debianubuntu/)

---

> **We are creating wealth every time we write a code**
