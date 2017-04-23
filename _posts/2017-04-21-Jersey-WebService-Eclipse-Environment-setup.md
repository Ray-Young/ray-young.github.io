---
layout: post
title: JAX-RS Jerseys WebService Eclipse Development Environment Setup
date: 2017-04-21
comments: true
tags: [WebService, JAX-RS]
---

### Eclipse web application extensions

Install the dynamic web application extensions and Server Adapters

1. Help -> Install New Software
2. Type in the current edition of eclipse, e.g. neon, then it will
   auto-completition, choose http://download.eclipse.org/releases/neon
3. Select the following

```code
JST Server Adapters
JST Server Adapters Extentions
Eclipse Java EE Developer Tools
Eclipse Java Web Developer Tools
Eclipse Web Developer Tools
Eclipse XML Editors and Tools
```

### Download JAX-RS Jerseys jars

I used Jerseys jersey-bundle-1.17.1, bundle is much more easier in the
environment setup. Remember to add asm.jar for the Jersey Path search

Jars:

```code
jersey-bundle-1.17.1.jar
asm-3.1.jar
```

Put these jars into WebContent/WEB-INF-lib

The environment is completed then. Enjoy your programming now !

A [reference project][1] you can refer.

[1]: https://github.com/Ray-Young/DoMeAFavor

