---
layout: default
title: R Squared
---

### Introduction

DNS servers traditionally store their current data in their own memory. This creates two problems:
1. Lack of cache coherency - each server has its own view of the data
2. Overhead of writing and maintaining code to store the data (in memory).

R Squared intends to be a proof of concept name server that utilises other modern technologies to solve the above problems. Depending on the validity of the approach, future work could also make it an authoritative server too.

The main design choice for this work is [Redis](http://redis.io). Redis provides clustering/partitioning/sharding of data across multiple servers and replication for reliability.

### Roadmap

* The initial proof-of-concept is pure Ruby with a Redis back-end, caching only nameserver.
* Assuming (and I believe it's a safe assumption) Redis works fine, we'll carry on
* If ruby really isn't performant enough, port to C/hiredis
* Investigate methods for storing authoritative zone information in a modern datastore (such as [MongoDB](http://www.mongodb.org/))
