---
title: "Week 14"
date: 2022-04-09T00:08:05+01:00
draft: false
---

My update for the week ending on 9th April, 2022.

## Cloud Resume
I made some changes to my resume during the week and noticed the build workflow run that allows for CI/CD failed. GitHub Actions was unable to write the files on my repo to my Azure Blob Storage.

 ![Build Error](/static/images/build_error.png)

I soon realized this was because the Azure CLI executing the scripts had a new version. It used to be version 2.33.1 but was now 2.34.1. All I needed to do was add the "overwrite" argument to my script and that fixed it.