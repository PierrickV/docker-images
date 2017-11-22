FROM debian:stretch
RUN apt update -qq && apt install -y \
      git \
      build-essential \
      libssl-dev \
    && git clone --depth=1 https://github.com/magnumripper/JohnTheRipper.git \
    && cd JohnTheRipper/src \
    && ./configure \
    && make clean \
    && make -s \
    && apt remove -y \
        git \
        build-essential \
        libssl-dev \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/JohnTheRipper/run/john"]
