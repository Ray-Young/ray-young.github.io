---
layout: post
title: JavaScript Asynchronous call
comments: true
tags: [JavaScripts, AngularJS]
date: 2017-07-23
---

### Introduction:

Recently I was implementing a front-end UI, which I need to use a
RESTful call to get endpoint data. However I can't get the data through
JavaScript. After ask google and stackoverflow, I found JS is really a
bit different from other programming language. Let's discover the root
reason.

### Single thread event loop
In the browser end, JS runs in a single thread event loop. Which means
it only has one thread to handle the process. Understand that gives us
the reason why we need promise.

### Promise
Promise is a way we can make asynchronous call in browser end. Because
we only has one thread now, and we can't make the system wait until we
get the response. $Promise leaves a place for the response, and says
'When the response back, this place is for it. Let the program do what
is supposed to do first'.

### AngularJS Http $promise

```js
method(parameter)
    .post(payload)
    .$promise
```

Inside the method, there should be some logic of http request. For
example

```js
function method(headers) {
    return $resource(url, {} {
        post: {
           method: "POST",
           header: headers || {}
    });
}
```

$resource is another AngularJS usage, usually used in REST call.

### Make promise call
JavaScript has special strategy to handle the promise call. Usually we
have to define a method and use 'then' to handle the response. For
example

```js
function method(parameter) {
    HttpCall(data)
        .then(function(response) {
            // handle response
        });
};
```

If we directly use the response, it's more likely the reponse is still
on the way, and we are likely get and empty. (Remember the single thread
principle)

### In the end
Anyway JS and AngularJS is a bit mysterious before understanding the
mechanism inside. Once get, it's beautiful!
