---
layout: post
title: Build Restful server with Jerseys framework
date: 2017-04-23
comments: true
tags: [JAX-RS, WebService]
---

### Introduction:
Recently I am developing an Android application, which needs to write a
server.
I choose to build a restful server, because it's most compatiable. We
don't need to build another server if we want to extend IOS, PC, Windows
Phone or any other clients. I used tomcat as
the server, mysql as database. And Jerseys as the webservice
implementation framework.

I have introduced the environment setup in the [last post][1], this time
I am going to introduce how to use Jerseys APIs.

### Architecture Overview

![architecture][4]


### Why Restful Web Service

The most significant benefit of REST architecture is easy data extract.
Imagine different data type, html, string, xml, json...... It's so
messy. With REST Architecture, everyone use json, it makes communication
easier!

The reason why web service is because its lightweight and portability.
Now we can access all the data using URL through http request, and get
json object back, which is easy to read! Clients don't need get tired of
match the server code. E.g. Server is in C, we can write client in Java,
in Python, in Perl, in anything can send http request and receive
respond. And the client's data accessing part become extremely easy!

### Web Service based on Jerseys Framework
Here is the project overview

![overview][2]

Let's break the problem from analyzing the request URL
```
e.g. localhost:8080/ProjectName/url-pattern/path1/path2
```

ProjectName is the project name

url-pattern is defined in web.xml

path1 is usually the class path defined in the top of class

path2 is usually the method path defined in the top of the method

In a real example,

```
e.g. localhost:8080/DoMeAFavorServer/rest/user/getUser
```

The project name is DoMeAFavorServer

rest is defined in web.xml

```xml
    <servlet-mapping>
        <servlet-name>jersey</servlet-name>
        <url-pattern>/rest/*</url-pattern>
    </servlet-mapping>
```

user is defined in the top of UserService Class

```Java
@Path("/user")
public class UserService {
...
```

getUser is defined at the top of the getUser method

```Java
    @GET
    @Path("/getUser")
    @Produces(MediaType.APPLICATION_JSON)
    public String getUser() throws Exception
```

### Things need to take care

The web.xml file is pretty different based on different Jersey Version,
If you use Jersey-bundle-1.1.17.jar as me, then just copy paste the
following code to the web.xml, remember to change the display name, and
no underscore for the display name

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns="http://java.sun.com/xml/ns/javaee"
xmlns:web="http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd"
    xsi:schemaLocation="http://java.sun.com/xml/ns/javaee
http://java.sun.com/xml/ns/javaee/web-app_3_0.xsd"
    id="WebApp_ID" version="3.0">
    <display-name>DoMeAFavorServer</display-name>
    <servlet>
        <servlet-name>jersey</servlet-name>
        <servlet-class>com.sun.jersey.spi.container.servlet.ServletContainer</servlet-class>
        <load-on-startup>1</load-on-startup>
    </servlet>

    <servlet-mapping>
        <servlet-name>jersey</servlet-name>
        <url-pattern>/rest/*</url-pattern>
    </servlet-mapping>
</web-app>
```

Refer the [sample project][3] for reference!

[1]: http://www.leiyangblog.com/2017/04/21/Jersey-WebService-Eclipse-Environment-setup/
[2]: /assets/Jerseys/jerseys_project_overview.png
[3]: https://github.com/Ray-Young/DoMeAFavor
[4]: assets/Jerseys/architecture.png

