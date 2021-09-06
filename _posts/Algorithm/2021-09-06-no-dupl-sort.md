---
layout: post
title: 백준 10867번 중복 빼고 정렬하기 (python 파이썬)
subtitle: 백준 10867번 중복 빼고 정렬하기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 10867번 중복 빼고 정렬하기 문제를 Python으로 해결한 문제이다.  

* [백준 10867번 중복 빼고 정렬하기 문제 링크](https://www.acmicpc.net/problem/10867){:target="_blank"}


### 문제 
N개의 정수가 주어진다. 이때, N개의 정수를 오름차순으로 정렬하는 프로그램을 작성하시오. 같은 정수는 한 번만 출력한다.


### 입력
첫째 줄에 수의 개수 N (1 ≤ N ≤ 100,000)이 주어진다. 둘째에는 숫자가 주어진다. 이 수는 절댓값이 1,000보다 작거나 같은 정수이다.


### 출력
**<u>첫째 줄에 수를 오름차순으로 정렬한 결과를 출력한다. 이때, 같은 수는 한 번만 출력한다.</u>**


### 문제풀이
1. N을 입력받는다.
2. 숫자를 배열에 넣어준다.
3. 배열을 정렬하고, set으로 중복을 제거한뒤, 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
arr = list(map(int, read().split()))

for i in sorted(list(set(arr))):
    print(i, end=' ')
```