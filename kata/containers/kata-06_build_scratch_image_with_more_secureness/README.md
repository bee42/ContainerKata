# Kata-04: Build Scratch Images with a User


When you are using Scratch Layers in your Docker Images are these the final step to archieve. Sometimes you also want to provide more stability in terms of a separate user for app or providing certificates to the application. But how could this work in real ? 

Let's look at this simple go lang app as a start:
```go
package main

import (
	"fmt"
	"log"
	"net/http"
)

// main runs some tests to exercise the environment, including
// loading a timezone and verifying a well-known TLS certificate.
func main() {
	fmt.Println("\nTests from within scratch container:")
	testTLS()
}

func testTLS() {
	rsp, err := http.Get("https://meetup.com")
	if err != nil {
		log.Panicf("Unable to establish https connection: %s\n", err)
	} else {
		rsp.Body.Close()
		log.Println("Successfully established https connection")
	}
}
```

```Dockerfile
FROM golang:1.11-stretch as build
WORKDIR /go/src/app
COPY . .
RUN CGO_ENABLED=0 go build -o app 

FROM scratch
COPY --from=build /go/src/app/app /app
ENTRYPOINT ["/app"]
```

How do you need to change this example, in order to transform it into a production ready Application image with a User and Certificates ?

## Things to consider

* Which user should run the application?
* What is really needed for your application to run ?


## Helpful information

* https://medium.com/@lizrice/non-privileged-containers-based-on-the-scratch-image-a80105d6d341
