---
layout: post
title: 백준 4948번 베르트랑 공준 (python 파이썬)
subtitle: 백준 4948번 베르트랑 공준
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 4948번 베르트랑 공준 문제를 Python으로 해결한 문제이다.  

* [백준 4948번 베르트랑 공준 문제 링크](https://www.acmicpc.net/problem/4948){:target="_blank"}


### 문제 
베르트랑 공준은 임의의 자연수 n에 대하여, n보다 크고, 2n보다 작거나 같은 소수는 적어도 하나 존재한다는 내용을 담고 있다.

이 명제는 조제프 베르트랑이 1845년에 추측했고, 파프누티 체비쇼프가 1850년에 증명했다.

예를 들어, 10보다 크고, 20보다 작거나 같은 소수는 4개가 있다. (11, 13, 17, 19) 또, 14보다 크고, 28보다 작거나 같은 소수는 3개가 있다. (17,19, 23)

자연수 n이 주어졌을 때, n보다 크고, 2n보다 작거나 같은 소수의 개수를 구하는 프로그램을 작성하시오. 


### 입력
입력은 여러 개의 테스트 케이스로 이루어져 있다. 각 케이스는 n을 포함하는 한 줄로 이루어져 있다.

입력의 마지막에는 0이 주어진다.


### 출력
**<u>각 테스트 케이스에 대해서, n보다 크고, 2n보다 작거나 같은 소수의 개수를 출력한다.</u>**


### 문제풀이
1. 미리 최대 N의 소수를 에라토스테네스의 체를 이용하여 모두 구해놓는다.
2. n+1 <= x <= 2n 범위의 소수를 세어 준다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = 123456 * 2 + 1
prime_number = [True] * N

for i in range(2, int(N**0.5)+1):
    if prime_number[i]:
        for j in range(2*i, N, i):
            prime_number[j] = False

def prime_count(num):
    count = 0
    for i in range(num + 1, num * 2 +1):
        if prime_number[i]:
            count += 1
    print(count)

while True:
    number = int(read())
    if number == 0:
        break

    prime_count(number)

```