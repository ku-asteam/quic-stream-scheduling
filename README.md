# quic-stream-scheduling
Modified QUIC stream scheduling for [quiche](https://github.com/cloudflare/quiche)

## Introduction

Modified http3 server and client using [quiche](https://github.com/cloudflare/quiche) to test various QUIC stream scheduling and resulting performance impact. Unlike TCP which adopts single stream abstaction, QUIC supports multiple streams in a single connection to multiplex independent application data. For each endpoint, deciding which stream to send in each epoch can affect the performance of the session, especially the latency of each data request. The current [quiche](https://github.com/cloudflare/quiche) supports only round-robin manner.

## Requirements and Dependencies

* Rust (tested on Rust 1.39)
* [quiche](https://github.com/cloudflare/quiche) and its dependencies (like [BoringSSL](https://github.com/google/boringssl))

## Instructions

* Apply the `patch-quic-scheduling.patch` to the [quiche](https://github.com/cloudflare/quiche) library (tested on commit `7e68456620d96c1dedbdc23f496a16c4e81c958d`)
* Run the http3 server
`./http3-server`
* Run the http3 client 
`./http3-client --no-verify https://127.0.0.1:4433/`
