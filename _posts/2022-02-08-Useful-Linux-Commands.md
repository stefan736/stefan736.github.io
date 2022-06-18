---
layout: post
title:  "Useful Linux Commands"
date:   2022-02-08 20:55:06 +0000
categories: update
---

In the following table you see a collection of commands which can come handy. For some you need installed tools like jq, grep, aws or something. Should work in bash on Ubuntu or equivalent. 

| Command | Comment |
| --- | --- |
| iperf3 -s | Start network performance tool as server |
| iperf3 -c serverIP | Connect client to server and do network performance test |
| iperf3 -R -c serverIP | Do the above but reverse traffic flow |
| cat /proc/mdstat | Check software raid status |
| du -hs /path/ | Get folder size. Last / is for filtering on directory. |
| df -hT | Get all filesystems and their utilizations |
| netstat -tnpa \| grep 'ESTABLISHED.\*sshd' | Display all established ssh connections |
| docker-compose pull<br />docker-compose down<br />docker-compose up --remove-orphans -d | Update docker containers using docker-compose |
| aws s3 sync s3://bucketname/ ./ --delete --endpoint-url=https://s3.eu-central-1.wasabisys.com | One-way sync objects in a bucket on [Wasabi](https://wasabi.com) to ./ |
| cat secret.txt \| age -r a_public_key -a > secret.txt.age | PKI encrypt secret.txt using [age](https://github.com/FiloSottile/age) |
| age --decrypt -i your_private_key secret.txt.age > secret.txt.age.txt | PKI decrypt secret.txt.age using [age](https://github.com/FiloSottile/age) |
| curl -s https://matrix.org/_matrix/federation/v1/version \| jq -r .server.version | Get the installed [Matrix/Synapse](https://matrix.org) Versions of a host. |
| curl -s https://demo1.nextcloud.com/status.php \| jq -r .versionstring | Get the installed [Nextcloud](https://nextcloud.com) Versions of a host. |
| curl wttr.in/Berlin | Get weather forcast for a location for command line output |