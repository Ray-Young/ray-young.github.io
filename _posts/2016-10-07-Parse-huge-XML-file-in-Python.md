---
layout: post
title: "Parse huge XML file in Python"
date: 2016-10-07
comments: true
tags: [Python, Data Science]
---

These days I am learning Data Science, since there are a lot of effective ways
to parse huge file in Python, today I am going to introduce a way that I 
recently learned. Here is the [official document][1] for iterparser, while it 
doesn't give clear examples, I will make up it.

First of all, you need to import the cElementTree

```python
import xml.etree.cElementTree as etree
```

It's a extended package for ElementTree, the only difference seems it has the 
advanced XML parser iterparse

To use it, you need two magic lines

```python
for event, elem in etree.iterparse("filename", events = ("start", "end")):
    if event == "end" and elem.tag == "element_name" and other conditions...:
```

There are four events in iterparse, to simplify, we just need to events which
are start and end. Start event is the beginning we parse a XML element, and end
is the end of the element

Every element we get will be saved in the elem variable, use 
```
elem.get("entry_name")
```
to get the value in each entry. elem.tag is the name of the element. In 
another word, 
```
elem.tag
```
is father, 
```
elem.get("") is child.
```

elem.tag is the name of the element. In short, if we want to build a XML file, use start event, if we want to parse a XML, use end event. Otherwise, if we want
to build and parse the XML together, use two conditional statement like

```python
if event == "end"......
......
if event == "start"......
......
```

Finally, use

```python
elem.clear()
```

to clear every element we parsed, thus we saved enough memory to parse the next
element.

In general, iterparse is the most efficient way to parse huge XML file. The 
official says it can parse up to 40GB XML file. But make sure you have at 
least 8GB memory for your computer because it need OS need at least 4GB to 
place the tmp files.

You can get a [real program][2] from my github


[1]: http://effbot.org/zone/element-iterparse.htm
[2]: https://github.com/Ray-Young/RSS-Reader/blob/master/src/python/ParseHugeXML.py
