---
layout: post
title: 백준 2747번 피보나치 수 (python 파이썬)
subtitle: 백준 2747번 피보나치 수
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2747번 피보나치 수 문제를 Python으로 해결한 문제이다.  

* [백준 2747번 피보나치 수 문제 링크](https://www.acmicpc.net/problem/2747){:target="_blank"}


### 문제 
피보나치 수는 0과 1로 시작한다. 0번째 피보나치 수는 0이고, 1번째 피보나치 수는 1이다. 그 다음 2번째 부터는 바로 앞 두 피보나치 수의 합이 된다.

이를 식으로 써보면 Fn = Fn-1 + Fn-2 (n ≥ 2)가 된다.

n=17일때 까지 피보나치 수를 써보면 다음과 같다.

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597

n이 주어졌을 때, n번째 피보나치 수를 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 n이 주어진다. n은 45보다 작거나 같은 자연수이다.


### 출력
**<u>첫째 줄에 n번째 피보나치 수를 출력한다.</u>**


### 문제풀이
피보나치 수열을 45번째 까지 만든후, n번째에 해당하는 값을 출력하면 된다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

fibonacci = [0, 1, 1]

for i in range(2, 45):
    fibonacci.append(fibonacci[i] + fibonacci[i-1])

n = int(read())

print(fibonacci[n])
```