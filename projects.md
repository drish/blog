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
