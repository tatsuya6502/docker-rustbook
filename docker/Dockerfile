FROM debian:jessie

MAINTAINER Tatsuya Kawano https://github.com/tatsuya6502

RUN (GIT_URL=https://github.com/tatsuya6502/rustbook.git && \
     GIT_BRANCH=rust-1.11.0-nightly && \
     apt-get update -qq && \
     DEBIAN_FRONTEND=noninteractive apt-get install -yy curl file gcc git make openssh-client sudo && \
     curl -sSf https://static.rust-lang.org/rustup.sh | sh -s -- --channel=nightly && \
     echo 'export PATH=$PATH:/root/.cargo/bin' >> /root/.bashrc && \
     cargo install --git $GIT_URL --branch $GIT_BRANCH && \
     DEBIAN_FRONTEND=noninteractive apt-get remove -yy --auto-remove --purge curl file)

CMD ["/bin/bash", "-l"]
