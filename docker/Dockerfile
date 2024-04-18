FROM tpesout/hpp_base:latest
MAINTAINER nobody

### dipcall
WORKDIR /opt/dipcall
RUN wget https://github.com/lh3/dipcall/releases/download/v0.3/dipcall-0.3_x64-linux.tar.bz2 && \
    tar -jxf dipcall-0.3_x64-linux.tar.bz2 && \
    rm dipcall-0.3_x64-linux.tar.bz2

### apply patch from fork
WORKDIR /opt/dipcall/dipcall.kit
RUN wget https://github.com/rlorigro/dipcall_asm10/commit/4a776744fbee1b5b9f8d2648add91ebd510f72a5.patch && \
    git apply 4a776744fbee1b5b9f8d2648add91ebd510f72a5.patch
RUN grep "asm10" run-dipcall

WORKDIR /data
