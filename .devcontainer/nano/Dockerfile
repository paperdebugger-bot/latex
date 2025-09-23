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
    tectonic \
    sudo \
    && rm -rf /var/cache/apk/*
# perl is for LaTeX compilation
# ca-certificates for secure downloads
# bash, curl, git, shadow, sudo are required by devcontainer features

# set default bash
ENV SHELL=/bin/bash
RUN bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)"
