# Go Twirp!

An example client / server for the Simple RPC framework powered by protobuf.

## What is it?

Twirp is a simple RPC framework built on `protobuf`. You define a service in a `.proto` specification file, then Twirp will generate servers and clients for that service. It's your job to fill in the "business logic" that powers the server, and then generated clients can consume your service straight away.

## Prerequisites

* Golang (a recent version -- I am using 1.16.3)
* [Protocol buffer compiler](https://grpc.io/docs/protoc-installation/) 

~~~bash
# Install protoc-gen-go plugin (to generate .pb.go files)
$ go get google.golang.org/protobuf/cmd/protoc-gen-go@latest

# Install protoc-gen-twirp plugin (to generate .twirp.go files)
$ go get github.com/twitchtv/twirp/protoc-gen-twirp@latest
~~~

## Development

1. Define the interface in `rpc/fxrates/service.proto`
2. Generate the code with `protoc --twirp_out=. --go_out=paths=. rpc/fxrates/service.proto`