FROM alpine:latest

# Install essential packages for devcontainer features and tectonic
RUN apk update && apk add --no-cache \
    bash \
    libstdc++ \
    openssh \
    curl \
    git \
    make \
    perl \
    ca-certificates \
    fontconfig \
    font-noto \
    font-noto-cjk \
    shadow \
    sudo \
    && rm -rf /var/cache/apk/*
# perl is for LaTeX compilation
# ca-certificates for secure downloads
# bash, curl, git, shadow, sudo are required by devcontainer features

# tectonic
ARG TECTONIC_VERSION=0.15.0
# ARG ARCH=x86_64-unknown-linux-gnu
ARG ARCH=aarch64-unknown-linux-musl
RUN wget https://github.com/tectonic-typesetting/tectonic/releases/download/tectonic%40${TECTONIC_VERSION}/tectonic-${TECTONIC_VERSION}-${ARCH}.tar.gz -O ${TECTONIC_VERSION}.tar.gz --no-check-certificate
RUN tar -xzf ${TECTONIC_VERSION}.tar.gz -C /usr/local/bin/
RUN rm ${TECTONIC_VERSION}.tar.gz
ENV PATH="/usr/local/bin:${PATH}"

# set default bash
ENV SHELL=/bin/bash
RUN bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)"
