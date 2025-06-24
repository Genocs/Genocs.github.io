---
title: "Multi Agent useful function"
date: 2025-06-24
---

# Introduction 

This file contains useful stuff in ccase of you want to use agent to build software solutions



``` bash
find . -maxdepth 1 -not -path "./\.*" -not -path "*/node_modules*" | sort | sed -e "s/[^-][^\/]*\// |/g" -e "s/|\([^|]*\)$/|\1/"
```
