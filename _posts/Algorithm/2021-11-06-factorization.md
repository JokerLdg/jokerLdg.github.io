---
layout: post
title: 백준 11653번 소인수분해 (python 파이썬)
subtitle: 백준 11653번 소인수분해
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 11653번 소인수분해 문제를 Python으로 해결한 문제이다.  

* [백준 11653번 소인수분해 문제 링크](https://www.acmicpc.net/problem/11653){:target="_blank"}


### 문제 
정수 N이 주어졌을 때, 소인수분해하는 프로그램을 작성하시오.


### 입력
첫째 줄에 정수 N (1 ≤ N ≤ 10,000,000)이 주어진다.


### 출력
**<u>N의 소인수분해 결과를 한 줄에 하나씩 오름차순으로 출력한다. N이 1인 경우 아무것도 출력하지 않는다.</u>**


### 문제풀이
N이 2이상일때만 진행한다.

1. N이 1이 아닐때까지 반복한다.
2. N을 i로 나누었을때 나머지가 0이면 i를 출력한다.
3. N을 i로 나눈 몫을 N에 대입한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())

if N >= 2:
    i = 2
    while N != 1:
        if N % i == 0:
            N = N//i
            print(i)
        else:
            i += 1
```