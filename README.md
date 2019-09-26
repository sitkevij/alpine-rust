# Smallest Rust Alpine Docker images

[![build](https://travis-ci.org/sitkevij/alpine-rust.svg?branch=master)](https://travis-ci.org/sitkevij/alpine-rust)

<img src="https://www.rust-lang.org/static/images/rust-logo-blk.svg" height="80" /><br/>
<img src="https://alpinelinux.org/alpinelinux-logo.svg" height="30" />

## building the rust image

### clone repo
```
git clone https://github.com/sitkevij/alpine-rust && cd alpine-rust
```

### docker build
```
docker build -t sitkevij/alpine-rust:latest .
```

### test docker image outputting `rustc` and `cargo` versions
```
docker run --rm sitkevij/alpine-rust rustc --version && docker run --rm sitkevij/alpine-rust cargo --version
```