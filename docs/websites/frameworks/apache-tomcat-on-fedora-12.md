---
deprecated: true
author:
  name: Linode
  email: skleinman@linode.com
description: 'Instructions for installing and using the Apache Tomcat Java Servlet engine on Fedora 12.'
keywords: 'apache tomcat fedora 12,java,java fedora 12,java servlets fedora 12,java fedora'
license: '[CC BY-ND 3.0](http://creativecommons.org/licenses/by-nd/3.0/us/)'
alias: ['frameworks/apache-tomcat/fedora-12/']
modified: Friday, April 29th, 2011
modified_by:
  name: Linode
published: 'Friday, July 23rd, 2010'
title: Apache Tomcat on Fedora 12
---



Apache Tomcat is a free and open source software implementation for Java Servlets. It provides support for the Java Server Pages (JSP) that power many popular web-based applications.

This guide assumes that you have a working installation of Fedora 12, and that you have followed our [getting started guide](/docs/getting-started/) to get your system working and up to date. If you are new to Linux server administration, you may be interested in our [introduction to Linux concepts guide](/docs/tools-reference/introduction-to-linux-concepts/), [beginner's guide](/docs/beginners-guide/) and [administration basics guide](/docs/using-linux/administration-basics).

Install Apache Tomcat
---------------------

Install the latest version of Tomcat 6 with the following command:

    yum update
    yum install tomcat6 tomcat6-webapps tomcat6-admin-webapps java-1.6.0-openjdk-devel.i686
    chkconfig tomcat6 on

This command will install the tomcat6 service, as well as the OpenJDK runtime environment and developer tools. Start the tomcat6 service with the following command:

    service tomcat6 start

Tomcat should now be totally functional. In the future, if you need to start, stop, or restart, you can use the following commands:

    service tomcat6 start
    service tomcat6 stop
    service tomcat6 restart

Test and use Tomcat
-------------------

You can test your Tomcat installation by pointing your browser to `http://[yourdomain-or-ip-address]:8080/`. By default, files are located at `/usr/share/tomcat6/webapps/`.

At this point, you may want to create a user to access the "Tomcat Manager" web application. This will give you some information concerning your Tomcat instance, as well as some demo applications for testing. To add a user, edit the `/etc/tomcat6/tomcat-users.xml` file to include the following line, substituting your own username and password. Make sure you keep the "manager" role.

{: .file-excerpt }
/etc/tomcat6/tomcat-users.xml
:   ~~~ xml
    <user name="squire" password="examplemorris" roles="manager" />
    ~~~

Once you have saved the `tomcat-users.xml` file, restart the tomcat6 service with the following command:

    service tomcat6 restart

At this point, you will be able to log in to the Tomcat Manager application and begin deploying Java Servlets with Apache Tomcat!

More Information
----------------

More Information
----------------

You may wish to consult the following resources for additional information on this topic. While these are provided in the hope that they will be useful, please note that we cannot vouch for the accuracy or timeliness of externally hosted materials.

- [Tomcat Home Page](http://tomcat.apache.org/)
- [Tomcat FAQ](http://wiki.apache.org/tomcat/FAQ)



