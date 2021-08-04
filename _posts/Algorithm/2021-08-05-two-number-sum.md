---
layout: post
title: 백준 3273번 두 수의 합 (python 파이썬)
subtitle: 백준 3273번 두 수의 합
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 3273번 두 수의 합 문제를 Python으로 해결한 문제이다.  

* [백준 3273번 두 수의 합 문제 링크](https://www.acmicpc.net/problem/3273){:target="_blank"}


### 문제 
n개의 서로 다른 양의 정수 a1, a2, ..., an으로 이루어진 수열이 있다. ai의 값은 1보다 크거나 같고, 1000000보다 작거나 같은 자연수이다. 자연수 x가 주어졌을 때, ai + aj = x (1 ≤ i < j ≤ n)을 만족하는 (ai, aj)쌍의 수를 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 수열의 크기 n이 주어진다. 다음 줄에는 수열에 포함되는 수가 주어진다. 셋째 줄에는 x가 주어진다. (1 ≤ n ≤ 100000, 1 ≤ x ≤ 2000000)


### 출력
**<u>문제의 조건을 만족하는 쌍의 개수를 출력한다.</u>**


### 문제풀이
1. 배열(arr)을 입력받고 정렬을 해준다.
    * 정렬을 하지 않으면 투 포인터를 정상적으로 사용할 수 없다.

2. arr[start]와 arr[end]를 더해서 temp 변수에 담는다.
    * temp가 x일 경우 answer를 1 증가 시킨다.
    * temp가 x보다 작을 경우는 두 값의 합이 부족하므로 start를 1 증가시킨다.(오름차순 정렬이기 때문에)
    * temp가 x보다 클 경우, end를 1 감소시킨다. (오름차순 정렬이기 때문에 한값 내려와야한다.)
 
3. 결과를 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

n = int(read())
arr = list(map(int, read().split()))
x = int(read())

arr.sort()

start, end = 0, n-1
answer = 0

while start < end:
    temp = arr[start] + arr[end]

    if temp == x:
        answer += 1

    if temp < x:
        start += 1
    else:
        end -= 1

print(answer)
```