---
layout: post
title: JAX-RS WebTarget URI disable autoencode
comments: true
date: 2017-06-12
tags: [WebService, Jerseys]
---

Introduction: Let's start from bottom. So, what's url encoding?

### URL/URI Auto-encoding
From [1][w3schools], it says" URLs can only be sent over the Internet using the ASCII character-set.

Since URLs often contain characters outside the ASCII set, the URL has to be converted into a valid ASCII format.

URL encoding replaces unsafe ASCII characters with a "%" followed by two hexadecimal digits.
URLs cannot contain spaces. URL encoding normally replaces a space with a plus (+) sign or with %20."

It clearly explains the reason of URL encoding, and how it works.

In other word, no matter how you manipulate, in network transfer, the url will be always encoded, and be decoded on the other side.

### The trouble WebTarget path method results

### Is there a disable API? No.

### Solution

ref:https://www.w3schools.com/tags/ref_urlencode.asp

WebTarget.path will auto encode
use queryParam to avoid

in transform, everything will be encoded.
But we don't want to encode twice.

Give example
