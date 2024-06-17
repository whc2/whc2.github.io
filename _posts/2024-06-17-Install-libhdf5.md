---
layout: post
title:  Lib dependence for R package to run
subtitle:   solve problems when running R packages
date:   2024-06-17
author: HC
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - R
---

I want to use R package SeuratDisk. When I use `library(SeuratDisk)` to load the package, it reported that `libhdf5.so.8 no such file` on all node of the cluster. But, I can run `library(SeuratDisk)` on the head node, because there is `libhdf5.so.8` on this node in /lib/. The flowing steps can be used to solve this problem.



```
1. download HDF5:
>>>	wget -c "https://support.hdfgroup.org/ftp/HDF5/releases/hdf5-1.8/hdf5-1.8.13/bin/linux-x86_64/hdf5-1.8.13-linux-x86_64-shared.tar.gz"

2. untar the package:
>>>	tar xzvf hdf5-1.8.13-linux-x86_64-shared.tar.gz

3. add environment variable:
export LD_LIBRARY_PATH=.:software/hdf5-1.8.13-linux-x86_64-shared/lib/:$LD_LIBRARY_PATH

4. source ~/.bashrc

```
Enjoy, hope it will be usefull.

