---
title: Benchmarks With Rust
date: 2023-09-28 12:00:00 -0600
categories: [programming,software]
tags: [programming,hardware,software,rust,python]
---

# IN PROGRESS...

Trying to create applications that are highly performant require nowadays to be multithreaded in order to take advantage of the whole processing power of modern processors. To put this into perspective Intel just announced a [144 core](https://www.tomshardware.com/news/intel-details-sierra-forest-and-granite-rapids-architecture-xeon-roadmap) Xeon processor, imagine having a single thread process running in such a processor with 143 cores just idle! less than 1% of processing capacity being used!

It is important to have a baseline of a single thread program performance to understand how well an application scales with adding more threads/cores. [Amdahl's Law](https://en.wikipedia.org/wiki/Amdahl%27s_law) states that parallel performance cannot be linear, which would be the desired case. So we hope for a good algorithm to scale close to linear in performance and that is something that needs to be measured.

## Cargo

[Cargo](https://doc.rust-lang.org/cargo/) is the Rust package manager besides helping with project dependencies and compilation, there are other tooling like code formatting, even additional fuctionality could be installed like benchmarks and flamegraphs which is pretty convenient and easy to use for the purpose of performance analysis.

## Cargo-Bench 

[Cargo-Bench](https://doc.rust-lang.org/cargo/commands/cargo-bench.html) is a benchmark tooling that can be directly with cargo to benchmark code by writing a benchmark file with the testing scenario desired, it takes several measures and provides as an output 3 measure being low, average and high.


## Flamegraphs

[Flame Graphs](https://www.brendangregg.com/flamegraphs.html) are a visualization based on sampling of the call stack at quantized moments to statistically reflect from the total spent time running (sampling) an application what function did the program was running and tying that to the respective call stack, the samples with the same call stack get grouped togheter showing a representation of time based on the width of each function call in the stack.

Flame Graphs are images but it goes beyond that, they are svg file that are interactive so that you can select a specific call and kind of zoom and better uderstand what are the particular details related to the time spent by a function and how is distributed based on what other funtions were called by it.

![Flame Graph](https://www.chromium.org/developers/profiling-flame-graphs/flamegraph.png){: width="350" height="200" }

image credit: [chromium project](https://www.chromium.org/developers/profiling-flame-graphs/)


## TO BE CONTINUED...