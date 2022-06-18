---
layout: post
title:  "SSH with MFA"
date:   2021-09-06 20:55:06 +0000
categories: update
---

`Last updated in September, 2021`

Connecting to machines these days via SSH is still a thing.
To make this more secure, please use at least pubkey authentication and disable password login.

You can of course set a passphrase for your private key, which is quiet secure but you can even do more.

Since OpenSSH 8.2 you can also use a hardware token to secure your key.
You can check your installed version via (this is a UPPERCASE V):
```bash
$ ssh -V
```
This version is included in Ubuntu 20.04 and later.

So if your client and the ssh-server is using OpenSSH 8.2 or later you can create private/public keypair using e.g. a [YubiKey 5](https://www.yubico.com/products/yubikey-5-overview/).

```
$ ssh-keygen -t ed25519-sk
```

What that means is, that everytime you are connecting to a machine using this key you need your hardware token (e.g. YubiKey) to be connected to your client machine and you need to press it's button.

## What does it look like
- when hardware token is not connected
```
$ ssh -i ~/.ssh/id_ed25519_sk example.com                
Confirm user presence for key ED25519-SK SHA256:6PoiX2PRxhd7tYEXBpzsH/ulYmetHY13IlIuJOiXrmY
sign_and_send_pubkey: signing failed for ED25519-SK "/Users/stefan/.ssh/id_ed25519_sk": invalid format
stefan@example.com: Permission denied (publickey).
```
- when hardware token is connected
```
$ ssh -i ~/.ssh/id_ed25519_sk example.com
Confirm user presence for key ED25519-SK SHA256:6PoiX2PRxhd7tYEXBpzsH/ulYmetHY13IlIuJOiXrmY
```

## Conclusion
This is really the next big step towards security. Hardware security tokens can also be used more and more on websites for MFA. You should consider buying one of these.
### BUT what happens if the hardware token gets lost or damaged??
For the online services you usually get backup codes when you activate MFA.
For SSH you need a conventional keypair to be setup or better you have a second hardware token with which you create a second keypair.