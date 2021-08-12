---
layout: post
title: 백준 14921번 용액 합성하기 (python 파이썬)
subtitle: 백준 14921번 용액 합성하기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 14921번 용액 합성하기 문제를 Python으로 해결한 문제이다.  

* [백준 14921번 용액 합성하기 문제 링크](https://www.acmicpc.net/problem/14921){:target="_blank"}


### 문제 
홍익대 화학연구소는 다양한 용액을 보유하고 있다.  각 용액은 -100,000,000부터 100,000,000사이의 특성 값을 갖는데,

같은 양의 두 용액을 혼합하면, 그 특성값은 두 용액의 특성값의 합이 된다.

당신은 두 용액을 혼합하여 특성값이 0에 가장 가까운 용액을 만들려고 하는데, 각 용액은 10ml시험관에 10ml씩 들어있고, 빈 20ml 시험관이 단 하나 있다.  게다가 용액을 계량할 수 없어서, 두 용액을 섞을 때는 10ml씩 섞어서 20ml로 만드는데, 단 한번밖에 할 수 없다.  그래서 미리 용액의 특성값들을 보고, 어떤 두 용액을 섞을 것인지 정해야 한다.

예를 들어, 연구소에 있는 용액들의 특성값이 [-101, -3, -1, 5, 93]이라고 하자. 이 경우에 특성 값이 각각 -101, 93인 용액을 혼합하면 -8인 용액을 만들 수 있다. 또한 특성값이 5인 용액과 93인 용액을 혼합하면 특성 값이 98인 용액을 만들 수 있다.  모든 가능한 조합을 생각해 보면, 특성값이 2인 용액이 0에 가장 가까운 용액이다.

용액들의 특성값 A_1, … ,A_N이 오름차순으로 주어졌을 때, 이 중 두 개의 용액을 혼합하여 만들 수 있는 0에 가장 가까운 특성값 B를 출력하시오.


### 입력
```
N
A_1 A_2 … A_N
```
2 <= N <= 100,000
-100,000,000 <=A_i<=100,000,000
A_(i-1) <= A_i <= A_(i+1)


### 출력
```
B
```


### 문제풀이
해당 문제는 투포인터로 해결 할 수 있다.

1. start, end 를 통해 배열의 양쪽 끝에서부터 각 원소를 더해가며(temp) 최솟값을 찾는다.
- temp의 값이 음수이면 start를 1 증가한다.
- temp의 값이 양수이면 end를 1 감소한다.

2. 최솟값을 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())

arr = list(map(int, read().split()))

start, end = 0, N-1
answer = arr[start] + arr[end]

while start < end:
    temp = arr[start] + arr[end]
    if abs(answer) > abs(temp):
        answer = temp

    if temp < 0:
        start += 1
    else:
        end -= 1

print(answer)
```