FROM debian:stable AS build

ENV DEBIAN_FRONTEND noninteractive
RUN set -e

RUN apt update -qq && apt install -y \
      git \
      build-essential \
      libssl-dev \
      python \
      libghc-zlib-dev

RUN git clone --depth=1 https://github.com/magnumripper/JohnTheRipper.git

RUN cd JohnTheRipper/src \
    && ./configure \
    && make clean \
    && make -s


FROM debian:stable-slim

RUN useradd --create-home john
COPY --from=build JohnTheRipper/ /home/john/JohnTheRipper
RUN apt update && apt install \
    libgomp1 \
  && rm -rf /var/lib/apt/lists/*
    
RUN chmod +x /home/john/JohnTheRipper/run/john
WORKDIR /home/john/
USER john

ENTRYPOINT ["/home/john/JohnTheRipper/run/john"]
CMD ["/home/john/JohnTheRipper/run/john --help"]