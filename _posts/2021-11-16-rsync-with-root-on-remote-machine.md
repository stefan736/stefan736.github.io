---
layout: post
title:  "rsync with root on remote-machine"
date:   2021-11-16 20:55:06 +0000
categories: update
---

In case you want to backup a remote machine, which runs Ubuntu, and you do not want to grant root access to this machine you can tell **rsync** to run on the source (remote) machine as root.

Add `--rsync-path="sudo rsync"` so it looks like:

`rsync -rltDv --delete --rsync-path="sudo rsync" source:/path target:/path`

Just make sure the user you are connecting as on the source is able to sudo.
