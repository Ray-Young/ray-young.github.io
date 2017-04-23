---
title: JAX-RS Jerseys WebService Eclipse Development Environment Setup
date: 2017-04-21
comments: true
tags: [WebService, JAX-RS]
---

### TODO
1. Eclipse install packages, enable dynamic web application
2. Download jars jerseys, mysql, gson
3. Download mysql Trouble shooting Mac terminal ERROR 2002 (HY000):
   Can't connect to local MySQL server through socket
'/tmp/mysql.sock' —restart mysql server.
http://stackoverflow.com/questions/2933415/mysql-mac-error-2002-cant-connect-to-local-through-socket  
4. Download tomcat
5. Jersey environment 1 asm jar is needed for path search 2 display name
   mustn’t have underscore, it must match name template, otherwise 404
or 500 will occur 3 Local URL:
localhost:8080/ProjectName/url-pattern/path1/path2 // path1 is usually
class name, path2 is usually function 4 Remote URL:
http://146.115.45.215:8080/AsAbove
