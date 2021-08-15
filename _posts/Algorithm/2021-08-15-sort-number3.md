---
layout: post
title: 백준 10989번 수 정렬하기 3 (python 파이썬)
subtitle: 백준 10989번 수 정렬하기 3
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 10989번 수 정렬하기 3 문제를 Python으로 해결한 문제이다.  

* [백준 10989번 수 정렬하기 3 문제 링크](https://www.acmicpc.net/problem/10989){:target="_blank"}


### 문제 
N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.


### 입력
첫째 줄에 수의 개수 N(1 ≤ N ≤ 10,000,000)이 주어진다. 둘째 줄부터 N개의 줄에는 숫자가 주어진다. 이 수는 10,000보다 작거나 같은 자연수이다.


### 출력
**<u>첫째 줄부터 N개의 줄에 오름차순으로 정렬한 결과를 한 줄에 하나씩 출력한다.</u>**


### 문제풀이
1. N값을 입력받는다.
2. 입력 받는 값이 10000까지 이기때문에 10001 까지 0으로 초기화 한 배열을 만든다.
3. 입력받는 수를 index 값으로 하여 index 값을 1씩 증가해준다.
4. 반복문을 돌면서 0이 아닐경우 해당 숫자만큼 index를 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline()

N = int(read())

numbers = [0] * 10001

for i in range(N):
    numbers[int(read())] += 1

for i in range(10001):
    if numbers[i] != 0:
        for j in range(numbers[i]):
            print(i)
```