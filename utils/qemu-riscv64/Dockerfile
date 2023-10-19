FROM ubuntu:22.04 as build

RUN apt-get update -y \
  && apt-get -y install git make gcc python3 python3-pip pkg-config libglib2.0-dev libpixman-1-dev flex bison ninja-build \
  && cd /tmp \
  && git clone https://git.qemu.org/git/qemu.git \
  && cd qemu \
  && ./configure --prefix=/usr --static --disable-system --target-list=riscv64-linux-user \
  && make -j 4 \
  && make install DESTDIR=/tmp/install

FROM ubuntu:22.04

COPY --from=build /tmp/install/usr/ /usr/