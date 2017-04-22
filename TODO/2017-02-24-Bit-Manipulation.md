---
layout: post
title: Bit Manipulation
date: 2017-02-24
comments: true
tags: [Java, Bitwise]
---

In bit calculate (&, |), it is better to add parentheses for them,
especially, we must add parentheses in condition judgement

Tips for XOR
1. XOR can only check duplicate of two, e.g. 010 ^ 010 = 0, it cannot
   check duplicate more than two
2. Each 1 bit position of XOR result is the different bit of the two
   inputs
3. Using a &= -a can get the right most 1 bit (the first 1 bit from
   right)

The fact is, bit operation can do in parallel in terms of bit position.
i.e., the operation of position P & Q & any other positions can be done
in parallel. Therefore the code becomes
Signed integer. When consider a new bitwise rule, first get the formula
for state transfer, then apply the formula into the entire bits
together.

Bit mainipulation can be used to design logic operation, refer single
number II, which can calculate number occur for any times
