# Build system templates

## CMake

Configure a CMake project:
```bash
cmake -B build -S .
```

Build a CMake project:
```bash
cmake --build build
```

## Makefile (C and C++)

```bash
# Build
make -j16

# Clean
make clean
```

## Makefile (C++)

```bash
# Build
make -j16

# Clean
make clean
```

## Makefile (C and C++ Debug and Release)

```bash
# Build
make debug -j16
make release -j16

# Clean
make clean
```
