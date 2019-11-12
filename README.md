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
You are free to disable these log messages using the options `logStarting` and `logCompleted` of the `Middleware` struct.
The intention is to allow to replace these generic messages with custom messages more fitted to the usecase.

Note that if logging completed requests is disabled and negroni-logrus is part of an entire chain of middlewares, logging the exact moment of the completed request is not possible.
Logging e.g. a custom message for a completed request is delayed until all middlewares have finished.

