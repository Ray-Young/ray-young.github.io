---
layout: post
title: Trigger other script from Bash
date: 2017-10-17
comments: true
tags: [Linux]
---

### Introduction:
There are many advantage to use script as the entrance of small program,
which saves environment setup time and make things easy. Furthermore,
it's also preferred to write small script to solve daily small problem
(e.g. sort folders, find docs, etc.). This post intends to illustrate how to write Linux Script in an easy way.

### What is #! /bin/...
We can see in the first line of the script file, it's usually a line
shows

```shell
#! /usr/bin/perl
```

Or like

```shell
#! /usr/bin/env perl
```

It direct the shell how to find the location of interpreter.

### A short example
Here I give a short python script.

```python
#! /usr/bin/env python
from KNN_Handler import run
import sys

def main():
    argv = sys.argv
    run(argv[1], argv[2], argv[3])

if __name__ == "__main__":
    main()
```

We don't need any postfix when saving this file. Just leave it empty.
It's executable everywhere.

Here KNN_Handler is a python class I wrote, and run is a public method
in it.

### A short tip
Remember to change mode of this file to executable by run command

```command
chmod -x 'file_name'
```
