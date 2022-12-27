FROM golang:1.12.5 as build

RUN go mod download && \
    go mod verify

COPY  main.go  $GOPATH/src/app/

RUN CGO_ENABLED=0 GOOS=linux go build \
    -a -installsuffix cgo -o $GOPATH/src/app/  && \
    chmod 755 /app
#RUN section

FROM scratch

COPY --from=build app .
COPY form.html  /static

EXPOSE 8080

ENTRYPOINT ["./app"]