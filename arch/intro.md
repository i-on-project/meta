# Architectural Notes

## Introduction

This document contains a set of architectural notes for the i-on project.

The project goal is to build an information system to support academic activities. 
It also aims to work as a showcase for the principles and techniques taught in the LEIC program.

## Architecture summary

The initial draft architecture will be composed by:

- Core - service with an HTTP API exposing the _domain_ functionality.
  - Owns the main relational database, containing the domain information (e.g. curricular units, classes, student groups, events).
  - Exposes an HTTP API with the domain functionality (e.g. create a curricular unit, get classes for current semester of a given curricular unit).
  - Does not provide an human-interface.
  - Delegates authentication and part of access control to the Access Manager.

- Handler host - service hosting a set of _handlers_
  - An handler performs a task, triggered by an event such as a timer or a Web Hook request.
  - E.g. an handler that is triggered periodically to retrieve the exam calendar PDF, process it, and update the associated events (via the Core HTTP API).
  - E.g. an handler that is triggered by a GitHub web hook when a tag is created on a repo.
  - This functionality could be inside Core, however it seems different thing.

- Mobile client application - Android-based mobile client
  - Provides an human-interface for a subset of domain functionalities, mainly for information consumption.
  - Uses the Core HTTP API.

- Web application
  - Provides a browser-based human-interface for the domain functionality.
  - Includes _backoffice_ like functionalities, such as curricular unit management.
  - Uses the Core API
  - Mainly uses server-side rendering

- Web application 2
  - Optional or alternative to the previous Web application.
  - SPA-based (Single Page Application) application providing a browser-based human-interface for the domain functionality.

- Access Manager
  - Service responsible for managing users and associated authentication.
  - Integrates with external authentication mechanisms (e.g. IPL based email).
  - Acts as a token service for the other architectural components

## Technologies

Design criteria:
  - Use technologies that are used in the LEIC program.

Core:
  - JVM based application
    - Use Spring as the server framework
      - Alternatively, create a framework using a Servlet embedded server similar to what is done in LS, however that seems a significant work and too risky.
      - Use Spring MVC (well known, old/hacky, mostly synchronous) or use Spring WebFlux (asynchronous, cleaner?, integrates with coroutines, implies usage of reactive streams)
    - Use JDBI as the JDBC helper?

  - Postgres database
    - The relational model is well known by the students
    - Has some document-based features that would be interesting to explore
    - Preferable to SQL Server, mainly due to the document-based features and more hosting options

Web Application
  - JVM based application, with the same technology stack as the Core
    - Which templating language to use? Is thymeleaf the best we can get? Can we use kotlinx.html?
