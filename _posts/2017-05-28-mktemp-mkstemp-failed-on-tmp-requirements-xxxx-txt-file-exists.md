---
layout: post
title: mktemp&#58; mkstemp failed on /tmp/requirements.XXXX.txt&#58; File exists
tags: ['Brew', 'Python', 'pyenv']
published: true
---

Today I tried to migrate my installed Python packages from version 3.6.0 to 3.6.1 with `pyenv migrate 3.6.0 3.6.1`.

But I received the following error:

> mktemp: mkstemp failed on /tmp/requirements.XXXX.txt: File exists

This can be solved with the following commands:

```bash
cd /tmp/
rm requirements.XXXX.txt
```

Solved!