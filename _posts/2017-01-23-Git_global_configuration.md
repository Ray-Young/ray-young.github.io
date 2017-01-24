---
layout: post
title: Set Git local/global config using CL/File
date: 2017-01-23
comments: true
tags: [Git]
---

### Introduction
There are two ways to set git config, commandline and directy write in
git config file. The principle of two ways are similiar. Here introduce
how to do them.

### Set Git configuration using command line
Sometimes we use git config to set configuration, like

```bash
# map st as status
git config alias.st status
```

Sometimes we add --global option. It is obvious that first is local setting and the second is global setting.

### Set Git configuration using file

We can also do it in git file. The local git config file is at

```bash
./.git/config
```

The global git config file is at

```bash
~/.gitconfig
```

Take an example, add the following text will update the alias setting

```bash
[alias]
    co = checkout
    ci = commit
    br = branch
    st = status
```

