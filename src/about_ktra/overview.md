# Overview

## What is `Ktra`?

`Ktra` is a implementation of the [Alternate Registry](https://doc.rust-lang.org/cargo/reference/registries.html) that is introduced for non-public crates in Rust/Cargo 1.34.

In other words, `Ktra` is an all-in-one package for the private cargo registry.

## When I/we need `Ktra`?

If you write a Rust crate in your job, your codes might be proprietary and/or closed-source.  
[crates.io](https://crates.io) cannot host closed-source crates so you have to construct a private registry by yourself.  
`Ktra` could help to reduce that annoying operations.

## What does `Ktra` mean?

`Ktra` is named after shortened name of [Kei truck](https://en.wikipedia.org/wiki/Kei_truck) which is a japanese style mini pickup truck.

You can pronounce `Ktra` as you like.  
For your information, most native japanese speaker do it *KEI-TORA* or *KE-TORA*. 

## License

`Ktra` is icensed under either of [Apache License, Version 2.0](https://github.com/moriturus/ktra/blob/main/LICENSE-APACHE) or [MIT license](https://github.com/moriturus/ktra/blob/main/LICENSE-MIT) at your option.