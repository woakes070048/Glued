# Glued
Glued is an online ERP system developed specifically for NGOs and communities. It has been implemented in PHP as a working prototype and is now in a state, where further work gets problematic due to many dirty hacks done along the way. The current main todo item  is to reimplement Glued from scratch as a set of interconnected microservices/blackboxes.

With your participation, Glued can become one of the most important assets helping charities world wide. If you ever wanted to hack for a cause, this is your moment!

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
  - glued master service (keeps track of available/connected services, turns on/off debugging, performance tracking ...)
  - glued common libraries (common functions, caching, authorisation, url routing, interservice communication - rest api + zeromq api)
  - authentication service
  - notification service
  - file server service
  - reference / hello world functional service
- functional services (ticketing system, cms, calendar system, contacts database ...)
- mashup service (an ubercms component allowing mashups of functional services on a single url)

To speed up work, each of the services will be allowed a different paradigm (i.e. functional programming vs. oop), even a different programming language as long as each service has a language agnostic versioned API (https rest api + high performance sasl zeromq api) and has a unit test. The aim here is to be able to write a component from scratch where needed while not having to reinvent the wheel everytime. Using non-exotic runtime dependencies is encouraged.

## TODO

 - Decide architectural aspects relevant to microservice reimplementation (what to keep centralized and what to break up between services)
 - Have the base reimplementation up and running
 - UX rehaul of functional services
 - Import usable code from functional services
 - Setup CI
 - Licensing decisions (most permissive opensource license while respecting other code used)
 - Packaging
 - Internationalization /  translations
 - Packaging as a docker container for SaaS applications

## Call to action

We are looking for

 - developers
 - software architects
 - tree maintainers and release managers
 - UX designers
 - frontend ninjas

to help us kickstart the rewrite. This is your chance to get involved in a game changing open source project from its very first moment. 

Initial meetup in Brno, Industra: vote for the best time/date http://doodle.com/poll/538xdqyn82xb5f7v

## Why Glued

Glued has been developed with the aim to offer NGOs a state-of-the-art tool to manage their operations. Glued goal is to provide a userfriendly tool that will take lots of operational overhead from NGOs and allow them to focus on what they do best: doing the right thing.

Glued was prototyped and tested on a real-wold NGO. No NGO has been harmed in the process.
