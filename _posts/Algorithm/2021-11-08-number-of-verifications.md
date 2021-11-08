---
layout: post
title: 백준 2475번 검증수 (python 파이썬)
subtitle: 백준 2475번 검증수
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2475번 검증수 문제를 Python으로 해결한 문제이다.  

* [백준 2475번 검증수 문제 링크](https://www.acmicpc.net/problem/2475){:target="_blank"}


### 문제 
컴퓨터를 제조하는 회사인 KOI 전자에서는 제조하는 컴퓨터마다 6자리의 고유번호를 매긴다. 고유번호의 처음 5자리에는 00000부터 99999까지의 수 중 하나가 주어지며 6번째 자리에는 검증수가 들어간다. 검증수는 고유번호의 처음 5자리에 들어가는 5개의 숫자를 각각 제곱한 수의 합을 10으로 나눈 나머지이다.

예를 들어 고유번호의 처음 5자리의 숫자들이 04256이면, 각 숫자를 제곱한 수들의 합 0+16+4+25+36 = 81 을 10으로 나눈 나머지인 1이 검증수이다.


### 입력
첫째 줄에 고유번호의 처음 5자리의 숫자들이 빈칸을 사이에 두고 하나씩 주어진다.


### 출력
**<u>첫째 줄에 검증수를 출력한다.</u>**


### 문제풀이
각 숫자에 제곱을 하여 다 더한뒤 10으로 나눈 나머지 1인 값을 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

numbers = list(map(int, read().split()))

answer = 0

for n in numbers:
    answer += n**2

print(answer % 10)
```