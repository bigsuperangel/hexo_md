---
title: maven github-actions publish
date: 2020-09-24 16:36:24
tags: [actions,maven,java,github]
---

## sample

```
# This workflow will build a Java project with Maven
# For more information see: https://help.github.com/actions/language-and-framework-guides/building-and-testing-java-with-maven

name: Java CI with Maven

on:
  push:
    branches: [ master ]
    paths:
      - "doc/auto_deploy.txt"

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up JDK 1.8
      uses: actions/setup-java@v1
      with:
        java-version: 1.8
    - name: Build with Maven
      run: mvn -B package --file pom_github.xml -P sample_profile -Dmaven.test.skip=true
    - name: deploy file
      uses: wlixcc/SFTP-Deploy-Action@v1.0
      with:
        username: ${{ secrets.USERNAME }}
        server: ${{ secrets.HOST }}
        ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }} 
        port: ${{ secrets.PORT }} 
        local_path: './target/ROOT.war'
        remote_path: '/root/war'
    - name: executing remote ssh commands using ssh key
      uses: appleboy/ssh-action@master
      with:
        host: ${{ secrets.HOST }}
        username: ${{ secrets.USERNAME }}
        key: ${{ secrets.SSH_PRIVATE_KEY }}
        port: ${{ secrets.PORT }}
        script: ls -al
   
```
