# Kata-05: Build an image without Docker

A colleague of yours read a new article on hacker news and want to convice you to use a new tool for building images like kaniko,buildah, img, jib. On the other side Docker supports a new build mechanisim called Buildkit. But how pratictle these tools in a real world and how handy are those ? 

Let's take a simple application to take as applictation example [bee42/whoami](https://github.com/bee42/whoamI).

```Dockerfile
ARG GOLANG_TARGET=${GOLANG_TARGET:-golang:1.11.0-stretch}
ARG TARGET=${TARGET:-alpine:3.8}
FROM ${GOLANG_TARGET} as build

ENV REPO=github.com/bee42/whoamI \
    OUTPUT_PATH=/output

RUN apt-get update && apt-get install -y --no-install-recommends git make curl && \
    curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh

ARG ARCH=${ARCH:-amd64}
ARG OS=${OS:-linux}
WORKDIR $GOPATH/src/${REPO}
COPY . .
RUN mkdir -p vendor && dep ensure
RUN mkdir -p $OUTPUT_PATH && \
    GOOS=${OS} GOARCH=${ARCH} CGO_ENABLED=0 go build -a --installsuffix cgo --ldflags="-s" -o $OUTPUT_PATH/whoamI

FROM ${TARGET}
LABEL maintainer nicals.mietz@bee42.com
LABEL maintainer peter.rossbach@bee42.com
COPY --from=build /output/whoamI /whoamI
ENTRYPOINT ["/whoamI"]
EXPOSE 80
```

How much work did it cost you to use this tools ? How differently behave them ?

How do you need to change this example, in order to transform it into a production ready Java image?

## Things to consider

* Are root privileges needed for executing these applications ? 
* Does it provide caching ? 
* Does it work with Multi Stage Builds ? 
* Build üpeed of an image creation 


## Helpful information

* https://github.com/AkihiroSuda/buildbench
* https://github.com/GoogleContainerTools/kaniko
* https://jaxenter.de/kaniko-docker-images-70153
* https://blog.codecentric.de/2018/07/docker-images-google-jib-kaniko/
