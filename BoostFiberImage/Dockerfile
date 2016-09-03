FROM opensuse:tumbleweed

# 0. Install dependencies
RUN zypper -n in which wget tar gcc6-c++ gcc-c++ gcc

# 1. Clone
RUN wget -qO-  http://downloads.sourceforge.net/boost/boost_1_62_0_b1.tar.gz | tar xz -C /tmp/

# 2. Bootstrap 
RUN cd /tmp/boost_1_62_0/ && ls -lah && ./bootstrap.sh

# 3. Build
RUN cd /tmp/boost_1_62_0/libs/fiber/examples && \
    /tmp/boost_1_62_0/b2 -j12 toolset=gcc cxxflags="-std=c++14" address-model=64 release

# 4. Verify
RUN pushd /tmp/boost_1_62_0/bin.v2/libs/fiber/examples/gcc-6/release/link-static/threading-multi && \
    ./ping_pong
