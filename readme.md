This project is based on infobright-4.0.7.

Try to make the compress module compilable independently, both on Linux and Mac ox. Some code have to modified for that.

##install boost:
* linux:

First down load boost from http://www.boost.org/users/download/, untar it, and then install by
```
./bootstrap.sh --prefix=/usr/local
./b2 install
```

* mac:

```
brew install boost

#if facing permission issue
sudo chown -R `whoami` /usr/local
```

## Setup environment:

```
export CPLUS_INCLUDE_PATH=${CPLUS_INCLUDE_PATH}:/usr/local/include
export C_INCLUDE_PATH=${C_INCLUDE_PATH}:/usr/local/include
export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/usr/local/lib
```

## Let's compile!

Download source code of Infobright Community Edition from http://www.infobright.org/, untar it.

```
cd <infobright src home>/src/storage/brighthouse

g++ -c -fPIC -I./ -I./community compress/*.cpp 
g++ -shared -o libcompress.so *.o -lboost_system

```

`libcompress.so` is the dynamic lib we want, right?