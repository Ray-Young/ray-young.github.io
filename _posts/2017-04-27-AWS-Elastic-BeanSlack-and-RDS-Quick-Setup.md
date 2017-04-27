---
layout: post
title: AWS Elastic BeanSlack and RDS Quick Setup
date: 2017-04-27
comments: true
tags: [AWS]
---

### Introduction:

Setup an AWS environment for testing and production environment can save
a lot time compared with local environment setup. Also, a cloud
environment helps developers cooperate more conveniently in web
application development and deployment. This post shows how to setup
 Elastic BeanSlack and Rational Database system for serving a WebService Servlet.

### Elastic BeanSlack

Elastic BeanSlack is an easy deployment service for web application.
Just select which server you need (I used Tomcat), and upload the war
file, then everything is done. You can visit and get the response
through the url.
Here I deployed my Web Service Servlet on the Elastic BeanSlack.

![elsatic_beanslack][1]

### RDS

Since we have the server now, we need a database to connect with the
server, cloud database is our first choice because each developers can
corporate with each other conveniently. Here we choose RDS, Rational
Database System. It can directly connect with the elastic beanslack.
Just take the following steps.

![rds_elastic_bean_config][2]

You can also refer the [documentation][3] for this configuration.

Now you can remote connect the mysql server

```bash
mysql -h [server_name // given in RDS] -u username -p password
```

Note username and password are defined when initialize the database

### EC2

Maybe you will have the doubt. Why not use EC2 directly? In my
understanding, EC2 is a complete virtual machine. Either Elastic
BeanSlack or RDS are partial modules. To use EC2, you have to configure
the entire environment (path, config files, etc).

Using Elastic Beanslack and RDS is convenient, all the configurations
are completed, we just need to upload our warfile/remote connect the
database. We don't need worry about the configuration, the system path,
etc.

In conclusion, if you want to take control of everything or you need to
build a complex server, use EC2 is the first choice. Otherwise, choose
the seperate service and leave the annoyed environment setup to AWS!

### Useful commands

Connect to EC2

```bash
ssh -i [key_location] ec2-user@[ec2_dns]
```

Remember to chmod of the key before connect.

[1]: assets/AWS/elastic_beanslack.png
[2]: assets/AWS/rds_elastic_bean_config.png
[3]: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/java-rds.html
