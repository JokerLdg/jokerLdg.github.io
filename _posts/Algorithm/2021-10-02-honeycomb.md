---
layout: post
title: 백준 2292번 벌집 (python 파이썬)
subtitle: 백준 2292번 벌집
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2292번 벌집 문제를 Python으로 해결한 문제이다.  

* [백준 2292번 벌집 문제 링크](https://www.acmicpc.net/problem/2292){:target="_blank"}


### 문제 
![그림](/img/algorithm/honeycomb.PNG)

위의 그림과 같이 육각형으로 이루어진 벌집이 있다. 그림에서 보는 바와 같이 중앙의 방 1부터 시작해서 이웃하는 방에 돌아가면서 1씩 증가하는 번호를 주소로 매길 수 있다. 숫자 N이 주어졌을 때, 벌집의 중앙 1에서 N번 방까지 최소 개수의 방을 지나서 갈 때 몇 개의 방을 지나가는지(시작과 끝을 포함하여)를 계산하는 프로그램을 작성하시오. 예를 들면, 13까지는 3개, 58까지는 5개를 지난다.


### 입력
첫째 줄에 N(1 ≤ N ≤ 1,000,000,000)이 주어진다.


### 출력
**<u>입력으로 주어진 방까지 최소 개수의 방을 지나서 갈 때 몇 개의 방을 지나는지 출력한다.</u>**


### 문제풀이
1. total의 값이 N보다 작거나 같을때까지 반복한다.
	* total += 6 * layer 의 공식을 적용한다.
	* layer값을 1 증가시킨다.
2. N이 1이면 1을 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())

total, layer = 2, 0

if N == 1:
    print(1)
else:
    while total <= N:
        total += 6 * layer
        layer += 1
    print(layer)
```