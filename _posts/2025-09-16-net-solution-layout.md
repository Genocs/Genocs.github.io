---
title: ".NET Solution Repository layout"
date: 2025-09-16 10:00:00 -0700
categories: architectures
---


## Repository structure for .NET Solution

```plaintext
root-project/
├── .cursor/
│   └── rules/
├── .git/
├── .github/
│   ├── chatmodes/
│   ├── instructions/
│   ├── workflows/
│   └── copilot-instructions.md
├── devops/
│   └── azure/
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


## Build pipeline
The build pipeline shall not take more the 10 min to be completed. 1 min is the default value

## Unit test
The unit test shall not take more the 5 min to be completed. 2 min is the default value

## Deployment pipeline
The deployment pipeline shall be separated by the build pipeline.

## Database migration shall be disabled and only manual migration shall be possible.

## Commit and PR
PR approvation is not compulsory, developer will decide when code review is need.


| Repo                        | Artifact             | Note                            |
|-----------------------------|----------------------|----------------------------------|

