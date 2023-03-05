---
title: ""
date: "2022-09-30"
draft: true
categories:
tags:
---



wmic service get name,pathname,displayname,startmode | findstr /i auto | findstr /i /v "C:\Windows\\" | findstr /i /v """
