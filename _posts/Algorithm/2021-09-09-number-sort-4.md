---
layout: post
title: 백준 11931번 수 정렬하기 4 (python 파이썬)
subtitle: 백준 11931번 수 정렬하기 4
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 11931번 수 정렬하기 4 문제를 Python으로 해결한 문제이다.  

* [백준 11931번 수 정렬하기 4 문제 링크](https://www.acmicpc.net/problem/11931){:target="_blank"}


### 문제 
N개의 수가 주어졌을 때, 이를 내림차순으로 정렬하는 프로그램을 작성하시오.


### 입력
첫째 줄에 수의 개수 N(1 ≤ N ≤ 1,000,000)이 주어진다. 둘째 줄부터 N개의 줄에는 숫자가 주어진다. 이 수는 절댓값이 1,000,000보다 작거나 같은 정수이다. 수는 중복되지 않는다.


### 출력
**<u>첫째 줄부터 N개의 줄에 내림차순으로 정렬한 결과를 한 줄에 하나씩 출력한다.</u>**


### 문제풀이
1. N을 입력받고, 배열에 값을 입력받는다.
2. sort와 reverse를 이용하여 내림차순으로 정렬한다.
3. 순서대로 출력해준다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
arr = []

for _ in range(N):
    arr.append(int(read()))

arr.sort(reverse=True)

for num in arr:
    print(num)
```