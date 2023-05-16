---
author:马凯旋
title:intro-to-springboot
---



# 1 Spring vs Spring Boot
> 1) Spring is a comprehensive framework that provides various modules for building different   
> types  of applications. 
>
> 2) Spring Boot makes working with Spring much simpler. Spring Boot is like a more opinionated version of Spring. It comes with a many pre-configured settings and dependencies that are commonly used in Spring applications.
>
> Summary: Spring Boot is a **opinionated version of Spring coming with many pre-configured settings**

# 2 Inversion of control (IoC) vs Dependency injection (DI)
> 1) Dependency injection and accompanying frameworks are **one way of achieving inversion of control**, and Spring developers will often state that dependencies are "injected" into their applications at runtime.
>
> 2) within the Spring community, you'll often hear the terms used interchangeably


# 3 Spring Initializr
> 1) You can think of Spring Initializr like a shopping cart for all of the dependencies your application might need. It will quickly and easily generate a complete, ready-to-run Spring Boot application
>
> 2) he general flow for Spring Initializr is to fill in the metadata, add relevant dependencies, and generate your new project.

# 4 REST in Spring Boot
> 1) definition of REST: Representational State Transfer.  **Data objects are called Resource Representations.**  The purpose of a RESTful API (Application Programming Interface) is to manage the state of these Resources.
>
> 2) **You can think of “state” being “value” and “Resource Representation” being an “object” or "thing".** Therefore, REST is just a way to manage the values of things. Those things might be accessed via an API, and are often stored in a persistent data store, such as a database.

<img src="E:\courses\notes\spring-boot\pictures\rest-http-flow.png" alt="REST data flow using HTTP" style="zoom: 80%;" />

> 3)  One of the main things Spring does is to **configure and instantiate objects.** These objects are called **Spring Beans**, and are usually created by Spring (as opposed to using the Java new keyword)

* 我們是暗室逢燈暗室逢燈阿斯弗	