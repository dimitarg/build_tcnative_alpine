# build_tcnative_alpine

## Overview

A gradle build script to build  netty-tcnative binaries for alpine linux and publish them to a repository - via a single command.

It utilizes [this docker image](https://github.com/pires/netty-tcnative-alpine) to build the binaries. Credits to [@pires](https://github.com/pires)


## Prerequisites
* You need docker on your system
* If you are publishing to a remote maven repository, you need this in your ~/.gradle/gradle.properties:
```
mavenRepoUrl=https://your/repo
mavenRepoUser=your_user
mavenRepoPassword=your_pass
```

## Configuration
You can confugure what version (and git tag) of tcnative will be built via the system property `tcnative_version`

## Usage

### Publishing to the local maven repo
`./gradlew publishToMavenLocal`

, or if you want to build a specific version:

`./gradlew publishToMavenLocal -Dtcnative_version=(some netty-tcnative git tag)`

### Publishing to the remote maven repo

**You need to setup `gradle.properties` like [this](#prerequisites)**


Again the commands are:

`./gradlew publish`

, or if you want to build a specific version:

`./gradlew publish -Dtcnative_version=(some netty-tcnative git tag)`

