---
layout: post
title: 백준 4153번 직각삼각형 (python 파이썬)
subtitle: 백준 4153번 직각삼각형
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 4153번 직각삼각형 문제를 Python으로 해결한 문제이다.  

* [백준 4153번 직각삼각형 문제 링크](https://www.acmicpc.net/problem/1193){:target="_blank"}


### 문제 
과거 이집트인들은 각 변들의 길이가 3, 4, 5인 삼각형이 직각 삼각형인것을 알아냈다. 주어진 세변의 길이로 삼각형이 직각인지 아닌지 구분하시오.


### 입력
입력은 여러개의 테스트케이스로 주어지며 마지막줄에는 0 0 0이 입력된다. 각 테스트케이스는 모두 30,000보다 작은 양의 정수로 주어지며, 각 입력은 변의 길이를 의미한다.


### 출력
**<u>각 입력에 대해 직각 삼각형이 맞다면 "right", 아니라면 "wrong"을 출력한다.</u>**


### 문제풀이
1. 가장 큰 값은 리스트에서 뺀다.
2. 가장 큰 값의 제곱과, 리스트안의 숫자들의 각각의 제곱의 합이 같다면 right를 출력, 아니면 wrong을 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

while True:
    t = list(map(int, read().split()))
    max_num = max(t)

    if sum(t) == 0:
        break

    t.remove(max_num)

    if (t[0] ** 2) + (t[1] ** 2) == max_num ** 2:
        print("right")
    else:
        print("wrong")
```