FROM opensuse:tumbleweed

# 0. Install dependencies
RUN zypper -n in which git-core gcc5-c++ 

# 1. Clone
RUN cd /tmp && \
    git clone --recursive --depth 1 https://github.com/boostorg/boost.git modular-boost >clone.log

# 2. Bootstrap 
RUN cd /tmp/modular-boost && ./bootstrap.sh

# 3. Build
RUN /tmp/modular-boost/b2 -j12 toolset=gcc cxxflags="-std=c++14" address-model=64 release

# 4. Verify
RUN pushd /tmp/modular-boost/bin.v2/libs/fiber/examples/gcc-6/release/link-static/threading-multi && \
    ./ping_pong
