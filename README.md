negroni-logrus
==============

[![GoDoc](https://godoc.org/github.com/meatballhat/negroni-logrus?status.svg)](https://godoc.org/github.com/meatballhat/negroni-logrus)
[![Build Status](https://travis-ci.org/meatballhat/negroni-logrus.svg?branch=master)](https://travis-ci.org/meatballhat/negroni-logrus)

logrus middleware for negroni

## Usage

Take a peek at the [basic example](./examples/basic/example.go) or the [custom
example](./examples/custom/example.go), the latter of which includes setting a
custom log level on the logger with `NewCustomMiddleware`.

If you want to reuse an already initialized `logrus.Logger`, you should be using
`NewMiddlewareFromLogger` (see [existinglogrus](./examples/existinglogrus/example.go)).

## Logging

By default, starting requests and completed requests will be logged.
You can disable start messages using the option `logStarting` of the `Middleware` struct.
You can disable completion messages by replacing the `Middleware.After` function with one that does not log.
