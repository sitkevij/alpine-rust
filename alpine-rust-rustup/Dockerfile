FROM sitkevij/alpine-rust:base-glibc
# FROM frolvlad/alpine-glibc
LABEL org.label-schema.name="alpine-rust" \
      org.label-schema.description="Alpine image with rust, cargo and rustup" \
      org.label-schema.url="https://hub.docker.com/r/sitkevij/alpine-rust/" \
      org.label-schema.usage="https://github.com/sitkevij/alpine-rust/blob/master/README.md" \
      org.label-schema.vcs-url="https://github.com/sitkevij/alpine-rust" \
      org.label-schema.vendor="sitkevij" \
      org.label-schema.version="0.1.0" \
      maintainer="https://github.com/sitkevij"
ENV RUSTUP_TOOLCHAIN=stable-x86_64-unknown-linux-musl
RUN cd && \
apk update && \
apk upgrade && \
apk add curl ca-certificates gcc make zlib-dev openssl-dev perl git
RUN cd && git clone --depth 1 https://github.com/rust-lang-nursery/rustup.rs.git && cd rustup.rs && cargo build --release
RUN echo "export PATH=$PATH:~/.cargo/bin"  >> ~/.profile && source ~/.profile && \
apk del cargo && \
apk del rust && \
~/rustup.rs/rustup-init.sh -y

# ~/rustup.rs/rustup-init.sh
# apk del cargo
# (1/2) Purging cargo (0.22.0-r3)
# (2/2) Purging libgit2 (0.25.1-r4)
# Executing busybox-1.27.2-r8.trigger
# Executing glibc-bin-2.27-r0.trigger
# OK: 333 MiB in 46 packages
# apk del rust
# (1/7) Purging rust (1.22.1-r0)
# (2/7) Purging rust-stdlib (1.22.1-r0)
# (3/7) Purging musl-dev (1.1.18-r3)
# (4/7) Purging llvm-libunwind-dev (5.0.0-r0)
# (5/7) Purging llvm-libunwind (5.0.0-r0)
# (6/7) Purging llvm4-libs (4.0.0-r6)
# (7/7) Purging libffi (3.2.1-r4)
# Executing busybox-1.27.2-r8.trigger
# Executing glibc-bin-2.27-r0.trigger
# OK: 166 MiB in 39 packages
# curl https://sh.rustup.rs -sSf | sh -s -- -y