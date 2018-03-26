FROM frolvlad/alpine-glibc
LABEL org.label-schema.name="docker-alpine-rust" \
      org.label-schema.description="Docker Alpine Rust Cargo" \
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
# RUN cd && git clone --depth 1 https://github.com/rust-lang-nursery/rustup.rs.git && cd rustup.rs && cargo build --release
RUN echo "export PATH=$PATH:~/.cargo/bin"  >> ~/.profile && source ~/.profile && \
apk del cargo && \
apk del rust && \
curl https://sh.rustup.rs -sSf | sh -s -- -y