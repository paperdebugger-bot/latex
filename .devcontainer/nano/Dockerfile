FROM ubuntu:plucky

RUN apt-get update && apt-get install -y --no-install-recommends --no-install-suggests \
    wget \
    make \
    fonts-noto-cjk \
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
RUN wget https://drop-sh.fullyjustified.net -O install.sh --no-check-certificate
RUN chmod +x install.sh
RUN ./install.sh
RUN mv tectonic /usr/local/bin/
ENV PATH="/usr/local/bin:${PATH}"

RUN tlmgr update --self --all
RUN tlmgr install ctex
RUN tlmgr install xetex latex-bin
RUN tlmgr install fancyhdr booktabs latexindent 
RUN fmtutil-sys --byfmt xelatex
