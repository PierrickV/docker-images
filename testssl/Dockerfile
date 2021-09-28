FROM alpine

RUN apk add --no-cache bash procps drill git libidn coreutils

RUN addgroup testssl
RUN adduser -G testssl -g "testssl user" -s /bin/bash -D testssl
USER testssl
WORKDIR /home/testssl/

RUN git clone --depth=1 https://github.com/drwetter/testssl.sh.git

ENTRYPOINT ["/home/testssl/testssl.sh/testssl.sh"]

CMD ["--help"]
