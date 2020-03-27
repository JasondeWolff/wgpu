<img align="right" width="25%" src="logo.png">

This is an active GitHub mirror of the WebGPU implementation in Rust, which now lives in "gfx/wgpu" of [Mozilla-central](https://hg.mozilla.org/mozilla-central/file/tip/gfx/wgpu). Issues and pull requests are accepted, but some bidirectional synchronization may be involved.

# WebGPU

[![Matrix](https://img.shields.io/badge/Matrix-%23wgpu%3Amatrix.org-blueviolet.svg)](https://matrix.to/#/#wgpu:matrix.org)
[![Build Status](https://travis-ci.org/gfx-rs/wgpu.svg?branch=master)](https://travis-ci.org/gfx-rs/wgpu)
[![Crates.io](https://img.shields.io/crates/v/wgpu-core.svg?label=wgpu-core)](https://crates.io/crates/wgpu-core)
[![Crates.io](https://img.shields.io/crates/v/wgpu-native.svg?label=wgpu-native)](https://crates.io/crates/wgpu-native)

This is an experimental [WebGPU](https://www.w3.org/community/gpu/) implementation, exposing both Rust and C interfaces as a native static library. It's written in Rust and is based on [gfx-hal](https://github.com/gfx-rs/gfx) with help of [gfx-extras](https://github.com/gfx-rs/gfx-extras). See the upstream [WebGPU specification](https://gpuweb.github.io/gpuweb/) (work in progress).

The implementation consists of the following parts:

  1. `wgpu-core` - internal Rust API for WebGPU implementations to use
  2. `wgpu-native` - the native implementation of WebGPU as a C API library
  3. `wgpu-remote` - remoting layer to work with WebGPU across the process boundary, as a C API library used by Gecko
  4. `wgpu-types` - Rust types shared between `wgpu-core`, `wgpu-native`, `wgpu-remote`, and [`wgpu-rs`](https://github.com/gfx-rs/wgpu-rs)
  5. `ffi` - the C headers generated by [cbindgen](https://github.com/eqrion/cbindgen) for the native headers

# Bindings

- [gfx-rs/wgpu-rs](https://github.com/gfx-rs/wgpu-rs) - idiomatic Rust wrapper with [a few more examples](https://github.com/gfx-rs/wgpu-rs/tree/master/examples) to get a feel of the API
- [almarklein/wgpu-py](https://github.com/almarklein/wgpu-py) - experimental Python wrapper
- [porky11/wgpu](https://nest.pijul.com/porky11/wgpu) - experimental [Scopes](http://scopes.rocks) wrapper
- [cshenton/WebGPU.jl](https://github.com/cshenton/WebGPU.jl) - experimental Julia wrapper

## Supported Platforms

   API   |       Windows      |       Linux        |    macOS & iOS     |
  -----  | ------------------ | ------------------ | ------------------ |
  DX11   | :white_check_mark: |                    |                    |
  DX12   | :heavy_check_mark: |                    |                    |
  Vulkan | :heavy_check_mark: | :heavy_check_mark: |                    |
  Metal  |                    |                    | :heavy_check_mark: |
  OpenGL | :construction:     | :construction:     | :construction:     |

## Usage

This repository contains C-language examples that link to the native library targets and perform basic rendering and computation. Please refer to our [Getting Started](https://github.com/gfx-rs/wgpu/wiki/Getting-Started#getting-started) page at the wiki for more information.
