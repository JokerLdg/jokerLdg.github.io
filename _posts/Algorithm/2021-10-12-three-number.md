---
layout: post
title: 백준 10817번 세 수 (python 파이썬)
subtitle: 백준 10817번 세 수
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 10817번 세 수 문제를 Python으로 해결한 문제이다.  

* [백준 10817번 세 수 문제 링크](https://www.acmicpc.net/problem/10817){:target="_blank"}


### 문제 
세 정수 A, B, C가 주어진다. 이때, 두 번째로 큰 정수를 출력하는 프로그램을 작성하시오. 


### 입력
첫째 줄에 세 정수 A, B, C가 공백으로 구분되어 주어진다. (1 ≤ A, B, C ≤ 100)


### 출력
**<u>두 번째로 큰 정수를 출력한다.</u>**


### 문제풀이
숫자를 입력후 정렬하여 2번째의 값을 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

s = list(map(int, read().split()))
s.sort()

print(s[1])
```