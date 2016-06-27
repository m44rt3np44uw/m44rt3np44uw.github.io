---
layout: post
title: Jekyll driver voor Laravel Valet
date: '2016-06-27 17:52:13 +0100'
published: true
---

Helaas is er nog geen officiële Jekyll driver voor Laravel Valet maar dat kan met het volgende commando eenvoudig worden opgelost:

```shell
cd ~/.valet/Drivers/
wget https://raw.githubusercontent.com/scrwdnet/valet/72603e278f80310a92838370fa4326a3592b2e5f/cli/drivers/JekyllValetDriver.php
```

Dit is een tijdelijke oplossing totdat pull request [#29](https://github.com/laravel/valet/pull/29) van [scrwdnet](https://github.com/scrwdnet) wordt geaccepteerd.
