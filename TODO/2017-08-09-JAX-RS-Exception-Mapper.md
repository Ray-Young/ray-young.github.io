---
layout: post
title: JAX-RS Exception Mapper
date: 2017-08-09
comments: true
tags: [Java, JAX-RS]
---

### Introduction:
ExceptionMapper is an implementation of JAX-RS exception. It allows you to use customized exception.

### Provider
**@Provider** is a JAX-RS annotation that tells JAX-RS that you want use some customized implementation instead of default.

### Usage
The basic usage is override the **toResponse** Method.

>> In specific, if you want to map the ClientErrorException, pick the type as ClientErrorException in the implements.

>> e.g.

```java
public class ClientExceptionMapper implements ExceptionMapper<ClientErrorException> {
    @Override
    public Response toResponse(final ClientErrorException exception) {
	// Customize the exception
    }
}
```

In this case, all the ClientErrorException will be mapped to the new class.


