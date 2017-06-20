---
layout: post
title: Mockito Junit Test
comments: true
date: 2017-06-19
tags: [Junit]
---

### Intoduction:
Mockito is very useful for Junit test. This post will discuss how to use
mockito to write a Junit. Here I will discuss the difference between
Stub, Mock and Spy. And use mockito to give three example.

### Stub, Mock and Spy
These three concept shares some points, and also has their own
difference.

Stub is like you making the return value, everything is
mocked.

```java
/**
 * Stub
 */

@Mock
MockService mockService

@Test
public void test() {
    when(mockService...).thenReturn(...)
    Assert...
}

```


Mock means your call is mocked, but system respond is real,
which means you don't make the return value.


```java
/**
 * Mock
 */

@Mock (answer = Answer.CALLS_REAL_METHODS)
MockService mockService

@Test
public void test() {
    mockService.API()
    Assert...
}

```

Spy is way beyond mock,
both the call and system respond are real.

```java
/**
 * Spy
 */

@Mock
MockService mockService

@Before
public void setup() {
    mockService = new MockService();
}

@Test
public void test() {
    mockService.API()
    assert...
}

```
