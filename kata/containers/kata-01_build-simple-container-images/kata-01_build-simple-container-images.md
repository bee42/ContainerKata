# Kata-01: Build a simple container image

This kata wants to train you in building a simple HTTP service container image. The problem domain is something seemingly simple: Serve something as a HTTP service.

Some things in http space mean today serve your information as with REST or gRPC style.
Promote your result inside a container image and push it to registry. For example:

* Setup or copy a HTTP-Service like whoami from emilevauge, Apache httpd or a Spring-Boot microservice. Your goal is to build a simple running http service container with quality :-)
* Think about how easy it is to build a new image with Docker CE and a Dockerfile
* If your service scales, how much ressources does the service consume?
* Find rules how a good container image looks like?
* Push the result to a registry
* Build the service with [12 factor rules](https://12factor.net) in mind!

## Other nice questions

* How to promote your image?
* What does simple really mean?
* How well proven is your image at production?
* How easy is it for other people to use your images?
* Which tools can help you in checking image quality?

## Helpful informations

* https://docs.docker.com/engine/reference/builder/
* https://docs.docker.com/develop/develop-images/dockerfile_best-practices/
* http://label-schema.org/rc1/
* https://microbadger.com/
