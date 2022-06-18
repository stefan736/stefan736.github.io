---
layout: post
title:  "Linux Startup Script"
date:   2021-09-05 20:55:06 +0000
categories: update
---

Sometimes you need a script to run when your favorite linux distro starts. 

Many people do not know that **cron** has an option for that. 

Edit your cron jobs 
```
$ crontab -e
```

just insert your script here
```
@reboot /path/to/script.sh
```