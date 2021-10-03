FROM golang:1.8-alpine
ADD . /go/src/k2
RUN go install k2

FROM alpine:latest
COPY --from=0 /go/bin/k2 .
ENV PORT 8080
CMD ["./k2"]
