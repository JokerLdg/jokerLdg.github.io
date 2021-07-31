---
layout: post
title: 백준 2003번 수들의 합 2 (python 파이썬)
subtitle: 백준 2003번 수들의 합 2
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2003번 수들의 합 2 문제를 Python으로 해결한 문제이다.  

* [백준 2003번 수들의 합 2 문제 링크](https://www.acmicpc.net/problem/2003){:target="_blank"}


### 문제 
N개의 수로 된 수열 A[1], A[2], …, A[N] 이 있다. 이 수열의 i번째 수부터 j번째 수까지의 합 A[i] + A[i+1] + … + A[j-1] + A[j]가 M이 되는 경우의 수를 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 N(1 ≤ N ≤ 10,000), M(1 ≤ M ≤ 300,000,000)이 주어진다. 다음 줄에는 A[1], A[2], …, A[N]이 공백으로 분리되어 주어진다. 각각의 A[x]는 30,000을 넘지 않는 자연수이다.


### 출력
**<u>첫째 줄에 경우의 수를 출력한다.</u>**


### 문제풀이
해당 문제는 투포인터를 이용하여 풀면 된다.

1. 시작, 끝 포인터와 합계 변수를 선언한다.  
2. 반복문을 돌린다.
    * total 값이 M보다 크다면 A[end] 값을 빼주고 end 포인터를 1 증가시킨다.
    * total 값이 M보다 작다면 A[start] 값을 더해주고 start 포인터를 1 증가시킨다.
    * 수열의 합이 M과 같아야 하므로 total 값이 M과 같으면 answer를 증가시킨다.
    * 시작값이 A의 길이와 동일하면 배열을 다 돌은것으로 반복문을 종료한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N, M = map(int, read().split())
A = list(map(int, read().split()))

start = end = total = 0
answer = 0

while True:
    if total > M:
        total -= A[end]
        end += 1
    elif start == len(A):
        break
    else:
        total += A[start]
        start += 1

    if total == M:
        answer += 1

print(answer)
```