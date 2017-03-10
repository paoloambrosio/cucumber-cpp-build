# Run the container

```
docker run --rm -it paoloambrosio/cucumber-cpp-build bash
```

# Master
```
GMOCK_PATH=/usr/src/gmock ./travis.sh
```

# PR #135

## Checkout

```
git checkout -b muggenhor-gmock-dependency-fix master
git pull git://github.com/muggenhor/cucumber-cpp.git gmock-dependency-fix
```

## Build

Working (!?):
```
GMOCK_PATH=/usr/src/gmock ./travis.sh
```

Not working:
```
GMOCK_VER=1.8 ./travis.sh
```

Working (serial):
```
mkdir build
cmake -E chdir build cmake -DCUKE_ENABLE_EXAMPLES=ON -G Unix\ Makefiles ..
make -C build
```

Not working:
```
mkdir build
cmake -E chdir build cmake -DCUKE_ENABLE_EXAMPLES=ON -G Unix\ Makefiles ..
make -C build -j5
```

Not working:
```
mkdir build
cmake -E chdir build cmake -DCUKE_ENABLE_EXAMPLES=ON -G Ninja ..
cmake --build build
```

