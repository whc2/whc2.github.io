---
layout: post
title:  mysql installation for MacOs 10.15
subtitle:   authority impact mysql start
date:   2025-07-06
author: HC
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - MySQL
---

I downloaded the installer (mysql-8.0.23-macos10.15-x86_64.dmg) from official website. After installation, I used 'mysql -u root -p' to run it. But due to permission problems on mac, it failed. I used the following steps to resolve it.

```
1. change permission of mysql directory:
>>>	sudo chown -R empty45:wheel /usr/local/mysql
>>> sudo chown -R empty45:wheel /etc/my.cnf

2. try to start mysql:
>>>	./mysql.server start --verbose # in support-files

3. find the problem in log file:
>>> less username.local.err

[my-011011] [server] failed to find valid data directory.

4. initialize the installation:
>>> ./mysqld --initialize

5. try to start mysql:
>>>	./mysql.server start --verbose # in support-files

6. use mysql:
>>> mysql -u root -p
```
Enjoy, hope it will be usefull.

