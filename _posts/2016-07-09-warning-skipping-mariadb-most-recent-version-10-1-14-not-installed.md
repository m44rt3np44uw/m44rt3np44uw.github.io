---
layout: post
title: Warning&#58; Skipping mariadb&#58; most recent version 10.1.14 not installed
---

It's possible you will receive this warning when trying to update all of your Brew packages. This is because they reverted mariadb version 10.1.15 back to version 10.1.14 because it was never released. 

Complete explanation at: [https://github.com/Homebrew/homebrew-core/commit/8e38426bb583295e7b1dea55dfbb565a902cf3e8](https://github.com/Homebrew/homebrew-core/commit/8e38426bb583295e7b1dea55dfbb565a902cf3e8)

## How to fix

1. Open up your terminal.
2. Unlink mariadb with `brew unlink mariadb`.
3. Install the latest mariadb version with `brew install mariadb`.
4. Stop current mariadb service with `brew services stop mariadb`.
5. Start latest mariadb service with `brew services start mariadb`.
6. Remove version 1.10.15 with `rm -rf /usr/local/Cellar/mariadb/10.1.15/`.

Now your mariadb version is up to date with brew. 