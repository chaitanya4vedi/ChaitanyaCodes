---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
author:
images:
-
categories:
-
related:
  threshold: 80
  includeNewer: true
  toLower: false
  indices:
  - name: keywords
    weight: 100
  - name: date
    weight: 10
---

