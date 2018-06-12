# Kata-03: Split a leagcy service

This kata wanted train you to split a monolith leagcy app into smaller separated service.
The existing IT-world love monoliths. Nothing is really wrong with a good modular monolith application.
But the current change rate is high. A lot of experiences and variants are created to find the real customer value. 
Nobody knows which effect are exists, if some functions are really used of million of requests. Really scale is a pain!

How you can split your legacy apps into smaller pieces?

Start small and thing bigger.

* Choose a big spring boot application
  * Split them into microservices
  * Split them into function
* Really all things needed?
* Hardening your services?
* Which tools really needed to debug or trace your system?
* Is something very bad into the new service design?
* Distributed monolith are an antipattern.

## Other nice questions

* How you can share binaries, without rebuilding all from scratch?
* How you redesign and refactor the service productive, with out destroy something?
* How you manage the integration testing?

## Helpful informations

* https://martinfowler.com/articles/break-monolith-into-microservices.html
* https://scs-architecture.org/
* https://github.com/openfaas/serverless-openfaas
* https://github.com/kubeless/kubeless
* https://istio.io/
