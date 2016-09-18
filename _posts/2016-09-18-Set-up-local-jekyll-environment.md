---
layout: post
title: Build local jekyll environment
date: 2016-09-18
comments: true
tags: [Github Page, Jekyll]
---

### Why we need to build jekyll locally
I used to built my site remotely, while I find it makes too many commits and 
it's a waste of time and resources to do so. So I decide to build a local 
Jekyll environment so that I can test it locally~!

### How to build the environment locally
Github has provided [official document][1] on how to set up the environment. 
While there are still a few tricky points blocked me. I will list them and 
wish to help someone meets the same problems.

### Specify repository name in config
When I finish the set up steps and try to make some updates, an error occurs which says

```bash
No repo name found. Specify using PAGES_REPO_NWO environment variables
```

This is caused by a bug of Github Page and it's a [raised issue][2] from jekyll
issues.

You can solve it by add the repository anme with organization to 

```bash
_config.yml
```

For example

```bash
repository: ray-young/ray-young.github.com
```

### Provide necessary Github APIs for Jekyll
To set the local jekyll environment successfully, you need to config Jekyll
following [Configuring Jekyll][3], it's important to add 

```bash
github: [metadata]
```
in the config file so provide necessary Github APIs for Jekyll.

Enjoy your trip in Github Page~

[1]: https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/
[2]: https://github.com/jekyll/jekyll/issues/4705
[3]: https://help.github.com/articles/configuring-jekyll/
