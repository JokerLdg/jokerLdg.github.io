---
layout: post
title: 백준 2869번 달팽이는 올라가고 싶다 (python 파이썬)
subtitle: 백준 2869번 달팽이는 올라가고 싶다
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2869번 달팽이는 올라가고 싶다 문제를 Python으로 해결한 문제이다.  

* [백준 2869번 달팽이는 올라가고 싶다 문제 링크](https://www.acmicpc.net/problem/2869){:target="_blank"}


### 문제 
땅 위에 달팽이가 있다. 이 달팽이는 높이가 V미터인 나무 막대를 올라갈 것이다.

달팽이는 낮에 A미터 올라갈 수 있다. 하지만, 밤에 잠을 자는 동안 B미터 미끄러진다. 또, 정상에 올라간 후에는 미끄러지지 않는다.

달팽이가 나무 막대를 모두 올라가려면, 며칠이 걸리는지 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 세 정수 A, B, V가 공백으로 구분되어서 주어진다. (1 ≤ B < A ≤ V ≤ 1,000,000,000)


### 출력
**<u>첫째 줄에 달팽이가 나무 막대를 모두 올라가는데 며칠이 걸리는지 출력한다.</u>**


### 문제풀이
(V-B) / (A-B)라는 공식을 사용 했는데, 정상에 한번 도달하면 밤에 미끄러지지 않는걸 고려해 준것이다.

마지막에 올림하여 출력하는 이유는 4.0까지는 4일이고, 4.1 이상은 5일이기 때문이다.


### 코드
```python
import sys
import math

read = sys.stdin.readline

A, B, V = map(int, read().split())

day = (V-B) / (A-B)

print(math.ceil(day))
```