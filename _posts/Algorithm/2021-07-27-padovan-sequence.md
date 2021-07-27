---
layout: post
title: 백준 9461번 파도반 수열 (python 파이썬)
subtitle: 백준 9461번 파도반 수열
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 9461번 파도반 수열 문제를 Python으로 해결한 문제이다.  

* [백준 9461번 파도반 수열 문제 링크](https://www.acmicpc.net/problem/9461){:target="_blank"}


### 문제 
아래 그림과 같이 삼각형이 나선 모양으로 놓여져 있다. 첫 삼각형은 정삼각형으로 변의 길이는 1이다. 그 다음에는 다음과 같은 과정으로 정삼각형을 계속 추가한다. 나선에서 가장 긴 변의 길이를 k라 했을 때, 그 변에 길이가 k인 정삼각형을 추가한다.

파도반 수열 P(N)은 나선에 있는 정삼각형의 변의 길이이다. P(1)부터 P(10)까지 첫 10개 숫자는 1, 1, 1, 2, 2, 3, 4, 5, 7, 9이다.

N이 주어졌을 때, P(N)을 구하는 프로그램을 작성하시오.

<p align="center"><img src="/img/algorithm/padovan.PNG"></p>


### 입력
첫째 줄에 테스트 케이스의 개수 T가 주어진다. 각 테스트 케이스는 한 줄로 이루어져 있고, N이 주어진다. (1 ≤ N ≤ 100)


### 출력
**<u>각 테스트 케이스마다 P(N)을 출력한다.</u>**


### 문제풀이
해당 수열은 피보나치 수열이랑 비슷하다.  

배열에 먼저 0,1,1,1 -2번째와 -1번째 배열의 값을 더하여 padovan 배열에 넣어주고, 
마지막에 N번째 배열에서 뽑아낸다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

padovan = [0, 1, 1, 1]

for i in range(3, 101):
    padovan.append(padovan[i-2] + padovan[i-1])

T = int(read())

for _ in range(T):
    N = int(read())
    print(padovan[N])
```