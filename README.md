# go-uuid is UUID package for Go language

This package provides pure Go implementation of Universally Unique Identifier (UUID). Supported both creation and parsing of UUIDs.

Supported versions:
* Version 1, based on timestamp and MAC address (RFC 4122)
* Version 2, based on timestamp, MAC address and POSIX UID/GID (DCE 1.1)
* Version 3, based on MD5 hashing (RFC 4122)
* Version 4, based on random numbers (RFC 4122)
* Version 5, based on SHA-1 hashing (RFC 4122)

## History
This repository based on from [github.com/satori/go.uuid](https://github.com/satori/go.uuid) after it seems to be no longer maintained.
Then I decided to make a little modification and maintenance because there were many issues that hadn't been completed in more than a year. And I get a few issues while working on a product.

Hopefully this repository can help other people who want to use uuid on Go.

## Installation

Use the `go` command:

	$ go get github.com/budhip/go-uuid

## Requirements

UUID package requires Go >= 1.2.
