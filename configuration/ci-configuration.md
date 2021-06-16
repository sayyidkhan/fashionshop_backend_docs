---
description: Setup CI Configuration for this project
---

# CI Configuration

## Directory

**Directory to file from root directory:**

.github/workflows/main.yaml

## YAML File

open the yaml file for the changes to the CI. 

* Uncommenting the push command will allow build to occur on every commit into the repository into the specific branch
* can put other branches in the array \[ \] to add and cater to other branches

```yaml
name: Node.js CI

on:
#  push:
#    branches: [ dev ]
  pull_request:
    branches: [ main ]
  workflow_dispatch:

jobs:
  #1st CI job
  build_backend:
    name: Build backend
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - name: setup Node.JS
        uses: actions/setup-node@v2
        with:
          node-version: '12'

      - name: Install Dependencies
        run: npm install

      - name: Test
        run: npm run test:cov

      - name: Build
        run: npm run build
```

This workflow will do a clean install of node dependencies, build the source code and run tests across different versions of node.

For more information see: https://help.github.com/actions/language-and-framework-guides/using-nodejs-with-github-actions.

{% hint style="info" %}
This project is using node-version: 12
{% endhint %}

