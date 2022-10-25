---
course: CPSC317
title: Resource Records
topic: DNS
tags: DNS Caching
module: 4
date: [[2022-10-14]]
---

```
ResourceRecord(name, value, type, TTL)

type := A|NS|MX|CNAME|PTR

A: address
- name = hostname
- value = IP address

NS: name server
- name = domain
- value = name of DNS server for domain

MX: mail eXchanger
- name = domain in email address
- value = name of mail server

CNAME: canonical name
- name = alias
- value = canonical name

PTR: pointer
- name = reversed IP address
- value = hostname
```