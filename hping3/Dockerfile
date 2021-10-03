FROM debian:unstable-slim

RUN apt update -qq && apt install -y \
  hping3 \
&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["hping3"]

CMD ["--help"]
