---
title: "Setting up local repo on new machine + SSH keys"
date: 2022-07-08
showDate: true
draft: false
tags: ["code","Pavel"]
---

_[Pavel⇢](https://pa2sh.club/) has tought me this:_

### Part I — setup SSH key
0. login at `github.com`
1. generate an SSH key. Paste `ssh-keygen -t ed25519 -C "your_email@example.com"` to Terminal, replace email ([github tutorial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key)).
2. Add the new key to ssh config (~/.ssh/config):

`Host *`
`AddKeysToAgent yes`
`IdentityFile ~/.ssh/gardenKey`
2. enter `cat ~/.ssh/gardenKey.pub` to print insides of the .pub file (public part of the key)
3. copy contents to `github.com/settings/ssh/new` and add

### Part II — setting local repo
0. clone repo using SSH at `github.com` (code dropdown)
1. type `cd` to go to home dir
2. type `git clone` + space + copied SSH address
3. 