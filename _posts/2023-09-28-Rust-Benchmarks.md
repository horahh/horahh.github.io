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

[Flame Graphs](https://www.brendangregg.com/flamegraphs.html) are visualizations based call stack sampled at quantized moments to statistically reflect from the total spent time running (sampling) an application what function did the program was running and tying that to the respective call stack, the samples with the same call stack get grouped togheter showing a representation of time based on the width of each function call in the stack.

Flame Graphs are images but it goes beyond that, they are svg file that are interactive so that you can select a specific call and kind of zoom and better uderstand what are the particular details related to the time spent by a function and how is distributed based on what other funtions were called by it.

![Flame Graph](https://www.chromium.org/developers/profiling-flame-graphs/flamegraph.png){: width="350" height="200" }

Image credit: [chromium project](https://www.chromium.org/developers/profiling-flame-graphs/).

## First Rust Profiling Project

A little optimization project [zip_test](https://github.com/horahh/zip_test) in which I am working for processing file contents within a zip file using Rust.

The code heavily relies on parallel library rayon uses iterators, closures and map reduce functions which is very [functional](https://doc.rust-lang.org/book/ch13-00-functional-features.html) influenced syntax.

### Zip File Processing

Zip files are an efficient way to store information specially if it comes from text, also  are though of as just an array of bytes and when decompressed their contents could be known. Actually zip file format consists of a header that provides pointers in this byte array to the different files the file holds so that individual files could be extracted. This is something very efficient in order to process only some of the content files.

To process a zip file there is a [crate](https://doc.rust-lang.org/book/ch07-01-packages-and-crates.html) called zip-rs which is easy to use and very stable. For now is the selected library to start our benchmarking.

To process the files efficiently we are going to use rayon which is another crate for parallel processing, this way will allow us to take the most advantage out of the multiple cores in the processor.


``` Rust

```

## TO BE CONTINUED...
