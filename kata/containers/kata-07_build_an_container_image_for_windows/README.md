# Kata-07: Build an image for your Windows app


When you are googeling for things like "Docker and Windows", you'll be able to find lot of articles, guides and blog posts telling you how to do it. But how much of a real life example do these articles actually provide? 

Let's look at this Dockerfile as a start (taken from [Stefan Scherer's Dockerfiles](https://github.com/StefanScherer/dockerfiles-windows/blob/master/webserver/Dockerfile)):

```
FROM microsoft/iis

RUN powershell -NoProfile -Command Remove-Item -Recurse C:\inetpub\wwwroot\*

WORKDIR /inetpub/wwwroot

COPY content/ .
```

What is really needed to run this application ? 

## Things to consider

* Which user should run the application?
* Which proccess will be executed ?
* Is there also a lighweight version ?
* How does the isolation works ? 


## Helpful information

* https://stefanscherer.github.io/how-to-run-lightweight-windows-containers-on-windows-10/
* https://github.com/StefanScherer/dockerfiles-windows/tree/master/webserver
* https://github.com/StefanScherer/dockerfiles-windows
* https://hub.docker.com/_/microsoft-windows-servercore-iis
