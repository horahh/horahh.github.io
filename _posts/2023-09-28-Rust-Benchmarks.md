---
title: Benchmarks With Rust
date: 2023-09-28 12:00:00 -0600
categories: [programming,software]
tags: [programming,hardware,software,rust,python]
---

## Unleashing the Power of Multithreading: Harnessing Modern Processor Potential

In the pursuit of creating highly performant applications, the key to success in today's computing landscape often lies in embracing multithreading. It's the secret sauce that allows us to tap into the immense processing power of modern CPUs. To illustrate this, consider Intel's recent announcement of a [144-core Xeon processor](https://www.tomshardware.com/news/intel-details-sierra-forest-and-granite-rapids-architecture-xeon-roadmap). Imagine a single-threaded process running on such a behemoth, with a staggering 143 cores idly twiddling their digital thumbs, accounting for less than 1% of the processor's immense capacity!

This underscores the importance of establishing a performance baseline for single-threaded programs. It serves as our reference point, enabling us to gauge how effectively an application can scale when we introduce additional threads and cores. [Amdahl's Law](https://en.wikipedia.org/wiki/Amdahl%27s_law), a fundamental concept in parallel computing, reminds us that parallel performance can't achieve perfect linearity, which would be the ideal scenario. Instead, we strive for algorithms that scale as close to linear performance as possible—an accomplishment that demands rigorous measurement and evaluation.

Now, let's delve into some of the tools that we will be using for our first benchmark project.

## [Cargo](https://doc.rust-lang.org/cargo): More Than Just a Rust Package Manager

The Rust package manager, goes beyond its role of managing project dependencies and compilation. It's a versatile tool that offers a range of functionalities to streamline your development process.

Not only does Cargo assist in managing dependencies, but it also facilitates code formatting and provides a platform for extending functionality. You can effortlessly enhance your Rust projects' performance with benchmarks and flamegraphs for in-depth performance analysis. It's a convenient to ensure your projects are not only well-structured but also optimized for peak performance.


## [Cargo-Bench](https://doc.rust-lang.org/cargo/commands/cargo-bench.html): Benchmarking with Ease

Cargo-bench, a versatile benchmarking tool seamlessly integrated with Cargo, transforms the process of performance analysis in Rust. By crafting a benchmark file with your desired testing scenarios, you unlock a world of possibilities.

This tool not only measures your code's performance but also provides three valuable metrics: low, average, and high. It doesn't stop there; it goes the extra mile by offering insightful comparisons with previous benchmarks, clearly indicating whether your code has seen performance improvements or encountered degradation.

With cargo-bench, optimizing your Rust projects becomes a straightforward endeavor, ensuring that your code not only runs smoothly but excels in its performance.

## [Flamegraphs](https://www.brendangregg.com/flamegraphs.html) 

Flame Graphs are visualizations based call stack sampled at quantized moments to statistically reflect from the total spent time running (sampling) an application what function did the program was running and tying that to the respective call stack, the samples with the same call stack get grouped togheter showing a representation of time based on the width of each function call in the stack.

Flame Graphs are images but it goes beyond that, they are svg file that are interactive so that you can select a specific call and kind of zoom and better uderstand what are the particular details related to the time spent by a function and how is distributed based on what other funtions were called by it.

![Flame Graph](https://www.chromium.org/developers/profiling-flame-graphs/flamegraph.png){: width="350" height="200" }

Image credit: [chromium project](https://www.chromium.org/developers/profiling-flame-graphs/).

## Rayon: Parallelism [Magic!](https://developers.redhat.com/blog/2021/04/30/how-rust-makes-rayons-data-parallelism-magical)

Rayon is a library that makes parallelism easy and safe at the same time. We are going to use it to work with threads and hopefully speed up our code.

>[Rayon](https://docs.rs/rayon/latest/rayon/) is lightweight and convenient for introducing parallelism into existing code. It guarantees data-race free executions and takes advantage of parallelism when sensible, based on work-load at runtime.

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
