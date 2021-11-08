---
layout: post
title: 백준 11050번 이항 계수 1 (python 파이썬)
subtitle: 백준 11050번 이항 계수 1
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 11050번 이항 계수 1 문제를 Python으로 해결한 문제이다.  

* [백준 11050번 이항 계수 1 문제 링크](https://www.acmicpc.net/problem/11050){:target="_blank"}


### 문제 
자연수 N과 정수 K가 주어졌을 때 이항 계수를 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 N과 K가 주어진다. (1 ≤ N ≤ 10, 0 ≤ K ≤ N)


### 출력
**<u>이항계수 값을 출력한다.</u>**


### 문제풀이
N! / K! * (N-K)! 으로 계산하면 된다.


### 코드
```python
import sys
from math import factorial

read = lambda: sys.stdin.readline().rstrip()

N, K = map(int, read().split())

answer = factorial(N) // (factorial(K) * factorial(N-K))

print(answer)
```