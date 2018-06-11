# Kata-01: Build a simple container image

This kata wanted train you to build a simple http service container images. The problem domain is something seemingly simple: serve something as a http service.

Some things in http space mean today serve your information as with REST or gRPC style.
Promote your result inside a container image and push it to registry. For example:

* Setup or copy a HTTP-Service like whoami from emilevauge or a Spring Boot microservice. Your goal is build a simple running http service container with quality :-)
* Think about how easy is building a new image with Docker CE and a Dockerfile
* If your service scale, how much ressource the service consumes?
* Find rules how a good container images look like?
* Pushing the result to a registry
* Build the service with [12 factor rules](https://12factor.net) in mind!

## Other nice questions

* How you promote your image?
* What simple really mean?
* How well proven is your image at production?
* How easy other people can use your images?
* Which tools can help to check image quality?

## Helpful informations

* https://docs.docker.com/engine/reference/builder/
* https://docs.docker.com/develop/develop-images/dockerfile_best-practices/
* http://label-schema.org/rc1/
* https://microbadger.com/
