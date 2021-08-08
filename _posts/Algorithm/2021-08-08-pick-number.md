---
layout: post
title: 백준 2230번 수 고르기 (python 파이썬)
subtitle: 백준 2230번 수 고르기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2230번 수 고르기 문제를 Python으로 해결한 문제이다.  

* [백준 2230번 수 고르기 문제 링크](https://www.acmicpc.net/problem/2230){:target="_blank"}


### 문제 
N개의 정수로 이루어진 수열 A[1], A[2], …, A[N]이 있다. 이 수열에서 두 수를 골랐을 때(같은 수일 수도 있다), 그 차이가 M 이상이면서 제일 작은 경우를 구하는 프로그램을 작성하시오.

예를 들어 수열이 {1, 2, 3, 4, 5}라고 하자. 만약 M = 3일 경우, 1 4, 1 5, 2 5를 골랐을 때 그 차이가 M 이상이 된다. 이 중에서 차이가 가장 작은 경우는 1 4나 2 5를 골랐을 때의 3이 된다.


### 입력
첫째 줄에 두 정수 N, M이 주어진다. 다음 N개의 줄에는 차례로 A[1], A[2], …, A[N]이 주어진다.


### 출력
**<u>첫째 줄에 M 이상이면서 가장 작은 차이를 출력한다. 항상 차이가 M이상인 두 수를 고를 수 있다.</u>**


### 문제풀이
1. 배열을 입력 받고 정렬한다.
2. start, end 포인터를 이용하여 큰값에서 작은값을 빼서 temp에 저장한다.
    * temp 값이 M과 같다면 answer에 M을 저장하고, 반복을 종료한다.
    * temp가 M보다 작다면 end 포인터를 1 증가시킨다.
    * temp가 M보다 크면, start 포인터를 1 증가시키고, answer와 temp중 더 작은값을 answer에 저장한다.
3. answer를 출력한다. 


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N, M = map(int, read().split())
arr = []

for _ in range(N):
    arr.append(int(read()))
    
arr.sort()

start, end = 0, 1
answer = sys.maxsize

while start < N and end < N:
    temp = arr[end] - arr[start]
    if temp == M:
        answer = M
        break
    if temp < M:
        end += 1
        continue
    start += 1
    answer = min(answer, temp)

print(answer)
```