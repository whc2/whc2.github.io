---
layout: post
title:  Lib dependence for R packages installation
subtitle:   solve problems when installing R packages
date:   2024-05-08
author: HC
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - R
---

When compile a package on Linux, the system libs are often used. For example, `install.packages('scater')` reports **systemfonts** was lack. On the conda environment, `fontconfig` and `freetype2` are exsists in `include` directory. However, the `pkg-config` in the system can not detect them. If we install a `pkg-config` in conda, the problem is resolved.



```
1. install scater in R session:
>>>	BiocManager::install("scater")
'systemfonts' had non-zero exit status

2. install systemfont,
>>>	install.packages('systemfont')
compile error, no 'ft2build.h' 

3. install.packages('pkg-config')

4. install.packages('systemfont')


## better way
>>> conda install r::r-cairo
```
Enjoy, hope it will be usefull.

