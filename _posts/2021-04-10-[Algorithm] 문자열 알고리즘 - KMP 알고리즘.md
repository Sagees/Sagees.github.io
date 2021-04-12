---
title: "[Algorithm] 문자열 알고리즘 - KMP 알고리즘"
date: 2021-04-10
categories: 문자열 KMP 알고리즘
toc: true
toc_sticky: true
---

**KMP 알고리즘**(Knuth-Morris-Pratt Algorithm)은 문자열 패턴 매칭 알고리즘으로, **접두사와 접미사**를 활용하여 <span style="color:red">불일치가 발생한 문자열의 앞부분</span>에 어떤 문자가 있는지 알고 있기에 앞부분에 대해 **다시 비교하지 않으면서** 매칭을 판단하는 알고리즘이다.

Time Complexity는 O(N+M), N은 문자열 길이, M은 패턴길이로 선형 시간동안 수행된다.

##