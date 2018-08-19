---
layout: post
title: Skipping&#58; fdupes&#58; most recent version 1.6.1 not installed
tags: ['Brew']
published: true
---

It's possible you will receive this warning when trying to update all of your Brew packages.

> Warning: Skipping fdupes: most recent version 1.6.1 not installed

## How to fix

1. Open up your terminal.
2. Unlink fdupes with: `brew unlink fdupes`
3. Install the latest fdupes version with: `brew install fdupes`
4. Go to the fdupes folder with: `cd /usr/local/Cellar/fdupes`
5. Remove all other versions than 1.6.1 with : `rm -rf <INSERT_FOLDER_VERSION>`

Now the warning is solved.