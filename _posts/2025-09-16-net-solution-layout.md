---
title: ".NET Solution Repository layout"
date: 2025-09-16 10:00:00 -0700
categories: architectures
---


## Generic repository folder structure

```plaintext
root-project/
├── .azure/
│   └── pipelines/
├── .cursor/
│   └── rules/
├── .git/
├── .github/
│   ├── chatmodes/
│   ├── instructions/
│   ├── workflows/
│   └── copilot-instructions.md
├── infrastructure/
│   ├── bicep/
│   ├── k8s/
│   └── terraform/
├── docs/
├── scripts/
├── src/
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── LICENSE
├── README.md
```


## Repository structure for .NET Solution

```plaintext
root-project/
├── .azure/
│   └── pipelines/
├── .cursor/
│   └── rules/
├── .git/
├── .github/
│   ├── chatmodes/
│   ├── instructions/
│   ├── workflows/
│   └── copilot-instructions.md
├── infrastructure/
│   ├── bicep/
│   ├── k8s/
│   └── terraform/
├── scripts/
├── src/
├── .gitignore
├── .editorconfig
├── Directory.Build.props
├── Directory.Build.targets
├── dotnet.ruleset
├── global.json
├── stylecop.json
├── nuget.config
├── project.sln
├── README.md
```





| Repo                        | Artifact             | Note                            |
|-----------------------------|----------------------|----------------------------------|

