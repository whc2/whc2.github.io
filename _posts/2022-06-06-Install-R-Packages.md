---
layout: post
title:  Config libs for R packages installation
subtitle:   solve problems when installing R packages
date:   2022-06-06
author: HC
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - R
---

I use these steps to solve problems when installing R packages. Usually, R packages depend on a lot of newer libraries and the system (Linux) has only old libraries. We can copy a newer library from a conda envs, and add it to link library. This way we can use ner library and without root account.

```
1. find the probelm, such as:
>>>	/usr/lib64/libz.so.1: version \\\`ZLIB_1.2.9\\\' not found (required by /public/lib/libpng16.so.16)

2. check the problem,
>>>	strings /usr/lib64/libz.so.1 | grep 'ZLIB_'

3. we find ZLIB_1.2.9 is lost in /usr/lib64/libz.so.1

4. find /home/software/miniconda3/envs/R/ -name 'libz.so.1'		// locate a newer library

5. check whether the new library has "ZLIB_1.2.9"
>>>	strings  /home/software/miniconda3/envs/R/lib/libz.so.1 | grep 'ZLIB_'

6. create a directory to contain the new library
>>>	mkdir my_libs
>>>	cp /home/software/miniconda3/envs/R/lib/libz.so.1 .

7. add the directory to your link path
>>> export LD_LIBRARY_PATH=~/my_libs:$LD_LIBRARY_PATH

8. reinstall the R package you need
```
Enjoy, hope it will be usefull.
