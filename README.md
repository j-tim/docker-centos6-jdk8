# docker-centos6-jdk8

Docker file for Oracle JDK based on the official Centos Docker image. 

## Centos

version: 6.8

## Java Oracle 

JDK: 8u121
Buid: b13 

## Tags

JDK Oracle Java 8:

* latest (without Java Cryptography Extension (JCE) Unlimited Strength jars)
* unlimited (with Java Cryptography Extension (JCE) Unlimited Strength jars)

## Usage

```shell
docker run -it --rm jtim/centos6-jdk8 -version
```
