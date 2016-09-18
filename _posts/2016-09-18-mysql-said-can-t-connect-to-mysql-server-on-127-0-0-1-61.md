---
layout: post
title: MySQL said&#58; Can&#39;t connect to MySQL server on &#39;127.0.0.1&#39; &#40;61&#41;
published: true
---

After I updated my MariaDB via brew I received the following error when trying to connect with Sequel Pro to my database.

> MySQL said: Can't connect to MySQL server on '127.0.0.1' (61)

I solved this problem with the following command.

```shell
brew reinstall mariadb
```