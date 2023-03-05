---
title: "Active Directory"
date: 2022-02-01
draft: true
categories:
  - "Cyber Security"
tags:
  - "AD"
  - "CEH"
---


Identify devices on the interanet
How to identify active directory domain controllers on the intranet by using DNS lookup
Example for Domain Name abc.local

nslookup -type=any _ldap._tcp.abc.local
nslookup -type=any _kerberos._tcp.abc.local
