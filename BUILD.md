# Build Instructions

## Overview

This project is a C++ library for specifying and simulating trajectories from semi-Markov models.

## Requirements

### Compiler
- **C++20 compatible compiler** (one of the following):
  - GCC 10 or later
  - Clang 10 or later
  - MSVC 19.29 or later

### Dependencies
- **Boost >= 1.54** (recommended: 1.70 or later)
  - boost_system
  - boost_random
  - boost_program_options
  - boost_filesystem
  - boost_date_time
  - boost_thread
  - boost_chrono
  - boost_log
  - boost_log_setup
  - boost_unit_test_framework
- **pthread**

## Building on Linux/macOS

### Install Dependencies

#### Ubuntu/Debian
```bash
sudo apt-get update
sudo apt-get install -y build-essential libboost-all-dev
```

#### Fedora/RHEL
```bash
sudo dnf install gcc-c++ boost-devel
```

#### macOS (with Homebrew)
```bash
brew install boost
```

### Build Steps

1. **Configure the build** (if building from git):
   ```bash
   ./autogen.sh
   ```

2. **Configure** (or re-configure after changes):
   ```bash
   ./configure
   ```

   If Boost is installed in a non-standard location:
   ```bash
   ./configure --with-boost=/path/to/boost
   ```

3. **Compile**:
   ```bash
   make -j$(nproc)
   ```

4. **Install** (optional):
   ```bash
   sudo make install
   ```

## Building on Windows

On Windows, you can use MinGW-w64 or Visual Studio with the appropriate Boost libraries installed.

## Troubleshooting

### Boost not found
If configure cannot find Boost, set the `BOOST_ROOT` environment variable:
```bash
export BOOST_ROOT=/path/to/boost
./configure
```

### C++ Standard
The project requires **C++20**. This is configured in `Makefile.am` with the `-std=c++20` flag.

## Testing

After building, you can run the test programs:
```bash
./disttest
```

## Examples

Several example programs are built:
- `weiss` - Weiss model example
- `bvd` - BVD model example
- `sirmixed` - SIR mixed model
- `meta` - Metapopulation example
- `disttest` - Distribution tests

Run any example with:
```bash
./weiss --help
```
