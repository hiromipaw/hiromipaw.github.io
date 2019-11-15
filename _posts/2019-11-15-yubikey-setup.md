---
title: 'How to setup and use yubikeys for authentication'
date: 2019-11-15
permalink: /posts/2019/11/yubikey-setup/
tags:
  - security
  - yubikey
  - authentication
  - gpg
  - encryption
---

I use yubikeys to store my gpg and ssh keys.

Before starting do a little bit of reading to familiarize yourself with the setup
procedure.
I have added a list of links at the end. These are mainly the resources that I used.

## Generate a new gpg key

```
$ gpg --gen-key
```

Selected option 0 and moved on to create my ID associated with the key.

In this step I used mostly the guide from yubico developers website [1]
The guide goes through generating Sign (S) Authentication (A) and Encryption (E)
keys.

## Add an authentication key

```
$ gpg --expert --edit-key 123ABC45
```

At this step we select another RSA key to attach to our key. In the gpg selection
menu this corresponds to option 8.

## Backup

Here is where you should backup your keys and revocation certificates. Please do
I have personally lost yubikeys and having backups really helps.

Also setup a PIN and a admin PIN for your yubikey [5]. With:

```
$ gpg --card-edit

$ gpg/card> admin
```

## Import the key to the yubikey

Finally we edit our key and add it to the keycard [1].

```
$ gpg --expert --edit-key 123ABC45

$ gpg> keytocard
```

Now your key is exported to your card and ready to be used.

## Setup key to be used with ssh

```
$ gpg2 -K --with-keygrip
```
This will show all your keys available with keygrip.
Use the keygrip of your authentication key to export it to `sshcontrol`

```
echo 1234567AB8CDFFF90G9H1I23JJ4K5L67M89N012O > ~/.gnupg/sshcontrol
```

I have also added the following to my `~/.gnupg/gpg-agent.conf` [4]:

```
default-cache-ttl 600
max-cache-ttl 7200
enable-ssh-support
write-env-file ~/.gpg-agent-info
```

And edited my `~/.bashrc` with:

```
gpg-connect-agent /bye
export SSH_AUTH_SOCK=$(gpgconf --list-dirs agent-ssh-socket)
```

You can now:

```
$ source ~/.bashrc
$ ssh-add -l
```

This should list your new key.

- [1] https://developers.yubico.com/PGP/Importing_keys.html
- [2] https://zeos.ca/post/2018/gpg-yubikey5/
- [3] https://www.esev.com/blog/post/2015-01-pgp-ssh-key-on-yubikey-neo/
- [4] https://www.isi.edu/~calvin/yubikeyssh.htm
- [5] https://developers.yubico.com/PGP/Card_edit.html
