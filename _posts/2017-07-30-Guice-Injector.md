---
layout: post
title: Guice Module
comments: true
date: 2017-07-30
tags: [Guice]
---

### Introduction:
In [previous post][1] I talked about what is dependency injection and
why use Guice. Today I would like to share my experience of using Guice
injector.


### Module
Before create injector, we should define module. Module specify where to
find all the dependencies required.

```java
public class TestModule extends AbstractModule {
    @Override
    protected void configure() {
        bind(SomeClassA.class).toInstance(Singleton.class);
        bind(SomeClassB.class).toInstance(SomeInstanceA);
        install(new SomeModule());
        requireBinding(SomeClassC.class);
    }
}
```

In Above I list four usage of configure. Each one has different meaning.
In short, bind is type, instance is real object. It tells the program
when meet the type, where to find the real object.

Override configure is required for each Module. It tells Guice how to
get the dependencies.

```java
bind(SomeClassA.class).toInstance(Singleton.class);
```

This statement is most usual. It means make 'SomeClassA' to Singleton,
SomeClassA is a dependency. Make it to singleton makes it easy to get
the instance when other places use this.


```java
bind(SomeClassB.class).toInstance(SomeInstanceA);
```

When the object is not complicate to create, and don't have other
dependency. We can directly bind a specific instance to a type.

```java
requireBind();
```

Require bind is always used when a module is already binded (in
Singleton), and here it will be used again.

```java
install(Module);
```

install is always used for bind another module.

[1]: http://www.leiyangblog.com/Guice-Dependency-Injection
