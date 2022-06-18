---
layout: post
title:  "IRC Commands"
date:   2021-09-04 20:55:06 +0000
categories: update
---

using [[WeeChat]] for example.

### add server and connect
```
/server add libera irc.libera.chat/6697 -ssl
/connect libera
```

### register nickname
```
/nick stefan736
/msg NickServ REGISTER xxxxxxxx you@example.net
/msg NickServ IDENTIFY yournick xxxxxxxx
```

### automatically use nickname and identify
```
/set irc.server.libera.nicks "yournick"
/set irc.server.libera.command "/msg NickServ IDENTIFY yournick xxxxxxxx"
```

### join channel, have fun
```
/join #linux
```
