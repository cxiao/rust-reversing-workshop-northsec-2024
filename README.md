# Reversing Rust Binaries: One step beyond strings - NorthSec 2024 Workshop

This repository contains the supplementary files for the [_Reversing Rust Binaries: One step beyond strings_ workshop at NorthSec 2024](https://nsec.io/session/2024-reversing-rust-binaries-one-step-beyond-strings.html).

During the presentation, we will be building and reversing a very simple Rust binary - a benign downloader. The source code for the downloader is inside this repository, in the `simple-downloader/` folder.

You will need the following:

1) A machine that can build a Rust binary. We'll be pulling dependencies to build the binary, so that machine should have internet access.
2) A machine that can run the Rust binary you built. We'll be building a benign downloader in this workshop, so that machine should ideally also have internet access. 
3) Your preferred reverse engineering tool, for reversing the Rust binary you built!

## Manual Setup

If you would like to do this entirely from the comfort of your own existing machine, you can use the manual instructions below!

### Installing the Rust Toolchain

The official toolchain setup instructions are at https://rustup.rs/. Follow the instructions there; the page will display specific instructions for your operating system.

Check, after installation, that you can run both the newly installed `rustup` and `cargo` tools:

```
$ rustup --version
rustup 1.27.0 (bbb9276d2 2024-03-08)
info: This is the version for the rustup toolchain manager, not the rustc compiler.
info: The currently active `rustc` version is `rustc 1.77.1 (7cf61ebde 2024-03-27)`
```

```
$ cargo --version
cargo 1.77.1 (e52e36006 2024-03-26)
```

We'll be using Rust version 1.77.1 in this workshop, so install that version, and switch your toolchain to that version as the default for all builds:

```
rustup install 1.77.1
rustup default 1.77.1
```

### Linux users: Ensure you have build tools

If you're building on Windows or macOS, you can skip this step.

If you're building on Linux: Parts of this build rely on `gcc`, `ld`, `pkg-config`, and the OpenSSL development headers. On Ubuntu, you can install these with

```
sudo apt install build-essential
sudo apt install pkg-config
sudo apt install libssl-dev
```