FROM debian:stretch-slim

MAINTAINER roc<imrocchan@gmail.com>

# gcc for cgo
RUN apt-get update && apt-get install -y --no-install-recommends \
		g++ \
		gcc \
		libc6-dev \
		make \
		pkg-config \
	&& rm -rf /var/lib/apt/lists/*

COPY go /usr/local/go

ENV GOLANG_VERSION 1.9.1
ENV GOROOT /usr/local/go
ENV GOPATH /go
ENV PATH $GOROOT/bin:$GOPATH/bin:$PATH

RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" "$GOPATH/pkg" && chmod -R 777 "$GOPATH"
WORKDIR $GOPATH
