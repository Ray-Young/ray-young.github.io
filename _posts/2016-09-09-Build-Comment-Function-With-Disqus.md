---
layout: post
title: "Build comment function with Disqus"
date: 2016-09-09
comments: true
---


### Introduction
Every blog need a comment function. So as this blog. I tried to build the comment function with DISQUS today, but I don't find a clear page describe how to build it up step by step. So I decide to write down my procedures.

### Register
First of all, you have to sign up an account in Disqus. Basically Disqus is a service that help you manage and build the comment function on your website. With Disqus, you don't need to build a complex backend to manage the comment function. Everything is managed by Disqus.

You can fill out anything in the sign up process. It won't interfere your own website. The only concern is the name you pick will be displayed in the website comment area.

### Follow the official document
Now you can follow the official [document][1] to add annotiation at page defination area.

### Trick Part
The work is still on half by here. Now you need to add [Universal Embed Code][2] to include folder, and name it as

```java
dispus.html
```
Just copy and paste the JS code into dispus.html. But notice you must register the disqus account first.

### Include in layout
It's the final step to finish the process. You need to add the include content to the layout, so every post will have a comment function.
You should add it like this in layout/post.index in header.

```java
{% if page.comments 
include disqus.html
endif %}
```

Now you will have your own comment function built by DISQUS.

Reference: [StackOverFlow: How to add comment function with DISQUS on Github Page][3]

[1]: https://help.disqus.com/customer/portal/articles/472138-jekyll-installation-instructions
[2]: https://leiyangblog.disqus.com/admin/universalcode/
[3]: http://stackoverflow.com/questions/21446165/how-do-i-use-disqus-comments-in-github-pages-blog-markdown
