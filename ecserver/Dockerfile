FROM golang:1.20-alpine3.17 as builder
LABEL maintainer="mgdevstack" \
    vendor="Zettabytes" \
    owner="zbio"
ADD main.go  .
RUN GO111MODULE=off CGO_ENABLED=0 GOOS=linux go build -o app

FROM alpine:3.17
LABEL maintainer="mgdevstack" \
    vendor="Zettabytes" \
    owner="zbio"
COPY --from=builder /go/app /app
USER nobody
ENTRYPOINT ["/app"]
