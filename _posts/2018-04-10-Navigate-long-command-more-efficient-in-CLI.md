---
layout: post
date: 2018-04-10
title: Manipulate long command more efficient in CLI
comments: true
---

### Introduction
Move cursor in a long command is painful. It's time to say bye bye to moving letter by letter. Let's see ways how to manipulate it more efficiently.

### Keys

`⌃A`

Use Ctrl + A and go to the start of the command

`^E`

Use Ctrl + E and go to the end of the command

`⌥B`

Use Alt + B and move word by word back

`⌥F`

Use Alt + F and move word by word forward

`^K`

Use Ctrl + K and delete to the end of line

`^U`

Use Ctrl + U and delete to the beginning of line


### Make option as meta (MAC OS only)

In the preference of terminal or iTerm, set option as meta key to use it as Alt.

#### iTerm2

Go to preference->profile->key

![iTerm][1]

#### Terminal

Go to preference->Profiles->Keyboard

![Terminal][2]

[1]: /assets/LongCommand/iTerm.png
[2]: /assets/LongCommand/Terminal.png


