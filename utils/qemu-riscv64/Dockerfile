FROM debian:12.2

RUN apt-get update -y && apt-get -y install \
  autoconf \
  automake \
  autotools-dev \
  curl \
  python3 \
  python3-pip \
  libmpc-dev \
  libmpfr-dev libgmp-dev \
  gawk \
  build-essential \
  bison \
  flex \
  texinfo \
  gperf \
  libtool \
  patchutils \
  bc \
  zlib1g-dev \
  libexpat-dev \
  ninja-build \
  git \
  cmake \
  libglib2.0-dev \
  make \
  gcc \
  pkg-config \
  libpixman-1-dev 

RUN git clone https://git.qemu.org/git/qemu.git /tmp/qemu \
  && cd /tmp/qemu \
  && ./configure --prefix=/usr --disable-docs --target-list=riscv64-softmmu 

RUN make -j 4 \
  && make install