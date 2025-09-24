FROM ubuntu:plucky

RUN apt-get update && apt-get install -y --no-install-recommends --no-install-suggests \
    wget \
    make \
    libfontconfig1 \
    perl \
    perl-base \
    perl-modules \
    libgraphite2-3 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
# perl is for tinytex compilation
# libgraphite2-3 is for tectonic

ARG FILE_NAME=TinyTeX-0-v2025.09.tar.gz
RUN wget https://github.com/rstudio/tinytex-releases/releases/download/v2025.09/${FILE_NAME} -O ${FILE_NAME} --no-check-certificate
RUN tar -xzf ${FILE_NAME} -C /usr/local
RUN rm ${FILE_NAME}
ENV PATH="/usr/local/.TinyTeX/bin/x86_64-linux:${PATH}"

# tectonic
ARG TECTONIC_VERSION=0.15.0
RUN wget https://github.com/tectonic-typesetting/tectonic/releases/download/tectonic%40${TECTONIC_VERSION}/tectonic-${TECTONIC_VERSION}-x86_64-unknown-linux-gnu.tar.gz -O ${TECTONIC_VERSION}.tar.gz --no-check-certificate
RUN tar -xzf ${TECTONIC_VERSION}.tar.gz -C /usr/local/bin/
RUN rm ${TECTONIC_VERSION}.tar.gz
ENV PATH="/usr/local/bin:${PATH}"


# RUN apt-get install fonts-noto-cjk
# RUN tlmgr update --self --all
# RUN tlmgr install ctex
# RUN tlmgr install xetex latex-bin
# RUN tlmgr install fancyhdr booktabs latexindent 
# RUN fmtutil-sys --byfmt xelatex
