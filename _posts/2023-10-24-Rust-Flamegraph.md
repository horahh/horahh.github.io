---
title: Flamegraphs With Rust
date: 2023-10-24 12:00:00 -0600
categories: [programming,software]
tags: [programming,hardware,software,rust,python]
---
# Learning Flamegraphs with Cargo and Rust
## [Flamegraphs](https://www.brendangregg.com/flamegraphs.html) 

Flame Graphs are visualizations based call stack sampled at quantized moments to statistically reflect from the total spent time running (sampling) an application what function did the program was running and tying that to the respective call stack, the samples with the same call stack get grouped togheter showing a representation of time based on the width of each function call in the stack.

Flame Graphs are images but it goes beyond that, they are svg file that are interactive so that you can select a specific call and kind of zoom and better uderstand what are the particular details related to the time spent by a function and how is distributed based on what other funtions were called by it.

## Using Cargo to create a flamegraph

In order to create a flamegraph we need an aplication that span for enough time to be sampled and provide enough insights on its behavior, as a test example  lets work with this simple code:

### Code Example
```rust
use core::time::Duration;
use std::thread;
fn main() {
    for _ in 0..1000 {
        f1();
        f2();
        f3();
    }
}

fn f1() {
    thread::sleep(Duration::from_millis(10));
}
fn f2() {
    thread::sleep(Duration::from_millis(20));
}
fn f3() {
    thread::sleep(Duration::from_millis(30));
    f4()
}

fn f4() {
    thread::sleep(Duration::from_millis(40));
}

```

Let's disect what the code is doing, the idea is to run several functions and allow us to observe how the execution time is split between the functions so that in a real application we could be able to identify the bottleneck or the functions that take the most time so we could concentrate efforts in those.

The functions are only sleeping for the purpose of allowing a good control on how the visualiztion is shown. The execution time will get splitted proportional to the time spend on each function, notice f3 calls f4 so that in the flamegraph f3 time should be the sum of the sleep within f3 plus the time of f4, and will also allow the visualiztion of the call stack of f4 on top of f3.

### Dependencies
Install cargo-flamegraph 

```
cargo install flamegraph
```

Install linux perf tools:

* https://www.swift.org/server/guides/linux-perf.html

### Compiling with Cargo

We have the code and now is a matter of using cargo to create a new project.


```
cargo new perf_bench
cargo run
cargo flamegraph
```


### Flamegraph

![Flame Graph](https://drive.google.com/uc?export=view&id=1hmbXxxizET_26TiI1jjRUqzORoJ4vOlV)

Notice the botton having the executable name which is the same name of the project and then going up in the call stack, main can be seen as well as f1...f3 and the nested f4 call, just as expected within them the respective calls to the sleep function.

From the graph it can clearly seen how the execution time is spend along the call stack which would be really helpful to get the insights of what are the bottle necks and where to spend effort optimizing.

This graph was generated on Ubuntu22 running WSL2.

Additional Information on flamegraphs:
* [Rust-Flamegraphs](https://github.com/flamegraph-rs/flamegraph#systems-performance-work-guided-by-flamegraphs)
* [Flamegraphs](https://www.brendangregg.com/flamegraphs.html)


### Github code

* [github_link_to_this_project](https://github.com/flamegraph-rs/flamegraph#systems-performance-work-guided-by-flamegraphs)
