Semi-Markov
===========

A C++ library to specify and simulate trajectories from semi-Markov models.

## Requirements

- **C++20** compatible compiler (GCC 10+, Clang 10+, or MSVC 19.29+)
- Boost libraries (>= 1.54, recommended 1.70+)

## Building

See [BUILD.md](BUILD.md) for detailed build instructions.

Quick start on Ubuntu/Debian:
```bash
sudo apt-get install build-essential libboost-all-dev
./autogen.sh  # if building from git
./configure
make -j$(nproc)
```

## Documentation

[Documentation](http://afidd.github.io) on afidd.github.io.
