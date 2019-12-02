# quic-stream-scheduling
QUIC Stream Scheduling Module for quiche

## Introduction

Modified http3 server and client using [quiche](https://github.com/cloudflare/quiche) to test various QUIC stream scheduling and resulting performance impact.

## Requirements and Dependencies

* Rust (tested on Rust 1.39)
* [quiche](https://github.com/cloudflare/quiche) and its dependencies

## Instructions

* Apply the `patch-quic-scheduling.patch` to the [quiche](https://github.com/cloudflare/quiche) library (tested on commit `7e68456620d96c1dedbdc23f496a16c4e81c958d`)
* Run the http3 server and client
