---
title: Benchmarks With Rust
date: 2023-09-27 12:00:00 -0600
categories: [programming,software]
tags: [programming,hardware,software,rust,python]
---

Trying to create applications that are highly performant require nowadays to be multithreaded in order to take advantage of the whole processing power of the processor. 

It is important to have a baseline of a single thread program performance to understand how well an application scales with adding more threads/cores. [Amdahl's Law](https://en.wikipedia.org/wiki/Amdahl%27s_law) states that parallel performance cannot be linear, which would be the desired case. So we hope for a good algorithm to scale close to linear in performance and that is something that needs to be measured.

## Cargo

[Cargo](https://doc.rust-lang.org/cargo/) is the Rust package manager besides helping with project dependencies and compilation, there are other tooling like code formatting, even additional fuctionality could be installed like benchmarks and flamegraphs which is pretty convenient and easy to use for the purpose of performance analysis.

## Benchmarks

## Flamegraphs
