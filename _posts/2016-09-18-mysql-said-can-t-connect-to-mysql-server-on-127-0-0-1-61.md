---
layout: post
title: MySQL said&#58; Can't connect to MySQL server on '127.0.0.1' (61)
---

After I updated my MariaDB via brew I received the following error when trying to connect with Sequel Pro to my database.

> MySQL said: Can't connect to MySQL server on '127.0.0.1' (61)

I solved this problem with the following command.

```shell
brew reinstall mariadb
```