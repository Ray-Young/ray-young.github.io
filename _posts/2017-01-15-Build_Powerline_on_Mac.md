---
layout: post
title: Build Powerline on OS Sierra
date: 2017-01-15
comments: true
tags: [Powerline, Environment, OS Sierra]
---

### Introduction
The new python 3.5 environment and OS Sierra seems have
 some tricks when configure the powerline configuration.
 Here are my solutions to some tricky problems. (Solve powerline-config
not found problem, etc.)

The [official doc][1] seems a bit complex. Here is a [short guide][2] I
find useful when build the powerline. We only need the following steps.

### 1. Install Python (We can install it from official python website, or Brew)

So many instructions online, just google python :)

### 2. Install Powerline from pip (Or we can install it from git)

```bash
sudo pip install powerline-status
```

### 3. Config Powerline in bash_profile

Go to home directory
```bash
cd ~
```
and open .bash_profile, Add the following statements to the bash profile

```bash
# Powerline configurations
export PATH="$HOME/.local/bin:$PATH"
export POWERLINE_COMMAND=powerline
export POWERLINE_CONFIG_COMMAND=powerline-config
powerline-daemon -q
POWERLINE_BASH_CONTINUATION=1
POWERLINE_BASH_SELECT=1
.  /Users/lei/.local/lib/python3.5/site-packages/powerline/bindings/bash/powerline.sh
```

Note that you may have different path of powerline and python, check the
location via

```bash
pip show powerline-status
```

The configurations relates to path are

```bash
.  /Users/lei/.local/lib/python3.5/site-packages/powerline/bindings/bash/powerline.sh
export PATH="$HOME/.local/bin:$PATH"

```

If you met powerline-config not found problem, this statement will save
your life. This problem blocked me when I configured mine. Finally I
found the solution from [here][3].

```bash
export POWERLINE_CONFIG_COMMAND=powerline-config
```

### 4. Install the Powerline font
Follow the [guide][4], it's a easy step.

### 5. Configure .Vimrc

Copy the following part to .vimrc (if you don't have one, create it at
home directory)

```bash
set
rtp+=/Users/lei/.local/lib/python3.5/site-packages/powerline/bindings/vim

set nocompatible
set t_Co=256
 
" let g:minBufExplForceSyntaxEnable = 1
" from powerline.vim import setup as powerline_setup
" python powerline_setup()
" python del powerline_setup
 
set laststatus=2 " Always display the statusline in all windows
set guifont=Inconsolata\ for\ Powerline:h14
set noshowmode " Hide the default mode text (e.g. -- INSERT -- below the
statusline)
```

You may find more configurations about vim from [here][5] (Node it's not
related with Powerline, but will make your vim operations more
convenient)

Another [system path][7] knowledge may help better understand the above
configurations.

Restart terminal and enjoy :)

Result Demo:
![result_demo][6]


[1]: https://powerline.readthedocs.io/en/latest/installation/osx.html
[2]: http://www.jianshu.com/p/68ef9d2e1653
[3]: https://github.com/powerline/powerline/issues/850
[4]: https://github.com/powerline/fonts
[5]: https://github.com/Ray-Young/dotvim/blob/master/vimrc
[6]: /assets/powerline/demo.png
[7]: http://stackoverflow.com/questions/13978654/export-path-in-profile-on-mac
