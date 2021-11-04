---
layout: post
title: 백준 2581번 소수 (python 파이썬)
subtitle: 백준 2581번 소수
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2581번 소수 문제를 Python으로 해결한 문제이다.  

* [백준 2581번 소수 문제 링크](https://www.acmicpc.net/problem/2581){:target="_blank"}


### 문제 
자연수 M과 N이 주어질 때 M이상 N이하의 자연수 중 소수인 것을 모두 골라 이들 소수의 합과 최솟값을 찾는 프로그램을 작성하시오.

예를 들어 M=60, N=100인 경우 60이상 100이하의 자연수 중 소수는 61, 67, 71, 73, 79, 83, 89, 97 총 8개가 있으므로, 이들 소수의 합은 620이고, 최솟값은 61이 된다.


### 입력
입력의 첫째 줄에 M이, 둘째 줄에 N이 주어진다.

M과 N은 10,000이하의 자연수이며, M은 N보다 작거나 같다.


### 출력
**<u>M이상 N이하의 자연수 중 소수인 것을 모두 찾아 첫째 줄에 그 합을, 둘째 줄에 그 중 최솟값을 출력한다. 단, M이상 N이하의 자연수 중 소수가 없을 경우는 첫째 줄에 -1을 출력한다.</u>**


### 문제풀이
소수 판별하는 함수를 하나 만드는데, 해당 수의 제곱근을 구해서, 2부터 그 수까지 나누었을때 나머지가 0이 아니면 소수로 판별하여 문제를 풀었다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

def isPrime(number):
    if number < 2:
        return False

    for i in range(2, int(number ** 0.5)+1):
        if number % i == 0:
            return False

    return True


M = int(read())
N = int(read())

prime_number = []

for n in range(M, N+1, 1):
    if isPrime(n):
        prime_number.append(n)

if len(prime_number) > 0:
    print(sum(prime_number))
    print(min(prime_number))
else:
    print(-1)
```
