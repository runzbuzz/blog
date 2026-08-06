---
layout: post
title:  "RcppArmadillo Quick Start"
description: blah blahj
author: Ahmad Alobaid
length: 2
categories: ["High Performance", "RcppArmadillo", "Rcpp"]
cover: armadillo.png
toc: true
---


# Summary

I wanted to compare **DeepSeek-V3** and **ChatGPT (GPT-4o)** to see how they perform in my use case: studying **statistical concepts** and using LLMs to explain them. While their responses were very similar, I did notice some key differences.

---




# Known Issues
## MacOS

Running <code>which gfortran</code> is getting you <code>/opt/homebrew/bin/gfortran</code>
Steps:
1. <code>mkdir .R; touch .R/Makevars</code>
2. <code>
FC      = /opt/homebrew/bin/gfortran
F77     = /opt/homebrew/bin/gfortran
FLIBS   = -L/opt/homebrew/lib/gcc
</code>

# References
- https://blog.cynkra.com/posts/2021-03-16-gfortran-macos/
- https://www.mjdenny.com/Rcpp_Intro.html
- https://arma.sourceforge.net/docs.html
