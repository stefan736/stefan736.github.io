---
layout: post
title:  "Virtualization on Apple Silicon M1"
date:   2021-09-18 20:55:06 +0000
categories: update
---

![Pasted image 20210918211807.png](/assets/Pasted image 20210918211807.png)

Owning a MacBook Air with Apple Silicon M1 is really really nice, performance and battery life are unmatched. 
But when it comes to virtualization, you can no longer use VirtualBox or something like that, at least not natively, because Apple Silicons are ARM-based chips instead of x64/AMD64.

To virtualize your favourite OS anyway, have a look at the open source macOS app [UTM](https://mac.getutm.app).
Based on [QEMU](https://www.qemu.org) you get fantastic performance running an ARM-based OS. X64 OSes are also supported, but performance is not nearly as good.