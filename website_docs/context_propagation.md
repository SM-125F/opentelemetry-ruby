---
title: "Ruby Context Propagation"
weight: 24
description: >
  <img width="35" src="https://raw.github.com/open-telemetry/opentelemetry.io/main/iconography/32x32/Ruby_SDK.svg"></img>
  A language-specific implementation of OpenTelemetry in Ruby.
---

## Context Propagation

Traces can extend beyond a single process. This requires _context propagation_, a mechanism where identifiers for a trace are sent to remote processes.

In order to propagate trace context over the wire, a propagator must be registered with the OpenTelemetry SDK.
The W3 TraceContext and Baggage propagators are configured by default, however operators may override this value by setting `OTEL_PROPAGATORS` environment variable to a comma separated list of [propagators](https://github.com/open-telemetry/opentelemetry-ruby/tree/main/propagator).

```sh
export OTEL_PROPAGATORS=tracecontext,baggage,b3
```

You will also have to add a gem dependency:

```sh
gem install opentelemetry-propagator-b3
```

or via `Bundler` by adding the following to your `Gemfile`:

```ruby
gem 'opentelemetry-propagator-b3'
```

followed by:

```sh
bundle install
```
