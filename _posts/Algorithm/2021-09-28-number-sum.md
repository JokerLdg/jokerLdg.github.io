---
layout: post
title: 백준 11720번 숫자의 합 (python 파이썬)
subtitle: 백준 11720번 숫자의 합
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 11720번 숫자의 합 문제를 Python으로 해결한 문제이다.  

* [백준 11720번 숫자의 합 문제 링크](https://www.acmicpc.net/problem/11720){:target="_blank"}


### 문제 
N개의 숫자가 공백 없이 쓰여있다. 이 숫자를 모두 합해서 출력하는 프로그램을 작성하시오.


### 입력
첫째 줄에 숫자의 개수 N (1 ≤ N ≤ 100)이 주어진다. 둘째 줄에 숫자 N개가 공백없이 주어진다.


### 출력
**<u>입력으로 주어진 숫자 N개의 합을 출력한다.</u>**


### 문제풀이
1. 입력받은 숫자를 숫자 배열로 만든다.
2. 1번의 배열의 합계를 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
numbers = list(map(int, str(read())))

print(sum(numbers))
```