---
title: asterinas
date: 2024-10-27T12:19:14+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1726629597612-a48c0fdd0fe6?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MzAwMDI3NDJ8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1726629597612-a48c0fdd0fe6?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MzAwMDI3NDJ8&ixlib=rb-4.0.3
---

# [asterinas/asterinas](https://github.com/asterinas/asterinas)

<p align="center">
    <img src="docs/src/images/logo_en.svg" alt="asterinas-logo" width="620"><br>
    A secure, fast, and general-purpose OS kernel written in Rust and compatible with Linux<br/>
    <a href="https://github.com/asterinas/asterinas/actions/workflows/test_osdk.yml"><img src="https://github.com/asterinas/asterinas/actions/workflows/test_osdk.yml/badge.svg?event=push" alt="Test OSDK" style="max-width: 100%;"></a>
    <a href="https://github.com/asterinas/asterinas/actions/workflows/test_asterinas.yml"><img src="https://github.com/asterinas/asterinas/actions/workflows/test_asterinas.yml/badge.svg?event=push" alt="Test Asterinas" style="max-width: 100%;"></a>
    <a href="https://asterinas.github.io/benchmark/"><img src="https://github.com/asterinas/asterinas/actions/workflows/benchmark_asterinas.yml/badge.svg" alt="Benchmark Asterinas" style="max-width: 100%;"></a>
    <br/>
</p>

English | [中文版](README_CN.md) | [日本語](README_JP.md)

## Introducing Asterinas

Asterinas is a _secure_, _fast_, and _general-purpose_ OS kernel
that provides _Linux-compatible_ ABI.
It can serve as a seamless replacement for Linux
while enhancing _memory safety_ and _developer friendliness_.

* Asterinas prioritizes memory safety
by employing Rust as its sole programming language
and limiting the use of _unsafe Rust_
to a clearly defined and minimal Trusted Computing Base (TCB).
This innovative approach,
known as [the framekernel architecture](https://asterinas.github.io/book/kernel/the-framekernel-architecture.html),
establishes Asterinas as a more secure and dependable kernel option.

* Asterinas surpasses Linux in terms of developer friendliness.
It empowers kernel developers to
(1) utilize the more productive Rust programming language,
(2) leverage a purpose-built toolkit called [OSDK](https://asterinas.github.io/book/osdk/guide/index.html) to streamline their workflows,
and (3) choose between releasing their kernel modules as open source
or keeping them proprietary,
thanks to the flexibility offered by [MPL](#License).

While the journey towards a production-grade OS kernel can be challenging,
we are steadfastly progressing towards our goal.
Currently, Asterinas only supports x86-64 VMs.
However, [our aim for 2024](https://asterinas.github.io/book/kernel/roadmap.html) is
to make Asterinas production-ready on x86-64 VMs.

## Getting Started

Get yourself an x86-64 Linux machine with Docker installed.
Follow the three simple steps below to get Asterinas up and running.

1. Download the latest source code.

```bash
git clone https://github.com/asterinas/asterinas
```

2. Run a Docker container as the development environment.

```bash
docker run -it --privileged --network=host --device=/dev/kvm -v $(pwd)/asterinas:/root/asterinas asterinas/asterinas:0.9.4
```

3. Inside the container, go to the project folder to build and run Asterinas.

```bash
make build
make run
```

If everything goes well, Asterinas is now up and running inside a VM.

## The Book

See [The Asterinas Book](https://asterinas.github.io/book/) to learn more about the project.

## License

Asterinas's source code and documentation primarily use the 
[Mozilla Public License (MPL), Version 2.0](https://github.com/asterinas/asterinas/blob/main/LICENSE-MPL).
Select components are under more permissive licenses,
detailed [here](https://github.com/asterinas/asterinas/blob/main/.licenserc.yaml). For the rationales behind the choice of MPL, see [here](https://asterinas.github.io/book/index.html#licensing).