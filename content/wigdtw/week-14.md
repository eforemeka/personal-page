---
title: "Week 14"
date: 2022-04-09T00:08:05+01:00
draft: false
---

My update for the week ending on 9th April, 2022.

## Cloud Resume
I made some changes to my resume during the week and noticed the build workflow run that allows for CI/CD failed. GitHub Actions was unable to write the files on my repo to my Azure Blob Storage.

I soon realized this was because the Azure CLI executing the scripts had a new version. It used to be version 2.33.1 but is now 2.34.1. All I needed to do was add the "overwrite" argument to my script and that fixed it.

Also added font awesome globe icon to my social links. That icon links to this website.

## Ghosts of Co-Workers Past
Someone I used to work with reached out with an issue he was struggling with. Apparently, he 'mistakenly' uninstalled his Microsoft 365 App for Windows and was pretty much unable to work. We did not have an app to reinstall Office so I connected remotely to him using Anydesk and ran a restore on Windows to a point before the uninstall happened. I then repaired the office installation and that fixed everything.

Another ex-coworker reached out. He wanted to know what anti-virus his daughter could use on her laptop for school. She uses a Windows OS so I suggested that all she needed to do was ensure her laptop was up to date. Windows Defender on Windows 10 is pretty solid when kept updated. I also suggested she download and install Immunet by Cisco to complement Windows Defender. It is free and really good.

## Timetable
I drafted a study timetable for skills I need to firm up on within the next 2 weeks. I will write about a few new things I learn along the way. So expect something about REST APIs and SQL next week and the week after.

## Applications
* I took the most intense assessment test I have taken in a while. It lasted almost two hours and I enjoyed it.
* Built a portfolio using Webflow. Created a special subdomain and pointed it to my portfolio's URL. I hope someone from Webflow likes it.

## New German words/phrases I learned on Duolingo
* *Spaß* - Fun
* *Spaß machen* - Have fun
* *Einmal* - Once

## TV Series
These are the TV shows I currently follow:
* The Good Doctor S05 E13
* Moon Knight S01 E02
* Killing Eve S04 E08