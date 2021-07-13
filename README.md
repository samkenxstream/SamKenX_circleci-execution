# Go service building blocks
This repository contains a collection of packages designed to aid building
reliable, observable, zero-downtime services using Go.

## What is in here?
- `conf/env` Load application config from environment variables (we are moving away from this).
- `conf/o11y` Wiring code for the `o11y` package.
- `conf/secret` Don't store your secrets in a string that can be accidentally logged.
  Use a `secret.String` instead.
- `db` Common patterns using when talking to an RDBMS. Currnetly only supports PostgreSQL.
- `httpclient` A simple HTTP client that adds observability and resilience to the standard
  Go HTTP client.
- `httpserver` Starting and stopping the standard Go http server cleanly.
- `o11y` Observability that is currently backed by Honeycomb. It also supports outputting
  trace data as JSON and plain or colored text output.
- `system` Manage the startup, running, metrics and shutdown of a Go service.
- `termination` A handler to aid signal based service termination. (Used internally by
  the `system` package).
- `testing/compiler` At CircleCI we aim to acceptance test whole compiled binaries. This
  package lets us do that, while capturing test coverage for the binary.
- `testing/download` Download releases of binaries for using in end to end service testing.
- `testing/httprecorder` Record HTTP requests inside an HTTP server, and search them.
- `testing/kongtest` If you are using [kong](https://github.com/alecthomas/kong) for your
  CLI parsing, this helps in writing golden tests for the CLI definition.
- `testing/releases` Helper to determine which binaries to download for end to end tests.
- `testing/testcontext` Setup a background context that includes `o11y`.
- `worker` Run a service worker loop with observability and back-off for no work found.

## Who is this for?
These packages are intended to be used internally at CircleCI. While this code is licenced
permissively with an MIT licence, this is not a true "open source" project, in that there is
no active community using it. 

## No guaranteed API stability
While we do not intentionally aim to break compatibility, we make no promises that we will
maintain a stable API if there are good reasons to break it.
