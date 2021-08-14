---
layout: post
title: 백준 1427번 소트인사이드 (python 파이썬)
subtitle: 백준 1427번 소트인사이드
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1427번 소트인사이드 문제를 Python으로 해결한 문제이다.  

* [백준 1427번 소트인사이드 문제 링크](https://www.acmicpc.net/problem/1427){:target="_blank"}


### 문제 
배열을 정렬하는 것은 쉽다. 수가 주어지면, 그 수의 각 자리수를 내림차순으로 정렬해보자.


### 입력
첫째 줄에 정렬하고자하는 수 N이 주어진다. N은 1,000,000,000보다 작거나 같은 자연수이다.


### 출력
**<u>첫째 줄에 자리수를 내림차순으로 정렬한 수를 출력한다.</u>**


### 문제풀이
1. 문자 배열을 list로 입력받는다.
2. 파이썬의 sort를 이용하여 내림차순 정렬을한다.
3. join으로 해당 리스트를 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = list(read())
N.sort(reverse=True)

print(''.join(N))
```