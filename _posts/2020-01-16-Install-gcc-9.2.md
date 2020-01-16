---
layout: post
title:  Installation of GCC
subtitle:   my simple steps
date:   2020-01-16
author: HC
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - C++
---

I use these steps to install gcc 9.2.0.
```
1. download source code from [official site](https://gcc.gnu.org/)
2. tar xzvf gcc-9.2.0.tar.gz // uncompress 
3. mkdir gcc-9.2.0_obj // create a new directory for compilation
4. ./contrib/download_prerequisites // download prerequisites for compilation in gcc-9.2.0/ dir.
5. ln -s gmp-6.1.2/ gmp
    ln -s isl-0.18/ isl
    ln -s mpc-1.0.3/ mpc
    ln -s mpfr-3.1.4/ mpfr  // create link for compilation in gcc-9.2.0/ dir.
6. ../gcc-9.2.0/configure --prefix=/directory/to/install/ --enable-checking=release  --enable-languages=c,c++  --disable-multilib
    // configure C and C++ language in gcc-9.2.0_obj/ dir.
7. unset LD_LIBRARY_PATH
    unset LIBRARY_PATH  // unset environments in gcc-9.2.0_obj/ dir.
8. make -j8 // compile in gcc-9.2.0_obj/ dir.
9. make install // install in gcc-9.2.0_obj/ dir.
```


