FROM texlive/texlive:latest-small

# Install additional packages
RUN apt-get update && apt-get install -y --no-install-recommends --no-install-suggests \
    wget \
    fonts-noto-cjk \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
