--------
layout: post
title: How I configured GIT with KLEOPATRA
published: true
tags: git kleopatra gpg4win
--------

Firstly I [downloaded gpg4win](https://gpg4win.org/get-gpg4win.html), donated some $$ and verifeid the downloaded file's signature.
I generated new GPG key pair, backed it up to my [Keeper vault](https://www.keepersecurity.com) and inserted its **public** portion to github.
I also published that certificate and generated a revocation certificate (which went straight to my Keeper vault).
I had to edit my global `.gitconfig` with the key's fingerprint:
```
[user]
  signingkey = <key_fingerprint>
  email = <my_email>
  name = <my_name>
[commit]
  gpgsign = true
```
And now git signs each commit with my certificate.
