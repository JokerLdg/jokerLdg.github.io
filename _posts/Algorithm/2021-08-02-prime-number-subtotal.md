---
layout: post
title: 백준 1644번 소수의 연속합 (python 파이썬)
subtitle: 백준 1644번 소수의 연속합
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1644번 소수의 연속합 문제를 Python으로 해결한 문제이다.  

* [백준 1644번 소수의 연속합 문제 링크](https://www.acmicpc.net/problem/1644){:target="_blank"}


### 문제 
하나 이상의 연속된 소수의 합으로 나타낼 수 있는 자연수들이 있다. 몇 가지 자연수의 예를 들어 보면 다음과 같다.

* 3 : 3 (한 가지)
* 41 : 2+3+5+7+11+13 = 11+13+17 = 41 (세 가지)
* 53 : 5+7+11+13+17 = 53 (두 가지)

하지만 연속된 소수의 합으로 나타낼 수 없는 자연수들도 있는데, 20이 그 예이다. 7+13을 계산하면 20이 되기는 하나 7과 13이 연속이 아니기에 적합한 표현이 아니다. 또한 한 소수는 반드시 한 번만 덧셈에 사용될 수 있기 때문에, 3+5+5+7과 같은 표현도 적합하지 않다.

자연수가 주어졌을 때, 이 자연수를 연속된 소수의 합으로 나타낼 수 있는 경우의 수를 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 자연수 N이 주어진다. (1 ≤ N ≤ 4,000,000)


### 출력
**<u>첫째 줄에 자연수 N을 연속된 소수의 합으로 나타낼 수 있는 경우의 수를 출력한다.</u>**


### 문제풀이
해당 문제는 소수를 구하는 알고리즘인 에라토스테네스의 체를 이용하여 소수를 먼저 담아놓고, 투포인터를 이용하여 풀면 된다.

1. start 값이 end값과 작거나 같을때 까지 반복한다.
2. total의 값이 N값보다 작으면
    * end를 1 증가시킨다.
    * end가 prime_list의 길이보다 작으면 total에 prime_list[end]값을 증가시킨다.
    * end가 prime_list의 길이보다 크면 반복문을 종료한다.
3. total의 값이 N값보다 크거나 같으면 
    * total의 값이 N값과 같다면 answer를 1증가시킨다.
    * total에 prime_list[start]를 빼준다.
    * start값을 1 증가시킨다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

def get_prime_number_list(n):

    is_prime = [True] * (n + 1)

    for i in range(2, int(n ** 0.5) + 1):
        if is_prime[i]:
            for j in range(i * 2, n + 1, i):
                is_prime[j] = False
    return [i for i in range(2, n+1) if is_prime[i]]


N = int(read())
prime_list = get_prime_number_list(N)

if not prime_list:
    print(0)
else:
    total = prime_list[0]
    start = answer = end = 0

    while start <= end:
        if total < N:
            end += 1
            if end < len(prime_list):
                total += prime_list[end]
            else:
                break
        else:
            if total == N:
                answer += 1
            total -= prime_list[start]
            start += 1
    print(answer)
```