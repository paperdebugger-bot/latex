FROM texlive/texlive:latest-full-doc

# Install additional packages
RUN apt-get update && apt-get install -y --no-install-recommends --no-install-suggests \
    wget \
    fonts-noto-cjk \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

   # tectonic
ARG TECTONIC_VERSION=0.15.0
# ARG ARCH=x86_64-unknown-linux-gnu
ARG ARCH=aarch64-unknown-linux-musl
RUN wget https://github.com/tectonic-typesetting/tectonic/releases/download/tectonic%40${TECTONIC_VERSION}/tectonic-${TECTONIC_VERSION}-${ARCH}.tar.gz -O ${TECTONIC_VERSION}.tar.gz --no-check-certificate
RUN tar -xzf ${TECTONIC_VERSION}.tar.gz -C /usr/local/bin/
RUN rm ${TECTONIC_VERSION}.tar.gz
ENV PATH="/usr/local/bin:${PATH}"


ENV SHELL=/bin/bash
RUN bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)"

