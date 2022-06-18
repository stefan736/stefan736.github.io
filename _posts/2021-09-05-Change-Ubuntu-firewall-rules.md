---
layout: post
title:  "Changing Ubuntu Firewall Rules"
date:   2021-09-05 20:55:06 +0000
categories: update
---

`Last updated in September, 2021`

### Grant Access to Port 80 
```
$ sudo iptables -I INPUT 6 -i ens3 -p tcp --dport 80 -m state --state NEW,ESTABLISHED -j ACCEPT
```

### Important: Save the rules
```
$ sudo netfilter-persistent save
```
If you do not do that, and e.g. change your ssh port, you can not access your machine after reboot!