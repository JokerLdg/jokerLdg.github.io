---
layout: post
title: 백준 10871번 X보다 작은 수 (python 파이썬)
subtitle: 백준 10871번 X보다 작은 수
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 10871번 X보다 작은 수 문제를 Python으로 해결한 문제이다.  

* [백준 10871번 X보다 작은 수 문제 링크](https://www.acmicpc.net/problem/10871){:target="_blank"}


### 문제 
정수 N개로 이루어진 수열 A와 정수 X가 주어진다. 이때, A에서 X보다 작은 수를 모두 출력하는 프로그램을 작성하시오.


### 입력
첫째 줄에 N과 X가 주어진다. (1 ≤ N, X ≤ 10,000)

둘째 줄에 수열 A를 이루는 정수 N개가 주어진다. 주어지는 정수는 모두 1보다 크거나 같고, 10,000보다 작거나 같은 정수이다.


### 출력
**<u>X보다 작은 수를 입력받은 순서대로 공백으로 구분해 출력한다. X보다 작은 수는 적어도 하나 존재한다.</u>**


### 문제풀이
number가 X보다 작으면 출력하는 방법으로 풀어보았다.

### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N, X = map(int, read().split())

numbers = list(map(int, read().split()))

for number in numbers:
    if number < X:
        print(number, end=" ")
```