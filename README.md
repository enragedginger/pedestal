# Pedestal + Pants Build System

> **This is a fork of [Pedestal](https://github.com/pedestal/pedestal)** used to evaluate the [Pants build system](https://www.pantsbuild.org/) with a large, real-world Clojure codebase using the [pants-backend-clojure](https://github.com/enragedginger/pants_backend_clojure) plugin. This fork is not kept in sync with upstream Pedestal and should not be used as a dependency. For the actual Pedestal framework, see the [official repository](https://github.com/pedestal/pedestal).

## Why Pants for Clojure?

Pedestal is an 11-module Clojure monorepo with 42 test files, Java interop, and a consolidated test directory — a good stress test for build tooling. This fork adds Pants support alongside the existing `deps.edn` + `build.clj` setup. Both build systems coexist without interference.

**What Pants brings to a Clojure project:**

- **Parallel test execution** — All 42 test files run concurrently. The standard `clj -X:test` runner is sequential.
- **Fine-grained caching** — After a warm run, only tests affected by changed files re-run. Unchanged tests return instantly from cache.
- **File-level dependency tracking** — Pants knows which tests depend on which source files, so changing one file doesn't invalidate the entire suite.
- **Unified toolchain** — `pants lint ::`, `pants fmt ::`, `pants test ::`, and `pants check ::` all through one command, with consistent caching and parallelism.
- **Hermetic sandboxed builds** — Each test runs in an isolated sandbox, surfacing implicit dependencies that a flat classpath hides. This migration uncovered several undeclared dynamic dependencies in Pedestal.

**Current status:** 40 of 42 tests pass. See [Known Test Failures](#known-test-failures) for details on the remaining 2.

## Getting Started with Pants

```bash
# Run all tests
pants test ::

# Run a single test
pants test tests/test/io/pedestal/http/cors_test.clj

# Lint all sources
pants lint ::

# Format all sources
pants fmt ::

# Check compilation
pants check ::
```

See [`pants.toml`](pants.toml) for the full Pants configuration and the `BUILD` files throughout the repo for target declarations.

## Known Test Failures

**`ring_middlewares_test` — `fast-resource-is-valid`** (1 error + 1 failure out of 51 assertions)

The legacy `fast-resource` interceptor calls `(io/as-file (io/resource path))`, which requires resources to be backed by actual filesystem files (`file://` URLs). Pants packages `resources()` targets into JARs, so `io/resource` returns `jar:file://` URLs that can't be converted to a `File`. Pedestal's modern `resource-routes` API handles both protocols correctly and passes all its tests. This only affects the deprecated `fast-resource` interceptor.

**`resources_test` — `access-resource-from-jar-with-spaces-test`** (1 error out of 33 assertions)

This test requires a custom JAR file (`test with spaces/jar with spaces.jar`) built by `tests/build.clj` and included on the classpath via `deps.edn :paths`. This JAR is not built or available under Pants. The test validates an edge case in classpath resource loading from JARs with spaces in their paths.

## Links

- [pants-backend-clojure](https://github.com/enragedginger/pants_backend_clojure) — The Pants plugin for Clojure
- [Pants Build System](https://www.pantsbuild.org/) — The build system
- [Pedestal (upstream)](https://github.com/pedestal/pedestal) — The official Pedestal repository

---

# Pedestal (Upstream README)

Pedestal is a set of libraries written in Clojure that aims to bring
both the language and its principles (Simplicity, Power, and Focus) to
server-side development.

Pedestal features:
- Secure by default
- Batteries included, but designed for extensibility
- Asynchronous request handling
- Server Sent Events and WebSockets as first class citizens
- Integrated logging, metrics, and tracing
- Default integration with [Jetty 12](https://eclipse.dev/jetty/) and [Http-Kit](https://github.com/http-kit/http-kit)

You can stand up a basic Pedestal server in just a few lines of code
(see the [guides in the documentation](https://pedestal.io/pedestal/0.7/guides/hello-world.html)), but Pedestal is designed to grow with you, 
as your application matures and expands.

See the [full documentation](http://pedestal.io) for far more detail about
using Pedestal, its design, and its philosophy.

Pedestal requires Clojure 1.11 or later, and works with Servlet API 5.0 and Java 17 and up.

## Support

Primary support is on the [#pedestal channel of Clojurians Slack](https://clojurians.slack.com/archives/C0K65B20P).

## Contributing

See [the Pedestal Contributor's guide](https://pedestal.io/pedestal/0.8/contributing.html) for details on contributing to Pedestal.

### Running the tests

From the `tests` subdirectory, execute `clj -X:test`.

---

## License
Copyright 2013 Relevance, Inc.

Copyright 2014-2022 Cognitect, Inc.
Copyright 2023-2026 Nubank NA

The use and distribution terms for this software are covered by the
Eclipse Public License 1.0 (http://opensource.org/licenses/eclipse-1.0)
which can be found in the file [epl-v10.html](epl-v10.html) at the root of this distribution.

By using this software in any fashion, you are agreeing to be bound by
the terms of this license.

You must not remove this notice, or any other, from this software.
