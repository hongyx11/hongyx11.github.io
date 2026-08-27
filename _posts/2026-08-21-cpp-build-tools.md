---
title: "HPC Starter 02: C++ and build tools"
date: 2026-08-21
permalink: /hpc-starter/cpp-build-tools/
tags: [HPC Starter, C++, CMake]
excerpt: "Build a small numerical program with useful warnings, release optimization, tests, and CMake."
---

HPC software is often built from C, C++, or Fortran because these languages offer predictable data representation and close control over the machine. Fast code still begins with correct, readable code.

## Start with compiler feedback

For a single C++ file:

```bash
g++ -std=c++20 -Wall -Wextra -Wpedantic -O3 src/vector_sum.cpp -o vector_sum
```

Warnings catch suspicious code. `-O3` enables aggressive optimization, but optimization is not permission to use undefined behavior. During debugging, use a separate build with symbols and sanitizers:

```bash
g++ -std=c++20 -Wall -Wextra -g \
  -fsanitize=address,undefined src/vector_sum.cpp -o vector_sum_debug
```

## Make data layout visible

A contiguous `std::vector<double>` is usually preferable to a collection of separately allocated objects for a numerical kernel. Contiguous storage supports spatial locality, vectorization, and efficient bulk transfer to accelerators.

Use fixed-width integer types for stored formats when width matters. Use `std::size_t` for memory sizes and indices into standard containers. Avoid allocating memory inside the timed inner loop.

## Use CMake for a project

```cmake
cmake_minimum_required(VERSION 3.20)
project(hpc_starter LANGUAGES CXX)

add_executable(vector_sum src/vector_sum.cpp)
target_compile_features(vector_sum PRIVATE cxx_std_20)
target_compile_options(vector_sum PRIVATE -Wall -Wextra -Wpedantic)
```

Configure and build outside the source tree:

```bash
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build --parallel
./build/vector_sum
```

An out-of-source build keeps generated files separate and makes it easy to maintain `build-debug` and `build-release` configurations.

## Correctness before speed

For a kernel, implement a simple reference version and compare optimized output with a tolerance appropriate for floating-point computation. Test empty, small, irregular, and randomized inputs. A fast wrong answer is not a performance result.

## Exercise

Implement dot product for two `std::vector<double>` objects. Add:

1. a reference test with known input;
2. a release build and a sanitizer build;
3. command-line selection of vector length; and
4. a printed checksum that prevents the computation from being optimized away.

Record the compiler version and flags in your lab repository.

**Next:** [Performance foundations](/hpc-starter/performance-foundations/)

