---
layout: post
title: 백준 11650번 좌표 정렬하기 (python 파이썬)
subtitle: 백준 11650번 좌표 정렬하기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 11650번 좌표 정렬하기 문제를 Python으로 해결한 문제이다.  

* [백준 11650번 좌표 정렬하기 문제 링크](https://www.acmicpc.net/problem/1181){:target="_blank"}


### 문제 
2차원 평면 위의 점 N개가 주어진다. 좌표를 x좌표가 증가하는 순으로, x좌표가 같으면 y좌표가 증가하는 순서로 정렬한 다음 출력하는 프로그램을 작성하시오.


### 입력
첫째 줄에 점의 개수 N (1 ≤ N ≤ 100,000)이 주어진다. 둘째 줄부터 N개의 줄에는 i번점의 위치 xi와 yi가 주어진다. (-100,000 ≤ xi, yi ≤ 100,000) 좌표는 항상 정수이고, 위치가 같은 두 점은 없다.


### 출력
**<u>첫째 줄부터 N개의 줄에 점을 정렬한 결과를 출력한다.</u>**


### 문제풀이
1. 배열을 입력받는다.
2. 배열을 정렬하는데, lambda를 이용하여 0번째, 1번째로 정렬한다.
3. 배열을 순서대로 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
arr = []

for _ in range(N):
    x, y = map(int, read().split())
    arr.append([x, y])

arr.sort(key=lambda x:(x[0], x[1]))

for x, y in arr:
    print(x, y)
```
