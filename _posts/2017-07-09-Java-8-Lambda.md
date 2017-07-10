---
layout: post
title: Java 8 Lambda Expression
date: 2017-07-09
comments: true
tags: [Java]
---

### Introduction:
Lambda is a magic expression in Java 8, which makes tens
or hundreds of lines become one line, and makes code concise and easy.
This post will introduce using lambda expression for thread pool and
stream.

### Thread pool lambda expression
Recently I am using Java thread pool, and Mateusz reminds me to try
lambda expression. It really opens a new world to me. Instead of
implementing another class implements runnable (or extends thread), I
can use one line to express everything.

Here let's see a short example I write.

```java
// Create 5 threads in pool
ExecutorService executor = Executors.newFixedThreadPool(5);

Runnable task = () -> {
    String threadName = Thread.currentThread().getName();
    System.out.println("The current thread is " + threadName);
}

executor.submit(task);
```

One awesome point using Lambda expression is that we don't need to create another class for thread, which means we don't need pass a lot of parameter and construct the class.

If you want to see the thread execution result, you can also use a
Future object to get the thread execution result;

```java
Future<String[]> future = executor.submit(task);
System.out.println("The execution of thread 0 is " + future.get()[0]);
```

### Stream

I am not going to talk about the inputstream. Instead, using stream to
manipulate list is another awesome lambda expression in Java 8.

```java
List<String> list = Arrays.asList("e1", "e2", "e3");

list.stream()
    .filter(s -> s.contains("1"))
    .map(String::toUpperCase)

// Out
E1
```
It's similar the list operation in Perl.

Anyway, Java 8 is more powerful than ever. I do see it learns a lot powerful strength from other language. Still remember how exhausting to write a thread class, now with Lambda expression, everything is becoming so concise and beautiful.

