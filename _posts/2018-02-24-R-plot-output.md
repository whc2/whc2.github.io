---
layout: post
title:  pdf output or svg output by R plot
subtitle:   there is issue to use pdf in AI
date:   2018-02-24
author: HC
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - blog
---

## begin
## R output file type problem
When I output a plot file generated by R scripts, pdf is opened by regular pdf viwer software. But the pdf file changed their colors when is opened by Adobe Illustrator. I think this is a incompatible issue that should be fixed.

The another option is to output svg file by R scripts, and then thansform it into pdf. Because NMDS plot by phyloseq in svg format can't be seen in AI directly. Open the pdf file in AI, and you can change it as you want.

-s
pdf x(AI)
svg -> pdf -> AI
