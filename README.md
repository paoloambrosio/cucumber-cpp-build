To build master:
```
$ docker run --rm -it paoloambrosio/cucumber-cpp-build bash
root@...# GMOCK_PATH=/usr/src/gmock ./travis.sh
```

To build PR #135:
```
$ docker run --rm -it paoloambrosio/cucumber-cpp-build bash
root@...# git checkout -b muggenhor-gmock-dependency-fix master
root@...# git pull git://github.com/muggenhor/cucumber-cpp.git gmock-dependency-fix
root@...# GMOCK_PATH=/usr/src/gmock ./travis.sh
```

