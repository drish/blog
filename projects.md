---
layout: page
title: Projects
---

Here you can find the list of projects I have been working on.

<br/>

## [ben](https://github.com/drish/ben)


**ben** is a CLI tool written in **Golang**.
The idea behind it is that you can configure it to run your benchmark code
under multiple hardware specs and environments, eg:

1. ubuntu:16.04 + golang:1.11 + 2vCPU + 8GB RAM
2. ubuntu:16.04 + golang:1.10.1 + 2vCPU + 8GB RAM

It would then spin up two short-lived containers using the hyper.sh cloud, run your benchmarks and generate
a report comparing both results for you.

I intend to go back to work on it this year, implementing support for [Kata Containers]()/[Firecracker]() MVMs, since
hyper.sh cloud has shutdown.

<br/>
## [dogstatsd-local](https://github.com/drish/dogstatsd-local)

**dogstatsd-local** is a simple UDP Service written in **Ruby**. It is meant to help when adding instrumentation with DataDog to your project, by acting as a sidecar container printing all incoming metrics to STDOUT in a JSON prettified format.

Adding to your project, via docker-compose:

```yml
version: '3.4'

services:
  dogstatsd-local:
    image: drish/dogstatsd-local
    ports:
      - 8125:8125/udp
```

Watch the logs:

```sh
~/drish/ » docker run -p 8125:8125 drish/dogstatsd-local
INFO -- : initialized dogstatsd-local 0.0.0.0:8125
INFO -- : waiting for statsd datagrams..
```

Send metrics using any statsD client

```ruby
require 'datadog/statsd'
statsd = Datadog::Statsd.new('dogstatsd-local', 8125)
statsd.increment('page.views')
```

Will log:

```json
I, [2019-09-18T18:44:38.221440 #1]  INFO -- : {"path":"page.views","namespace":"page","name":"views","value":1}
```

<br/>
## [benchparser](https://github.com/drish/benchparser)

**benchparser** is a **Ruby** gem that parses multiple languages benchmark outputs, e.g:

a Golang benchmark output:

```
goos: darwin
goarch: amd64
pkg: github.com/drish/parser
BenchmarkFib1-8     1000000000           2.48 ns/op        0 B/op        0 allocs/op
PASS
ok    github.com/drish/parser 9.960s
"
```

Now to parse that:

```ruby
require 'benchparser'
Bp.parse(data).functions.first[:iterations] # 1000000000
```

<br/>
## [cloak](https://github.com/drish/cloak)


**cloak** is a super simple CLI encryption tool written in **Golang**, it aims to help you
encrypting files using passphrases. It uses the incredible [scrypt](https://en.wikipedia.org/wiki/Scrypt) algorithm by Colin Percival for key derivation and [NaCL](https://nacl.cr.yp.to/) box for the actual encryption.

I have a long list of TODOs I would like to see implemented on it, eg: 
* key splitting using shamir algorithm
* hashicorp's vault integration.

**It shouldn't be used in production since this tool has never been formally validated by a cryptographer, like all crypto software should be.** 

<br/>
## [hyperb](https://github.com/drish/hyperb)

**hyperb** was the official **Ruby Gem** for of [Hyper.sh]() cloud API. It supported almost 95% of their API.
Unfortunately they had to [shutdown](https://news.ycombinator.com/item?id=18734658), their team is currently working on [Kata Containers](https://katacontainers.io), which seems to be a really interesting project.

<br/>
## [franz cloud](https://github.com/kinche/franz)

**franz cloud** is a platform still WIP, I am currently planning and designing it. More details to come soon !!

<br/>
## [library](https://github.com/drish/library)

collection of papers I'm interested on.

~
