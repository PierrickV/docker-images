FROM debian:stretch

ENV DEBIAN_FRONTEND noninteractive

RUN apt update -qq && apt install -y \
      git \
      build-essential \
      libssl-dev \
      zlibc \
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

WORKDIR "/JohnTheRipper/run/"

ENTRYPOINT ["john"]

CMD ["--help"]
