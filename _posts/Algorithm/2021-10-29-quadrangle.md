---
layout: post
title: 백준 1085번 직사각형에서 탈출 (python 파이썬)
subtitle: 백준 1085번 직사각형에서 탈출
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1085번 직사각형에서 탈출 문제를 Python으로 해결한 문제이다.  

* [백준 1085번 직사각형에서 탈출 문제 링크](https://www.acmicpc.net/problem/1085){:target="_blank"}


### 문제 
한수는 지금 (x, y)에 있다. 직사각형은 각 변이 좌표축에 평행하고, 왼쪽 아래 꼭짓점은 (0, 0), 오른쪽 위 꼭짓점은 (w, h)에 있다. 직사각형의 경계선까지 가는 거리의 최솟값을 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 x, y, w, h가 주어진다.


### 출력
**<u>첫째 줄에 문제의 정답을 출력한다.</u>**


### 문제풀이
해당 문제는 대각선 경계면까지의 경로에서 대각선은 고려하지 않아도 된다.  
(x, y) 좌표가 직사각형 내부의 어느 위치에 있건 x축, y축과 평행하는 4가지의 거리만 구하면 (x, y) 좌표에서 대각선의 경계면까지의 가장 짧은 거리는 4개 중에 하나에 해당하게 되기 때문이다. 


### 코드
```python
import sys

read = sys.stdin.readline

x, y, w, h = list(map(int, read().split()))

print(min([x, y, w - x, h - y]))
```