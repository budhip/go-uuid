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

## Example

```go
package main

import (
	"github.com/sirupsen/logrus"

	"github.com/budhip/go-uuid"
)

func main() {
	// Creating UUID Version 4
	// panic on error
	u1 := uuid.Must(uuid.NewV4())
	logrus.Printf("UUIDv4: %s\n", u1)

	// Create a Version 4 UUID.
	newUUID4, errNewUUID4 := uuid.NewV4()
	if errNewUUID4 != nil {
		logrus.Fatalf("failed to generate UUID: %v", errNewUUID4)
	}
	logrus.Printf("generated Version 4 UUID %v", newUUID4)

	// Parse a UUID from a string.
	str := "6ba7b810-9dad-11d1-80b4-00c04fd430c8"
	strToUUID, ErrStrToUUID := uuid.FromString(str)
	if ErrStrToUUID != nil {
		logrus.Fatalf("failed to parse UUID %q: %v", str, ErrStrToUUID)
	}
	logrus.Printf("successfully parsed UUID %v", strToUUID)
}
```
