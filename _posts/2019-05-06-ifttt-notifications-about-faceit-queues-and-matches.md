---
layout: post
title: IFTTT notifications about FACEIT queues and matches
subtitle: Receive a notification when a match is found or it is ready to join
tags: ['CS:GO']
date: 2019-05-06 15:0 +0200
published: true
---

Last week I [posted](https://www.reddit.com/r/GlobalOffensive/comments/bk8sai/i_used_the_faceit_api_and_ifttt_to_get/) a screenshot on Reddit of my smartphone where you could see that I received a notification when a FACEIT CS:GO match was found and a notification when a FACEIT CS:GO match is ready to join. It didn't go unnoticed. Many people wanted to know how I had done this. This is the reason why this post was written. Below a number of steps will be taken to set it up.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-0](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-0.png)

## Requirements

- An account on FACEIT (and logged in)
- An account on IFTTT (and logged in)
- The IFTTT application downloaded

## Set up the notifications

We are going to make the "match created" notifications. You can repeat the same steps for the "match ready" notications.

Go to [https://ifttt.com/my_applets](https://ifttt.com/my_applets) and click the **"New applet"** button on the right.

Click on **"+ this"**, search for **"Webhooks**" and select it.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-1](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-1.png)

Then we need to choose a trigger (This one is easy because there is only one option). Take **"Receive a web request"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-2](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-2.png)

Now we need to fill in an event name. Take something that is easy to remember. I took **"faceit-match-created"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-3](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-3.png)

After this we need to setup the action it will take. Click on **"+ that"**. Search for **"notifications"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-4](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-4.png)

Now we need to choose an action. There are two types of notifications (basic and rich). Basic notifications will only have a title. A rich notification will have a title, message, url and an image. I took rich notifications because a like to have an extra message. So take **"Send a rich notification from the IFTTT app"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-5](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-5.png)

The next the **title**. I took **"FACEIT - A match has been found!"**. Next up is the **message**. I took **"Click to accept"**. Finally fill in the **Link URL** (this is the click action). I filled in the URL to the FACEIT homepage, **[https://www.faceit.com/en/home](https://www.faceit.com/en/home)**, so I can mannualy accept the match from my phone (most of the time I use FACEIT enhancer).

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-6](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-6.png)

After filling in the notification values click **"create action"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-7](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-7.png)

At last give the applet a nice name (something like FACEIT - Match Ready) so it is easy to recognise and click **"Finish"**. Let's get the events from the FACEIT developers API.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-15](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-15.png)

## Receiving events from FACEIT

Go to [https://developers.faceit.com/](https://developers.faceit.com/) and log in. Select the **second menu item** (3 hexagons). This is the Application studio. Click on **"New"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-8](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-8.png)

Fill in the form (only 2 fields are required) and click on **"save"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-9](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-9.png)

Once it is created navigate to the **"Webhooks"** tab and click on the **"+ button"** to create a new subscription.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-10](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-10.png)

First we need to choose a **subscription type**. Take **"User"** so you will only receive notifications about your account. After this click **"next"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-11](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-11.png)

_If you have multiple FACEIT accounts take "Organiser" and add the other accounts via the "Collaborators" tab. I didn't test it but I assume this works. Let me know if you tried!_

Next up select the entities. Take **"My user"** and click **"next"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-12](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-12.png)

After this we need to select the **events** we want to subscribe to. Select **"Match Created"** and click **"next"**.

*If you choose multiple events at this step you will receive the same notification for every event.*

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-13](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-13.png)

Now it's time to fill in the **callback URL**. This is the **IFTTT** webhook URL. Open up a new browser tab and navigate to [https://ifttt.com/my_services](https://ifttt.com/my_services) and search for **"Webhooks"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-15](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-15.png)

On the top right corner click on **"documentation"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-16](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-16.png)

Replace **"{event}"** with the earlier chosen event name (in my case **faceit-match-created**) and copy the full URL.

_If you want to test the nofitication press the **"test it"** button._

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-17](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-17.png)

> **IMPORTANT:** YOUR WEBHOOK KEY IS SHOWN. MAKE SURE YOU DON'T SHARE THIS KEY. IF PEOPLE HAVE THIS KEY THEY CAN PREFORM WEBHOOKS UNDER YOUR ONS ON YOUR SMARTPHONE.

Go back to the FACEIT developers page and paste the URL at **"Callback URL"** and click **"create"**.

![2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-18](/assets/img/2019-05-06-ifttt-notifications-about-faceit-queues-and-matches-18.png)

Repeat the same proces for the **"match ready"** notification. You don't have to create a new application. You can use the same application. You can create multiple webhook subscriptions.

Now you are all set! Go queue for a match and test it out! GLHF!
