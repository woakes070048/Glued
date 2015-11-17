# Glued
Glued is an online ERP system developed specifically for NGOs and communities. It has been implemented in PHP as a working prototype and is now in a state, where further work gets problematic due to many dirty hacks done along the way. The current main todo item  is to reimplement Glued from scratch as a set of interconnected microservices/blackboxes.



## Features

- ticketing system
- wiki
- contact database (similar to google contacts)
- kanban boards (similar to trello)
- todo lists / checklists (similar to basecamp)
- non-hierarchic file store (tag based hierarchies)
- asset booking system* 
- todo matchmaker* (matching people with required skills with work to be done)
- accounting and banking*
- notification system
- calendar, planning, scheduling
- best practices templating (integrating todo lists, wikis, contacts database and basic BPM)
- discussion boards
- CMS
- version control over content

*) partially implemented

## Planned features

- e-mail integration
- mailing list 
- social media integration
- mobile app
- crowdfunding platform
- IoT integration (Glued as a server aggregating data from IoT devices)

## Technical aspects of the reimplementation

- microservices architecture (glued implemented as a set of interconnected blackboxes communicating over APIs)
- base implementation consisting of
  - glued master service (keeps track of available/connected services)
  - glued common libraries (common functions, caching, authorisation, url routing, interservice communication - rest api + zeromq api)
  - authentication service
  - notification service
  - file server service
- functional services (ticketing system, calendar system, contacts database ...)

To speed up the work, each of the services will be allowed a different paradigm, even a different programming language as long as each service has a language agnostic API (https rest api + high performance sasl zeromq api).

## TODO

 - Import usable
 - Licensing decisions
 - 
