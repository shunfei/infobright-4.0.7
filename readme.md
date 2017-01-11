This project is based on infobright-4.0.7 community edition.

We export the compression algorithm to Java via JNI.


*Node: You should compile c++ lib on the same platform as your cluster will run.*

### Install boost on Linux

* Download boost from [www.boost.org](http://www.boost.org/users/download/), we use `boost_1_59_0.tar.gz`, higher version should work as well.
* Compile boost

Switch to the appropriate user,
	
```shell
$> tar -xzf boost_1_59_0.tar.gz
$> cd boost_1_59_0
$> ./bootstrap.sh --prefix=/usr/local
$> ./b2 install
$> ls /usr/local/lib/
```

Check boost libs at `/usr/local/lib/`, we only need to deploy all libs in it.

### Install boost on Mac

Install via brew

```shell
$> sudo brew install boost
$> ls /usr/local/lib/*
```


### Compile cpp lib

Download sources and build the lib. 

```shell
$> git clone git@github.com:shunfei/infobright-4.0.7.git
$> cd infobright-4.0.7
$> ./compile_java_lib.sh
$> ls java_lib/
```

Now the `java_lib` folder should contains lib file. 

On mac:

```
libbhcompress.dylib
```

On linux:

```
libbhcompress.so
```
