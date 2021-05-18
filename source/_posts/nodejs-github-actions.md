---
title: nodejs github-actions publish
date: 2021-05-18 16:36:24
tags: [actions,nodejs,github]
---
## pre1
```
ssh-keygen -t rsa
ssh-copy-id -i xxx_rsa.pub root@x.x.x.x
```

## pre2
```
github secrets add private-key example xxx_rsa
```

## sample

```
# This workflow will do a clean install of node dependencies, build the source code and run tests across different versions of node
# For more information see: https://help.github.com/actions/language-and-framework-guides/using-nodejs-with-github-actions

name: Node.js CI

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]
  watch:
    types: [started]

jobs:
  build:

    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [12.x]
        # See supported Node.js release schedule at https://nodejs.org/en/about/releases/

    steps:
    - uses: actions/checkout@v2
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v2
      with:
        node-version: ${{ matrix.node-version }}
    - name: Install dependencies
      run: yarn --frozen-lockfile
    - run: yarn run build
    - run: tar -zcvf ./dist.tar.gz ./dist
    - name: deploy file
      uses: wlixcc/SFTP-Deploy-Action@v1.0
      with:
        username: ${{ secrets.USERNAME }}
        server: ${{ secrets.HOST }}
        ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }} 
        port: ${{ secrets.PORT }} 
        local_path: './dist.tar.gz'
        remote_path: '/root/war'
    - name: executing remote ssh commands using ssh key
      uses: appleboy/ssh-action@master
      with:
        host: ${{ secrets.HOST }}
        username: ${{ secrets.USERNAME }}
        key: ${{ secrets.SSH_PRIVATE_KEY }}
        port: ${{ secrets.PORT }}
        script: /root/shell/default-jl.sh
```

# GitHub Action SCP , another example

Simple GitHub Action to copy a folder or single file to a remote server using SSH. This is working with the latest [GitHub Actions](https://github.com/features/actions).

## ✨ Example Usage

**Copy a folder recursively to a remote server**

```yml
- name: Copy folder content recursively to remote
        uses: garygrossgarten/github-action-scp@release
        with:
          local: test
          remote: scp/directory
          host: ${{ secrets.HOST }}
          username: ${{ secrets.SSH_USER }}
          password: ${{ secrets.PASSWORD }}

```

**Copy a single file to a remote server**

```yml
- name: Copy single file to remote
        uses: garygrossgarten/github-action-scp@release
        with:
          local: test/oof.txt
          remote: scp/single/oof.txt
          host: ${{ secrets.HOST }}
          username: ${{ secrets.SSH_USER }}
          password: ${{ secrets.PASSWORD }}

```
