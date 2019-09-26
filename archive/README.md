# alpine-rust

Smallest Alpine images for rust.

[![build](https://travis-ci.org/sitkevij/alpine-rust.svg?branch=master)](https://travis-ci.org/sitkevij/alpine-rust)

# install notes

- For Alpine Linux (glibc) we are interested in default host `x86_64-unknown-linux-gnu`
- See [Other installation methods](https://github.com/rust-lang-nursery/rustup.rs#other-installation-methods)

## rustup-init.sh build method

### apk del cargo
```
(1/2) Purging cargo (0.22.0-r3)
(2/2) Purging libgit2 (0.25.1-r4)
Executing busybox-1.27.2-r8.trigger
Executing glibc-bin-2.27-r0.trigger
OK: 333 MiB in 46 packages
```

### apk del rust
```
(1/7) Purging rust (1.22.1-r0)
(2/7) Purging rust-stdlib (1.22.1-r0)
(3/7) Purging musl-dev (1.1.18-r3)
(4/7) Purging llvm-libunwind-dev (5.0.0-r0)
(5/7) Purging llvm-libunwind (5.0.0-r0)
(6/7) Purging llvm4-libs (4.0.0-r6)
(7/7) Purging libffi (3.2.1-r4)
Executing busybox-1.27.2-r8.trigger
Executing glibc-bin-2.27-r0.trigger
OK: 166 MiB in 39 packages
```

### ~/rustup.rs/rustup-init.sh

```
Welcome to Rust!

This will download and install the official compiler for the Rust programming 
language, and its package manager, Cargo.

It will add the cargo, rustc, rustup and other commands to Cargo's bin 
directory, located at:

  /root/.cargo/bin

This path will then be added to your PATH environment variable by modifying the
profile file located at:

  /root/.profile

You can uninstall at any time with rustup self uninstall and these changes will
be reverted.

Current installation options:

   default host triple: x86_64-unknown-linux-gnu
     default toolchain: stable
  modify PATH variable: yes

1) Proceed with installation (default)
2) Customize installation
3) Cancel installation
```

### ~/rustup.rs/rustup-init.sh -y
```
info: downloading installer
info: syncing channel updates for 'stable-x86_64-unknown-linux-gnu'
info: latest update on 2018-03-01, rust version 1.24.1 (d3ae9a9e0 2018-02-27)
info: downloading component 'rustc'
info: downloading component 'rust-std'
info: downloading component 'cargo'
info: downloading component 'rust-docs'
info: installing component 'rustc'
info: installing component 'rust-std'
info: installing component 'cargo'
info: installing component 'rust-docs'
info: default toolchain set to 'stable'

  stable installed - rustc 1.24.1 (d3ae9a9e0 2018-02-27)
```