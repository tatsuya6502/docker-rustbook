FROM debian:jessie

MAINTAINER Tatsuya Kawano https://github.com/tatsuya6502

RUN (apt-get update -qq && \
     DEBIAN_FRONTEND=noninteractive apt-get install -yy curl file gcc git make openssh-client sudo && \
     curl -sSf https://static.rust-lang.org/rustup.sh | sh -s -- --channel=nightly && \
     echo 'export PATH=$PATH:/root/.cargo/bin' >> /root/.bashrc && \
     cargo install --git https://github.com/steveklabnik/rustbook.git && \
     DEBIAN_FRONTEND=noninteractive apt-get remove -yy --auto-remove --purge curl file)

CMD ["/bin/bash", "-l"]
