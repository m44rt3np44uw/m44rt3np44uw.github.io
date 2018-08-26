---
layout: post
title: MagicMirror² Module&#58; MMM-zoom
subtitle: Scale the entire UI with this plugin
tags: ['MagicMirror²']
date: 2018-08-26 19:37 +0200
published: true
---

If you are running MagicMirror in a Docker container, like me, you may noticed the `custom.css` file will not be loaded. This is because only the `modules` and the `config` directory are mounted. So if you want to scale your MagicMirror UI with custom CSS it won't work. This module will do the job.

## Screenshots

### Default zoom

![MMM-zoom - 100%](/assets/img/2018-08-26-magicmirror2-module-mmm-zoom-1.00.png)

### 75% zoom

![MMM-zoom - 75%](/assets/img/2018-08-26-magicmirror2-module-mmm-zoom-0.75.png)

## Installation

In your terminal, go to your MagicMirror's Module folder:
````
cd ~/MagicMirror/modules
````

Clone this repository:
````
git clone git@github.com:maartenpaauw/MMM-zoom.git
````

Configure the module in your `config.js` file.

## Using the module

To use this module, add it to the modules array in the `config/config.js` file:

````javascript
modules: [
    {
        module: 'MMM-zoom',
        config: {
            zoom: 0.75
        }
    }
]
````

For more information visit the GitHub repository:
[https://github.com/maartenpaauw/MMM-zoom](https://github.com/maartenpaauw/MMM-zoom)
