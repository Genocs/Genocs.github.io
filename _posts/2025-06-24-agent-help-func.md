---
title: "Multi Agent useful function"
date: 2025-06-24
---

# Introduction 

This file contains useful stuff in case of you want to use LLM agents to build software solutions



Use following command to display folder structure that you can pass to LLM like Claude.

``` bash
find . -maxdepth 1 -not -path './\.*' -not -path '*/node_modules*' | sort | sed -e 's/[^-][^\/]*\// |/g' -e 's/|\([^ ]\)/|\1/'
```
