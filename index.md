---
layout: default
---

# Goals
* Get familiar with Spring and ecosystem
* Learn how to create Maven project for Spring
* Get familiar with Spring Core, Spring JDBC, Spring Data, Spring MVC, Spring Security
* Learn how to test applications based on the Spring Framework
* Learn best practices

# What is covered
* Inversion of Control (IoC)
* The Spring Web MVC framework
* Data access with JDBC
* Unit and integration testing
* Transaction management

# Prerequisites

* JDK 8
* Maven
* GIT
* IDE

# References
* Spring Workshops based on [https://github.com/jakubnabrdalik/spring-workshops](https://github.com/jakubnabrdalik/spring-workshops)
* JSTL tutorial [http://docs.oracle.com/javaee/5/tutorial/doc/bnakc.html](http://docs.oracle.com/javaee/5/tutorial/doc/bnakc.html)
* Boostrap 3 Template to use [http://getbootstrap.com/examples/starter-template/](http://getbootstrap.com/examples/starter-template/)
* Boostrap 3 Forms tutorial [http://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-forms.php](http://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-forms.php)
* [http://docs.spring.io/autorepo/docs/spring-framework/current/javadoc-api/org/springframework/web/WebApplicationInitializer.html](http://docs.spring.io/autorepo/docs/spring-framework/current/javadoc-api/org/springframework/web/WebApplicationInitializer.html)
* [https://schoudari.wordpress.com/2012/07/23/purpose-of-contextloaderlistener-spring-mvc/](https://schoudari.wordpress.com/2012/07/23/purpose-of-contextloaderlistener-spring-mvc/)
* [http://stackoverflow.com/questions/9016122/contextloaderlistener-or-not](http://stackoverflow.com/questions/9016122/contextloaderlistener-or-not)
* [http://www.summa-tech.com/blog/2009/04/20/6-tips-for-managing-property-files-with-spring](http://www.summa-tech.com/blog/2009/04/20/6-tips-for-managing-property-files-with-spring)
* [http://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/core/env/CommandLinePropertySource.html](http://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/core/env/CommandLinePropertySource.html)

# Technical documentation

* Maven
  * [Create standalone project]({{site.kospiotrPageURL}}wiki/maven.html#standalone-project)
  * [Create web project]({{site.kospiotrPageURL}}wiki/maven.html#web-project)
* Set up runtime environments
  * [Jetty embedded server for web application development purposes]({{site.kospiotrPageURL}}wiki/maven.html#jetty)
  * [Tomcat standalone server for web application local testing purposes]({{site.kospiotrPageURL}}wiki/tomcat.html)
  * [Derby embedded DB for development purposes]({{site.kospiotrPageURL}}wiki/maven.html#database)
* [Spring Core]({{site.kospiotrPageURL}}wiki/spring-core.html)
* [Spring JDBC]({{site.kospiotrPageURL}}wiki/spring-jdbc.html)
* [Spring Data]({{site.kospiotrPageURL}}wiki/spring-data.html)
* [Spring AOP]({{site.kospiotrPageURL}}wiki/spring-aop.html)
* [Spring MVC]({{site.kospiotrPageURL}}wiki/spring-mvc.html)
* [Spring Security]({{site.kospiotrPageURL}}wiki/spring-security.html)

#Tasks

## Spring Core

1. Create standalone project
2. Create Application Context with XML or Java configuration
3. Create basic layers to store and retrieve loans and autowire them together
  * Loan Service allows to CRUD loans using Loan Repository
  * Loan Repository is a simple in memory list of Loans
  * Loan model
      * Id (integer)
      * Requester full name (string, 128 chars)
      * Purpose (string, 255 chars)
      * Amount (positive decimal)
4. Create Integration Test that checks if CRUD operations are performed correctly
5. Localize application
6. Use properties placeholder that reads environment / commandline properties
	* In the command line store application name that will be displayed in the console when application starts. Remember to create Service for that!

## Spring JDBC

1. Make Loan Repository using database
2. Make datasource using connection properties from commandline properties

## Spring Data

1. Change Loan Repository to use Spring Data

## Spring AOP

1. In order to improve logging create logger for input and output data of annotated method.
2. The front page is often accessed. Create an aspect, which will cache list of loans for a user, without hitting a repository.

## Spring MVC

1. Create web project
2. Create home page with welcome title. 
	* Display application name that will be stored in environment variable
3. Add menu to home and all new pages, that holds links to:
	* Homepage
    * List of loans
    * Form for new loan request
4. Create loan list page
	* Display all loans in the grid
	* Add action column with delete, edit action
5. Create loan request page that:
	* Will display new loan request form
	* Will validate loan form
6. Create REST endpoints for loans
7. Stylize page using Bootstrap 3

## Spring Security

1. Secure application with Spring Security
	* Restrict browsing loans only for logged users (USERs and ADMINs)
	* Only users with ADMIN role can edit and delete loans
	* All users can request for a new loan (GUESTs, USERs, ADMINs)
2. Customize login page
3. Create registering new users page